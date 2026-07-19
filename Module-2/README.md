Welcome to module-2 : PC & Network Troubleshooting

# 1. PC Hardware Troubleshooting

## 1. Common PC boot issues and solutions
Power - On Self Test (POST) sequence is critical for diagnosing PC boot failure. When a computer power on. the BIOS/UEFI harware checks the CPU, RAM and Storage. A failure ai any stage halts the process.

### 1. **NO Power:** 
* **Symptoms:** The user presses the power button, but there is zero responce: no fan spin, no LED illuminate, and nobeed codes. The PC is electrically inert.
* **Diagnosis:** The failure is localized to the power delivery subsystem. The primary suspects are wall outlet, the power cable, or the power supply unit (PSU).
* **Solutions:**
  1. Bypass the power strip.
  2. Swap the cable.
  3. Apply the PSU "Paperclip Test".
  4. Clear CMOS.

### 2. **No Display:**
* **symptoms:** The PC power on; fan spin, LEDs activate, and you might even hear hard device activity or windows sound. However the monitor remains black, perhaps displaying "No signal" or "Going to sleep".
* **Diagnosis:** The PC is completing the POST, but the video signal is not reaching the monitor or cannot br rendered. The issue lies within the graphic card (GPU), the cable, or the display itself.
* **Solutions:**
  1. Basic Connection Check.
  2. Switch Ports.
  3. Reseat the GPU.
  4. Minimum Configiration.

### 3. **Boot loop:**
* **Symptoms:** The Pc power on, fan spin, and light com on. After a few seconds, the system abruptly powers off, the immediately restarts, repeating the cycle idefinately.
* **Diagnosis:** This is usually a protective measure triggered ny critical hardware instability during POST. The BIOS detects incorrect voltages, extreme tempratures, or incompatible RAM settngs and fails by Safe and rebooting.
* **Solutions:**
  1. Clear CMOS.
  2. Power off and remove all RAM sticks.
  3. Reseat one stick firmly.
  4. Test with different RAM stick.
  5. Hardware Isolation.

### 4. **No OS Found:**
* **Symptoms:** The PC completes POST successfully. The manufacture's splash screen appears. However instead of loading windows (or your OS), the process halts error message such as:
  * "Reboot and select proper Boot device"
  * "No bootable device found"
  * "A blinking cursor on a black screen."
* **Diagnosis:** The POST was successfule, meaning the core hardare is functional. The BIOS connot found a bootable partitions on any connected storage device. This is either a boot order priority issue or a catastrophic failure/corruption of storage device.
* **Solutions:**
  1. Check BIOS priority.
  2. Verify physical connection.
  3. Check BIOS recogonition.
  4. Repair via installation media.

## 2. Diagnosing Hardware Failures

### 1. **RAM**
* **Symptoms:** Random system crashes, blue screen of death (BSOD), failure to boot (POST), or memory management errors.
* **Diagnistic Methods:**
  1. **Software:** Run windows memory diagnostic or Mem Test 86.
  2. **Physical:** Reseat the modules. Test the individual stick in known good slots to isolate a faulty module.
  3. **Cleaning:** Use a compressed air to clean slots and a pencil eraser to gently clean the gold contacts.

### 2. HHD/SSD (Storage Devices)
* **Symptoms:** System freezes, the fill corruption, slow read/write speed, or clicking sound (mechanical HHD).
* **Diagnostic Method:"
  1. **Software:** Utilize CHKDSK vis command prompt for file system errors, or use SMART monitoring tools.
  2. **Physical:** Verify SATA/NVMe cable connections. If the BIOS does not defect the drive, it is often a conroller or power connection failure.

### 3. **GPU**
* **Symptoms:** Screen artifacts (lines, dots) driver crashes, system hands during gaming or rendering, or no signal output.
* **Diagnostic Methhod:**
  1. **Software:** Use DDu (Display Driver Uninstaller) to perform a clean driver reinstall. Run stress test to introduce failure under loud.
  2. **Physical:** Ensure the GPU is firmly seated and auxiliary power cables are connected. check for overheating due to fan failure or dust buildup.

