# Module 4: Introduction to GIT and Version Control

##  What is GIT and why use version control?

### Git
Git is a distributed version control system (DVCS) that tracks changes in source code during software development. It allows developers to collaborate efficiently, maintain a history of changes, and revert to previous versions of a project if needed.

### Version Control
Version control is a system that records changes to a file or set of files over time, allowing developers to recall specific versions later.

### Why use version control?
*   **Version history:** Tracks all changes with the ability to revert to any previous state.
*   **Collaboration:** Allows multiple people to work simultaneously without overwriting work.
*   **Safe environment:** Uses branches to test new ideas without affecting the main project.

---

##  GIT Architecture
GIT manages code through three distinct areas that defines its workflow:

*   **Working Tree:** Your current workspace where you create, edit, and delete files.
*   **Index (Staging Area):** A "Prep Zone" where you list the specific changes you want to include in your next snapshot.
*   **Repository:** The permanent storage where Git saves your project history and commit snapshots.

> **Workflow Summary:** Modify files in the Working Tree → Stage them in Index → Commit to the Repository.

---

##  Core Git Operations

*   **git init:** Creates a hidden `.git` folder in your directory to track project history. It turns any standard folder into a Git-managed repository.
*   **add:** Add modified files from the working directory to the staging area.
*   **commit:** Captures a snapshot of the staged changes and save them permanently in local repository. Every commit requires a descriptive message.
*   **status:** Displays the state of working directory and the staging area (modified files, untracked files or files ready to commit).
*   **log:** Provides a chronological history of all commits made within the repository.

---

##  Branching and Merging

*   **Branching:** Creates an independent line of development. This allows developers to work on new features or bug fixes without affecting the stable "Main" or "Master" codebase.
*   **Merging:** The process of integrating changes from a feature branch back into the main branch once the work is verified and complete.

---

##  Remote Operations

*   **Push:** Uploads your local commits to a remote repository.
*   **Pull:** Fetches changes from a remote and merges them into your current branch.
*   **Remote:** Manages the list of connections to remote repositories.

---

##  GitHub / GitLab Basics

### GitHub
Known as the "social network for code". It is the most popular for beginners and open-source projects. It excels in speed, simplicity, and community integration, offering a massive marketplace of third-party tools (like GitHub Actions) to extend its functionality.

### GitLab
Often described as an "all-in-one" DevOps platform, it comes with built-in tools for CI/CD, project management, and security, reducing the need for external services. It is highly favored by teams that requires a structured, reliable, and centralized environment for complex and or regulated projects.
