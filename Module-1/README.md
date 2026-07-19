Welcome to Module1.

# 1: Installing Linux in a Virtual Machine(Virtual Box / VMware)

### Steps to download Ubuntu:
1. **Go to the official download page:** Visit the Ubuntu desktop download page.
2. **Select the correct version:** There will be a button to download the latest LTS((Long Term Support) version.
3. **Click download:** Click download button. There will be a option for "Intel or AMD 64-bit architecture"- this is the standard version we need for VirtualBox on almost all modern PCs.
4. **Locate the File:** Once download is finished, look in your downloads folder. You should see the file named sonething like(ubuntu-26.04-desktop-amd.iso) We will use this specific file when we create our virtual machine in VirtualBox.

### Steps to download VirtualBox:
1. **Download VirtualBox:** * Go to the official VirtualBox Download Page.
   * Under the "VirtualBox Platform Packages" section
   * click the link for your operating system.
   * The download will start automatically.
2. **Install VirtualBox:** * Once the download completes,
   * open the installer file.
   * Follow the installation wizard. we can safely leave all settings at their default values(click "Next" through the prompts.)
   * Once finished, click "Finish"
3. **Create a new virtual machine:** * Click "New" to create a new virtual machine. Fill in the appropriate details
   * **Name**
   * **Machine folder**
   * **ISO Image**
4. **Create a user profile:** * To enable the automatic install we need prepopulate our username and password here in addition to our machine name so that it can be configired automatically during first boot.
5. **Define the virtual machine's resources:** * In this section we can specify much of our host machine's memory and processors the virtual machine can be.
   * click "next" to continue and view a summary of your machine setting.
   * After this finish to initialize the machine.
6. **Install your Image:** * click start to launch the virtual machine.
   * We will see a message saying "powering VM up..." and our desktop window will appear.
   * On first boot the unattended installation will kick in.
   * At this stage resolution of window is fixed at 800*600. This is because guest additions features are not installed until after the ubuntu installtion has completed.
   * Once the installation completes the machine will automatically reboot to complete the intallation.
   * Finally we will be greeted with the ubuntu screen where we can enter our username and password defined during the initial detup.

### Bare - Metal Installation(Dual boot / full disk)
1. **Preparing the Drive(Resizing windows):** Before launching the installer, we must shrink our existing windows partition to create unallocated space. We identify the main partition (C:), right click it, and select "Shrink Volume". This action frees up the space the Ubuntu installer requires.
2. **The "Installation Type" Decision:** * After booting from the Ubuntu USB and proceeding past the initial setup, we reach the most critical screen:
   * Installation Type. The installer intelligently detects the existing operating systems. we must select "Install Ubuntu alongside Windows Boot Manager". This is the automated method that safely creates partitions within the unallocated space we made in step 1, preserving our windows installation.
3. **Confirmation to write changes:** * Before any physical changes are made to the disk, the installer presents a final detailed summary of the actions. This is our last opportunity to verify what is happening.
   * It confirms that existing partitions (like the windows NTFS C: drive) will be resized and the new partitions (formatted as ext4 and swap will be created. Crucially it lists the specific device identifiers (e.g., /dev/nvme0n1). Once we click "Continue", Partitioning begins.
4. **The final boot menu (GRUB):** * Once the installation completes and we reboot out machine. we will wncounter the GRUB (Grand Unified Bootloader) menu. This is the final verification that dual boot was successfull.
   * Instead ofbooting straigt into windows, the system now pauses here, preswnting a choice. We can use the arrow key to select either Ubuntu (the default) or the Windows Boot Manager (at the bottom).

## Partitioning Schemes : MBR vs GPT
### Partitioning Schemes: MBR vs GPT

The partitioning scheme determines how information about the disk's partitions is stored and accessed.

| Features | MBR (Master Boot Record) | GPT (GUID Partition Table) |
| :--- | :--- | :--- |
| **Age / Legacy** | Older (BIOS-based system) | Modern (UEFI-based systems) |
| **Max Disk Size** | ~2 TB | ~9.4 Zettabytes |
| **Max Partitions** | 4 Primary partitions | 128 partitions (default) |
| **Reliability** | Low (Single copy of table) | High (Redundant headers) |

* **MBR:** An aging standard that stores boot and partitioning data at the very beginning of the drive. Because it is limited to four primary partitions, users often use "extended" partitions, which can be complex to manage.
* **GPT:** The modern standard. It uses globally unique identifiers (GUIDs) and is integral to UEFI firmware. It is significantly more resilient to corruption because it stores copies of the partitions table at both the beginning and end of the disk.

### Linux Directory Mounting Points
In Linux, a partition can be "mounted" to a specific directory in the file system tree. This allows us to delegate storage space to different parts of the system.
* **`/` (Root):** The top of the file system hierarchy. It must contain the core operating system files, binaries, and system libraries. If we choose not to create separate partitions for other directories, everything defaults to `/`.
* **`/boot`:** Contains files required to boot the system, such as the Linux kernel and the bootloader (e.g., GRUB). Separating this can be useful for multi-boot setups or if our main disk uses an encryption scheme that the bootloader cannot read.
* **`/home`:** Stores user-specific files (documents, downloads, desktop settings). Keeping this on separate partitions is highly recommended. If we ever need to reinstall or change our Linux distribution, we can "wipe" the root partition without losing our personal data.
* **`/swap`:** This acts as a "virtual memory". When our physical RAM is full, the system moves inactive data to this space. Having a dedicated swap partition can sometimes provide minor performance benefits over a swap file, though modern systems use both effectively.

# 2. Introduction to BASH & Linux Command Line Essentials

##$ Shell and BASH
  At its core, a shell is a command-line interpreter - a program that acts as an interface between the user and the operating system's kernel. When we type commands into terminal, the shell interprets them and communicates with the kernel to execute those instructions.

  BASH (Bourne Again Shell) is the most widely used shell in Unix-like operating systems. It is an improved, open source version of the original Bourne shell (sh).

### Key Role of BASH
BASH performs three primary functions that make it essential for Linux administration and development.

* **Command Execution:** It allows us to run system binaries (like `ls`, `grep` or `awk`) and manages the environment in which those commands run.
* **Programmability (Scripting):** BASH is a full-fledged programming language. We can write scripts - files containing a series of commands to automate repetitive tasks. This includes using:
  * **Variables:** Storing data for later use.
  * **Conditionals:** Using `if`, `else`, and `case` statements to make decisions based on system state.
  * **Loops:** Using `for` and `while` to perform actions across multiple files or entries.
  * **Interaction and Redirection:** BASH provides powerful mechanisms to control input and output.
  * **Pipes (`|`):** Allows the output of one command to serve as the input for another.
    ```bash
     cat file.txt | grep "sear"
  * **Redirection (`>` or `>>`):** Sends output to a file instead of the screen.
  * **Wildcards (`*`, `?`):** Enables operations on groups of files.
  
    ```bash
    rm *.log
    ```
    *(Note: This command deletes all log files)*

---

## File System Structure

### Directory Path
* **Absolute and Relative Path:** An absolute path specifies the full path from the root directory (`/`).
  
  ```bash
  /home/user/documents/file.txt
  
* A relative path specifies the path relative to the current working directory.
  
  ```bash
  documents/files.txt

 The Linux file systemis organized in a hierarchial tree starting from the root (/). key directory includes:
 * **/:** The root directory, which serves as the base of the entire file system.
 * **/home:** Contains personal directories for individual users.
 * **/etc:** Used for system configuration files.
 * **/var:** Contains variable data, such as system logs.

## File and Directory Permission
* **chmod:"" Modifies file or directory permissions.
  ```bash
  chmod 755 script.sh

* **chown:** Changes the owner of a file or directory.
  ```bash
  chown user1 file.txt

## Basic file operations

1. **`cp` (Copy):** Copies files or directories from one location to another.
   ```bash
   cp file.txt /home/user/backup/file.txt
2. **`mv` (move):** moves or renames file or directories
   ```bash
   mv file.txt
3. **`rm` (remove):** delete file or directory.
   ```bash rm file.txt
4. **`man ls` (Manual of ls):** Displays the manual page for the ls command.
   ```bash
   man ls
5. **touch:** Creates an empty file or updates the timestamp of the existing file.
   ```bash
   touch newfile.txt
6. **`mkdir` (Make directory):** Creates a new directory.
   ```bash
   mkdir myfolder
7. **tree:** Displayss directory structure in a tree-like format.
   ```bash
   tree myfolder
8. **`cat` (concatenate):** Displays file coontent or concatenate multiple files.
   ```bash cat file.txt
9. **cut:** Extracts specific section from each line of a file.
    ```bash
    cut -d ',' -f 1 data.csv

## Redirection and Pipes
1. **> (Redirection Output):** Redirects coommand output to a file, owerwriting it.
   ```bash
   ls > output.txt
2. **>> (Append Output):** Appends command output to a file without overwritinng.
   ```bash
   echo "New line" >> output.txt
3. **| (pipe):** Sends the output of one command as input to another.
   ```bash
   ls | grep text

## Widcards, Quoting, and escaping characters
* **Wildcards:** Wildcards are special characters used in Linux to represent one or more characters in file-names or commands. They are particularly useful for matching multiple files or patterns in a single command.
  1. **Common Wildcards:**
     * **`*`:** Matches any string or characters, including an empty stringg.
     * **?:** Matches any single character.
     * **[]:** Matches any single character within the brackets.
    ```bash
    ls * txt
    ls file?.txt
    ls file[1-3].txt
 2. **Escaping wildcards:**  To use a wildcard character litterally (without its speacila meaning), you can escape it with a backslach(\).
    ```bash
    echo \*
* **Quouting and Escaping:** Quouting is used in linux to control how the shell interprests single quotes, double quotes, and backslashes.
  1. **Single quote(''):** Single quotes preserve the literal value of all characters within them, preventing the shell from interpreting any special characters.
     ```bash
     'Hello $USER'
  2. **Double quotes (""):** Double quotes preserve the literal value of most character but allow certain expansions, like variable sustitution.
     ```bash
     echo "Hello $USER"
  3. **Backslash(\):** A backslash escapes a single character, presenting the shell from interpreting its special meaning.
     ```bash
     echo \$USER
* **Escaping special characters:** Special characters like $, *, ?, etc can be escaped using a backslash to use them literally.
  ```bash
  echo \*

# 3. Introduction to BASH & Linuc command Line Essentials:

## Linux Installation
### 1. Downloading and Verifying ISOs
* **Acquisition:** Download the ISO from the official vendor website.
* **Verification:** Use checksum algorithms (like SHA-256) to compare the downloaded file's signature against the official hash provided on the website.

### 2. Installing Linux in a Virtual Machine (VM)
Virtualization provides a sandboxed environment for testing and development without affecting the host operating system.

* **Setup:** Configure the hypervisor (e.g., VirtualBox) by allocating CPU, RAM, and creating a virtual hard disk.
* **Deployment:** Boot the VM and load the ISO file to initiate the installer, which guides us through time zone, user account, and software setup.

### 3. Installing Linux on Physical Hardware (Bare-metal)
Installing directly on hardware requires a careful consideration of disk partitioning and firmware settings.

* **Bootable Media:** Flash the ISO to a USB drive using tools like Rufus or Etcher.
* **BIOS/UEFI Configuration:** Enter the system firmware to set the USB drive as the primary boot device.
* **Partitioning:** Define the structure of the disk. This often involves choosing between MBR (legacy) or GPT (modern) and creating specific mount points like `/` (root), `/home`, and `swap`.

## BASH Scripting
* **Writting Simple shell scripts:**
  1. **Variables and printing:** BASH scripts use variables to store data, which can be prinnted to the terminal using echho command.
     ```bash
     name="Gagandeep"
     echo "Hello, $name"
  2. **Conditionals:** Basic conditional logic allows scripts to execute specific block of code only when defined conditions are met.
     ```bash
     if [$USER == "gagandeep"]; then
     echo "Welcome"
     fi

* **Using man and help from Linux commands:**
  1. **man:** Provides the manual page for command, detailing its purpose and usage syntax
     ```bash
     man ls
  2. **help:** Offers quick, built-in guidance fro shell-specific commands.
     ```bash
     help cd

* **Text Processing Tools:**
  1. **grep:** Primarily used to filter and search for text pattern within filesor comand outputs.
     ```bash
     ls \ grep txt
  2. **awk:** A powerful stream-processing tool used for manipulating, transforming, and structured data.
     ```bash
     awk '{print $1}' student.txt
  3. **sed:** Powerful stream-processing tool used for manipulating, transforming, and extracting structured data.
     ```bash
     sed 's/Gagandeep/John/'student.txt

* **File Compression:**
  1. **tar:** Used to archive multiple files and directories into a single file (often called a tarball).
     ```bash
     tar-cvf backup.tar training-data/
  2. **gzip:** A utility used to compress archived giles or individual documents to reduce their total file size.
     ```bash
     gzip backup.tar
  3. **zip:** A utility used to compress archived files or individual document to reduce their total file size.
     ```bash
     zip -r file.zip training_data/

     
    
  
  