### 4. **PSU**
* **Symptoms:** Sudden power-offs, system fails to turn on, intermittent reboot or burning smell.
* **Diagnistic Method:**
  1. **Methodology:** The PSU is difficult to text via software. Use a PSU tester or a multimeter to check voltage rails (3.3v, 5v, 12v)
  2. **Observation:** If the system is unstable under high load but stable at idle, it is a primary indicator of a failing or undersized PSU.

# PSU Hardware Troubleshooting
Troubleshooting hardware issues requires a systematic, layered approach to isolate the source of the problem.

## BIOS/UEFI settings and POST errors
The power-on seft test (POST) is the first stageof the boot process. If it fails, the computer cannot load the operating system.

### **POST Beep Codes**
If your computer has a internal speaker. It will emit a specific pattern of beep indicating the hardware failure.
| Beep Pattern | Typical Meaning |
| :--- | :--- |
| **1 short beep** | Normal POST; the system is functioning correctly. |
| **Continuous / Repeating** | Power supply, motherboard, or memory failure. |
| **1 long, 2 short** | Video card or graphics adapter failure. |
| **Repeating short** | Memory (RAM) or power supply issue. |
| **Random / Irregular** | Motherboard or CPU failure. |

### **POST/Error Messages:**
Modern motherboards often display text on the screen or have a "Debug LED" numeric/alphanumeric display on the board itself. Seach the specific code shown to identify the component (CPU, RAM, GPU) causing the hang.

### **BIOS/UEFI Configuration**
If the PC boots but behaves erractically:
1. **Check boot order:** Ensure your primary device is set as first boot device.
2. **Load optimized deafaults:" If you have overclocked or changed settings, resseting to factory defaults is the quickest way to rule out unstable configurations.
3. **Firmware updates:** Sometimes, bugs in the motherboard firmware cause hardware compatibility issues that can only be solved via an update.

## 3. Peripheral Troubleshooting
Peripheral issues are often related to connection, drivers, or power.
1. **Keyboard & Mouse:**
   * **Connections:** Switch ports (eg, move from a USB 3.0 port to a USB 2.0 port) to rule out a dead controller.)
   * **Drivers:** Open device manager in windows. If you see yellow exclamation mark under "Keyboard" or "Mice" and other pointing devices, right click to update or uninstall/reinstall driver.
  
2. **Printers:**
   * **Connectivity:** Confirm the printer is on the same network as the PC(for wireless) or that cable is firmly seated.
   * **Print spooler:** If jobs are stuck, search "Services" in windows, find print spooler, right click it, and click restart.
   * **Clear Queue:** Cancel all pending documents in the printer's control panel/queue to clear potential data corruption.

## BSOD and System Crash Analysis
A blue screen of death occurs when the kernel detects an error from which it cannot safely recover.

### **Undwerstanding the stop codes:**
Stop codes are either descriptive(text) or hexadecimal(numbers). They indicate which part of the system failed.
1. **PAGE_FAULT_IN_NONPAGED_AREA:** often memory related; check RAM or corrupted files.
2. **IRQL_NOT_LESS_OR_EQULA:** Usually an outdated, incompatible, or faulty deiver.
3. **CRITICAL_PROCESS_DIED:** A vital windows process stopped; check system file integrity.
4. **SYSTEM_SERVICE_EXCEPTION:** Often caused by conflicting drivers or antivirus software.
5. **WHEA_UNCORRECTABLE_ERROR:** Hardware-leve; error; indicates potential CPU or harware faiilure.

### **Dump files:** 
Windows creates memory dump files (.dump) when a crash occurs. Use tools like BlueScreenView or WinDbg to read these files and pinpointing the exact driver or process that triggered the crash

