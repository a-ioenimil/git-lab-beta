# Documentation of Executed Commands

This document provides a step-by-step explanation of the commands executed for the Git Repository Management Lab, along with their purpose, execution results, and interpretation.

---

## 1. `git config --global --list`

**Documentation:** The `git config` command allows you to view and set Git configuration options.
- `--global`: Targets the configuration file for the current user (applies to all repositories).
- `--list`: Lists all the variables set in the configuration file.

**Purpose:** To verify that the user identity (name and email) is correctly configured before starting work, ensuring commits are attributed correctly.

**Execution Result:** The output confirms the user is set to "Isaac Obo Enimil" and the email is "isaac.enimil@amalitech.com".

**Result:** ![git config output](./assets/images/carbon%20(6).png)

---

## 2. `mkdir git-lab`, `cd git-lab`, `git init`

**Documentation:** This sequence of commands sets up the workspace:
- `mkdir git-lab`: Creates a new directory named `git-lab`.
- `cd git-lab/`: Changes the current working directory into the new folder.
- `git init`: Initializes a new, empty Git repository in the current directory, creating the hidden `.git` folder.

**Purpose:** To create a project folder and transform it into a Git repository ready for version control.

**Execution Result:** Git confirms the initialization of an empty repository.

**Result:** ![git init output](./assets/images/carbon%20(7).png)

---

## 3. `echo "Hello Git" > readme.txt` & `git status`

**Documentation:** - `echo "Hello Git" > readme.txt`: Creates a file named `readme.txt` containing the text "Hello Git".
- `git status`: Displays the state of the working directory and the staging area.

**Purpose:** To create the first file for the project and verify how Git recognizes a new, untracked file.

**Execution Result:** The `git status` command reports `readme.txt` as an **Untracked file**, meaning Git sees it but is not yet managing it.

**Result:** ![git status output](./assets/images/carbon%20(8).png)

---

## 4. `git add readme.txt` & `git commit`

**Documentation:** - `git add readme.txt`: Moves the file from the working directory to the **staging area**.
- `git commit -m "..."`: Saves the staged changes to the local repository with a descriptive message ("Initial commit: Added readme file").

**Purpose:** To permanently record the first version of the project into the repository history.

**Execution Result:** Git confirms the commit with the hash `db8d06a` and notes that 1 file changed.

**Result:** ![git commit output](./assets/images/carbon%20(9).png)

---

## 5. `git branch feature-update` & `git checkout feature-update`

**Documentation:** - `git branch feature-update`: Creates a new branch pointer named `feature-update` at the current commit.
- `git checkout feature-update`: Switches the active working branch to `feature-update`.

**Purpose:** To create an isolated environment for developing a new feature without affecting the `main` branch.

**Execution Result:** The console output "Switched to branch 'feature-update'" confirms the active branch has changed.

**Result:** ![git branch checkout output](./assets/images/carbon%20(10).png)

---

## 6. Feature Implementation & Commit

**Documentation:** Commands executed:
- `echo "New feature added!" >> readme.txt`: Appends new text to the existing file.
- `git add readme.txt`: Stages the modified file.
- `git commit -m "Updated readme with new feature text"`: Commits the changes to the `feature-update` branch.

**Purpose:** To simulate working on a feature and saving that progress on a separate branch.

**Execution Result:** A new commit `3151519` is created on the feature branch.

**Result:** ![feature commit output](./assets/images/carbon%20(11).png)

---

## 7. `git checkout main` & `git merge feature-update`

**Documentation:** - `git checkout main`: Switches back to the primary branch.
- `git merge feature-update`: Integrates the history of the feature branch into the current branch (`main`).

**Purpose:** To bring the completed feature work back into the main project.

**Execution Result:** Git performs a **Fast-forward** merge, updating `readme.txt` in the `main` branch to match the feature branch.

**Result:** ![git merge output](./assets/images/carbon%20(12).png)

---

## 8. `git remote add` & `git push`

**Documentation:** - `git remote add origin ...`: Links the local repository to a remote GitHub repository.
- `git push -u origin main`: Uploads the local `main` branch to the `origin` remote and sets the upstream tracking.

**Purpose:** To back up the local work to GitHub and make it available for collaboration.

**Execution Result:** The output confirms the objects were compressed and written to GitHub, and the local `main` branch is set up to track `origin/main`.

**Result:** ![git push output](./assets/images/carbon%20(13).png)

---

## 9. `git log --oneline --graph`

**Documentation:** - `git log`: Shows the commit logs.
- `--oneline`: Condenses each commit to a single line.
- `--graph`: Draws a text-based graphical representation of the commit history on the left side.

**Purpose:** To visualize the project history and confirm that the merge operation resulted in a linear history (due to the fast-forward merge).

**Execution Result:** The log displays the two commits (`3151519` and `db8d06a`) and shows that `HEAD`, `main`, `origin/main`, and `feature-update` are all pointing to the latest work.

**Result:** ![git log output](./assets/images/carbon%20(14).png)

---

*End of Documentation*