### **Commmon Causes and Fixes:**
1. **Drivers:** Frequently ate culprit  roll back recently updated drivers.
2. **RAM instability:** Run the Window Memory Diagnistic tool or memtest86 to check for the bad physical RAM stick.
3. **Overheating:** Use monitoring software (like HMVMonitor) to checkif your CPU or GPU is throttling due to high temperature.
4. **System File Corruption:** Run sfc/scannow in an elevated command prompt to scan and repair windows system files.

# 3. Software/System Troubleshooting

## **Safe mode:**
A diagnostic startup environment that runs on a minimal set of essential files, drivers, and core services. It isolates the system by disabling non-essential software, start-up applications, and network drivers to contrilled zone for advanced recovery.

## **System Restore:** 
With system restore we can revert on out PC's state to a previous point inn time. This can be particularly usefult when troubleshooting issues caused by recent changes, such as software installation, driver updates or system settings modifications. By using system restore, we can undo these changes without affecting our personal data, providing a safe way to restore problems without losing important data.

## **System Recovery:**
When windows fails to boot or perform properly, several built in environments can be used to diagnose and repair the system.
1. **Windows Recovery Environment (WinRe):** Access this by repeatedly restarting your PC, using the settings menu, or booting from a dedicatd recovery drive. It feature tools like startup repair for fixing boot issues and system restore for rolling back sysytem settings to a previous, stable state.
2. **System File Checker ((SFC):**
3.  A command-line utility used to scan and restore corrupted windows system files. Run sfc/scannow via the command prompt to resolve missing or broken system components.
4. **Check Disk (chkdsk):**
5.  A tool that scan our hard drive's file system integrity and fixes physical or logical disk errors. Run chkdsk/r to identify and recover bad sectors.

## OD Repair in windows and linux
Operating syatem (OS) repair is the process of identifying and fixing problems that prevent on operting system from functioning correctly. Common issues include corrupted system files, boot failure, malware infections, driver configuration.

### **Common Problems - Windows**
1. System fails to boot
2. Corrupted System files
3. Blue screen of death
4. Missing or damages boot files
5. Driver conflicts

### **Common Problems - LINUX**
1. Bootloader (GRUB) failure
2. Corrupted system files
3. Package dependency issues
4. Kernel problems
5. Incorrect configuration files

### **Windows repair stretegy:**
Employs a progression of tools starting from automated starting automated startup Repair, rolling back changes via system restore, running SFC and DISM commands, checking for drive issues with CHKDSK, and execute a complete system reset or re-installation as a final resort.

### **LINUX repair stretegy:** 
Relies heavily on running fsck to repair system structures, executing terminal utilities for package, repair, restoring the GRUB architecture, or booting into a live USB to manually fix partitions and recover data blacks.

## **Virus/Malware Symptoms:**
1. Slow computer performance.
2. Frequent system crashes or freezes.
3. Unwanted pop-up advertisement.
4. Unkmown programs or files appearing.
5. Browser homepage or search engine changes automatically.
6. High CPU, memory, or disk usage.
7. Antivirus software is disabled unexpectedly.
8. Files become corrupted, missing, or encrypted.
9. Unusual internet or network activity.
10. Unauthorized emails or messages sent from your account.

## **Basic removal steps of virus/malware**
1. Disconnect the computer from innternet to prevent malware from spreading.
2. Restart computer in safe mode.
3. Update antivirus or anti-malware software.
4. Run a full system scan and remove or quarantine all deteted threats.
5. Uninstall suspicious or unknown programs.
6. Delete temporary files to remove malicious temporary data.
7. Update the OS and all software to fix security vulnerabilities.
8. Cjange passwork if you suspect account information has been stolen.
9. Restart the computer and perform another scan to ensure system is clean
10. If infection cannot be removed, restore the system from a backup or reinstall the OS.

## **Driver issues and Device Manager**
### **Common driver issues:**
1. Device not detected by the system.
2. Hardware not workinng properly.
3. Slow or unstable system performance.
4. Blue screen of death (BSOD) in windows.
5. Missing, outdated, or corrupted drivers.
6. Driver compatibility problems after OS updates.
7. Error messages such as "Device Cannot start" or "Driver not installed.

### **Device Manager:**
Device manager is a built in windows utility that allows users to view, manage, and troubleshoot hardware devices and their drivers.
* **How to open Device Manager?**
  1. Press windows + x --> Device Manager
  2. or press windows + R, type devmgmt.msm, and press Enter.
 
* **Features of Device Manager:**
  1. View all installed hardware options.
  2. Identify device and driver problems.
  3. Update device drivers.
  4. Roll back drivers to a previous version.
  5. Enable or disable hardware devices.

## **Disk Errors and Formatting Utilities:**
### **Disk errors:**
Disk errors are the problems that affect the storage device (HHD or SSD) or its file system leading to data corruption, slow performance, or failure to access files.

### **Symptoms of disk errors:**
1. Slow system performance.
2. Files or folder cannot be opened.
3. Frequent folder crashes or freezes.
4. Error message such as "Disk Read Error" or "Device Needs to be repaired".
5. Clicking or unusual noises from a hard disk.

### **Troubleshooting disk errors:**
1. Backup important data immediately.
2. Run a disk check utility.
3.  Scan for viruses and malware.
4.  Check storage cables and connections.
5.  Replace the storage device if it has severe hardware damage.

### **Formatting Utilities:**
Formatting is the process of preparing a storage device for use by creating a file system and removing exixting dara.

### **Types of Formatting:**
1. **Quick format:** Rapidly clears a driver's file tracking index to make the space available, leaving the underlying data intact and potentially recoverable.
2. **Full format:** Completely erases all existing data and check the entire surface for physical bad sectors, making the process slower.

# 4. Network Basics

## **IP Adressing:**
IP adressing is an unique logical address assignes to every device on a network. It works ai OSI layer 3 (Network layer)
* **Usage:** Used to identify devices, send requests, and transfer data across different networks.

## **Subnetting:**
Subnetting is the process of dividing a layer network reange into smaller networks.
* **usage:** Used in schools, offices, colleges, companies, and data centres to manage IP addresses efficiently, reduce traffic, and save address space.

## **Default gateway:** 
The local router interface configured with its own IP address.
* **Usage:** Used as the main dooe for traffic to leave the local netwok and communicate with outside networks like Google or Facebook.

## **MAC address:**
A permanent, unchangable 12-character physical hardware address burned into a device's network interface card.
* **Usage:** Used at the local level (layer 2) to identify exactly who is sending and receiving data with a local network segment.

## **DHCP (Dynamics Host Configuration Protocol):**
DHCP is an automated management provision protocol.
* **Usage:** Used to automatically assign temporary IP addresses, subnet masks, default gateways, and DNS server details to devices when they connect.

## **DNS (DOmain Name System):** 
DNS is the phone book of the global internet.
* **Usage:** Used to translate human-readable text domain names (like google.com) into numeric IP address so devices can locate websites.

## **Types of Cables and Connectors:**
1. **Ethernet cable:** Copper network cable such as Cat56 and Cat6.
   * **usage:** used along RJ-45 connector to link computer directly into LAN.
  
2. **Fiber optic cable:** Long - distance cabling that transmit data packets using light pulses.
   * **Usage:** Used for high bandwidth, long-range connections using specialized LC, SC or ST connector ends.

3. **Coaxial cable:** Shielded copper broadband cables terminating with F type or bayonet BNC chips.
   * **Usage:** Used to transport high - frequency broadband internet signals and traditional cable television feeds.

4. **Telephone cable:** Traditional flat communication lines utilizing small RJ-11 plugs.
   * **Usage:** Used to connect classic analog landline phone devices to wall outlets.

## **Audio & Video Connectors:**
1. **HDMI:** Transfer HD audio and video.
2. **Display port:** Used for high resolution monitoring.
3. **3.5 mm jack:** Used for headphones and microphones.
4. **TOJ link:** Optical digital audio connection.

## **Computer connectors:**
1. **USB:** Types: USB-A, Micro USB, USB-C
2. **Thunderbolt:** High speed data transfer use USB-c connector.
3. **Power cable:** Supply AC powers to computer.
4. **Legacy connectors:** VGA, DVI

## **Crimping and Cable testing:**
* **Crimping:** Crimping is the process of attaching an RJ-45 connector to an ethernet cable.
* **Steps:**
  1. Strio outer insulation.
  2. Untwist wires.
  3. Arrange wires in correct order.
  4. Trim evenly.
  5. Insert the RJ-45 connecot.
  6. Crimp using a crimping tool.
* **T568B Wiring Standard:**
  1. white/orange
  2. orange
  3. white/green
  4. blue
  5. white/blue
  6. green
  7. white/brown
  8. brown

* **Cable Testing:**
  * **Equipment:** LAN cable tester.
  * **Successful test:** LED glows between 1 to 8 in sequence.
  * **Errors:**
    1. **Open circuit:**
       * Broken wire
       * One LED does not glow
    2. **Short circuits:** Two LEDs glow together
    3. **Miswire:** Wring wire sequence
    4. **Split pair:** Connectivity is correct but data transition is poor due to crosstalk.
   
# 5. Network Troubleshooting

## **Diagnosing Connectivity Issues:**
1. **Ping diagnistics:** Mastered the use of ICMP packet requests to end-to-end logical connectivity and measure latency between a local and a remote target.
2. **Traceroute Mapping:** Utilized path-routing diagnostics to map every network hop, allowing precise localization of packet drops or high-latency routers along the transit path.
3. **Interface Configuration:** Employed command-line utilities to inspect network adapters:
   * **`ipconfig` (Windows environments):** To view IPV4/IP6 addresses,, subnet marks, and default gateways.
   * **`ifconfig` (Unix/Linux environments):** To audit activate interface parameters and hardware MAC addresses.

## 
**Resolving IP conflicts and DHCP Errors**
1. **IP conflict Migration:** Developed techinques to detect and isolate duplicate IP address assignments on a local subnet thar causes intermittent device drops and routing errors.
2. **DHCP Troubleshooting:** Analyzed dynamics address allocation failure, specially identifying when a client falls back to an APIPA address (169.254.x)
3. **Lease Renewal:** Practices manuals with release and renewal procedures to force communication with the DHCP server and obtain valid configuration.

## **Basic Router/Switch Configuration & Reset**
1. **Console Navigation:** Gained hands-on experience accessing local management interface for both switches and routers to erview basline running configurations.
2. **Device Reset Procedure:** Learned the proper execution of soft and hard device reset to flush volatile memory, clear comfiguration corruptions and restore hardware defaults during severe freezes

## **Wi-Fi Connectivity issues:**
1. **SSID & authentification:** Diagnose wireless connection issues related to hidden SSIDs, incorrect security protocols, and profile mismatches
2. **Signal strength:** Measured wireless attenuation and localized dead zones across physical infrastructure.
3. **Intererence:** Studied environmental and frequency barriers, learning how to shift channels (eg, managing overlapping channels in the 2.4 GHz or 5 GHz spectrum) to bypass ambient electronic noise.

## **Firewall and Antivirus Blocking Checks**
1. **Access Control Audits:** Evaluated scenarios where physical data - lik layers are fully operational, but application traffic is dropped at the host level.
2. **Rule Inspection:** Conducted systematic checks inside local software firewalls and antivirus security suites to identify over - aggressive security polocies, blocklisted ports, or  false - positive restrictions blocking legimate network traffic.
3. 
  
