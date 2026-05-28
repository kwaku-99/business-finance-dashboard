# Setup Journal — Business Finance Dashboard

## Project Goal

We are building a Business Finance Dashboard project from scratch as:

1. a serious learning experience
2. a scalable product prototype that could evolve into a real monetizable app

The project will help student entrepreneurs, freelancers, and small businesses:

* track revenue
* monitor expenses
* calculate profit
* visualize financial analytics
* gain business insights

The project is being built collaboratively using GitHub and modern software engineering workflows.

---

# Initial Development Environment

## Tools Being Used

| Tool       | Purpose                           |
| ---------- | --------------------------------- |
| VS Code    | Code editor/workspace             |
| PowerShell | Terminal/CLI                      |
| Python     | Programming language              |
| Git/GitHub | Collaboration and version control |
| Streamlit  | Dashboard framework (later)       |

---

# Important Concepts Learned

## 1. Terminal vs Python

A major realization early on was that:

* terminal commands are NOT Python code
* Python code goes inside `.py` files
* terminal commands control the operating system and project environment

Examples:

### Terminal Commands

```powershell
mkdir
cd
New-Item
code
```

### Python Code

```python
print("Hello")
```

---

# Project Folder Creation

## Command Used

```powershell
mkdir business-finance-dashboard
```

## Meaning

`mkdir` means:

> make directory

This created the main project folder.

---

# Navigating Into the Project

## Command Used

```powershell
cd business-finance-dashboard
```

## Meaning

`cd` means:

> change directory

This moved the terminal into the project folder.

Important realization:

* terminal location matters
* files/folders get created inside the current working directory

---

# Folder Structure Creation

Initially attempted:

```powershell
mkdir data src docs notebooks
```

## Error Encountered

```text
A positional parameter cannot be found that accepts argument 'src'
```

## Cause

PowerShell behaves differently from Bash/Linux terminals.

Creating multiple folders in one `mkdir` command works in Bash but not in this PowerShell environment.

## Solution

Created folders one-by-one:

```powershell
mkdir data
mkdir src
mkdir docs
mkdir notebooks
```

---

# Purpose of Each Folder

| Folder       | Purpose                                  |
| ------------ | ---------------------------------------- |
| `data/`      | stores datasets and CSV files            |
| `src/`       | stores source code and application logic |
| `docs/`      | stores documentation and project notes   |
| `notebooks/` | stores Jupyter notebooks and experiments |

---

# Understanding the VS Code Workspace

A key realization:

* terminal navigation and VS Code workspace are related but separate

Even after using:

```powershell
cd business-finance-dashboard
```

VS Code still needed:

```text
File → Open Folder
```

to officially recognize the project workspace.

Once opened properly:

* the sidebar displayed the project structure
* VS Code became connected to the project

---

# Moving the Project Folder

The project was initially created under:

```text
C:\Users\USER\
```

Goal:
Move it into:

```text
Documents/TBP/
```

## Command Attempted

```powershell
Move-Item business-finance-dashboard Documents\TBP\
```

## Error Encountered

```text
The process cannot access the file because it is being used by another process.
```

## Cause

VS Code had the folder open and locked.

## Solution

Closed VS Code completely, then reran:

```powershell
Move-Item business-finance-dashboard Documents\TBP\
```

After moving:

* reopened the project
* learned how programs can lock files/folders during active use

---

# Opening VS Code Through CLI

Learned that projects and files can be opened directly through terminal.

## Open Current Folder

```powershell
code .
```

Meaning:

> open the current folder in VS Code

The dot (`.`) represents:

> current directory

---

# File Creation Through CLI

## README.md Creation

Command used:

```powershell
New-Item README.md
```

Also learned:

```powershell
ni
```

is shorthand for:

```powershell
New-Item
```

Important realization:

* files created in terminal automatically appear in VS Code
* VS Code and terminal synchronize through the filesystem

---

# Markdown Basics

Learned that:

```text
.md
```

means:

> Markdown file

Markdown is used for:

* documentation
* project descriptions
* GitHub READMEs

First README content written:

```md
# Business Finance Dashboard

A finance analytics dashboard for student entrepreneurs, freelancers, and small businesses.
```

Learned:

* `#` creates a large heading
* Markdown is not Python
* GitHub renders Markdown beautifully

---

# Creating Python Files

## app.py Creation

Command used:

```powershell
ni app.py
```

## Opening File Through CLI

```powershell
code app.py
```

Important realization:

* `.py` indicates a Python source code file
* VS Code recognizes file types automatically
* syntax highlighting changes depending on extension

---

# Key Engineering Concepts Learned So Far

## Filesystem

Files and folders exist independently of VS Code.

## Current Working Directory

Terminal commands execute relative to the current folder.

## Workspace

VS Code uses a project workspace to manage files and tools.

## File Extensions

Extensions tell tools how files should be interpreted.

Examples:

| Extension | Meaning                |
| --------- | ---------------------- |
| `.py`     | Python source code     |
| `.md`     | Markdown documentation |
| `.csv`    | tabular data           |
| `.txt`    | plain text             |

## CLI Workflow

The terminal can:

* create folders
* create files
* move projects
* open VS Code
* navigate directories

This is often faster and more scalable than GUI workflows.

---

# Current Project Structure

```text
business-finance-dashboard/

├── data/
├── docs/
├── notebooks/
├── src/
├── README.md
├── app.py
```

---

# Current Understanding

At this stage, the following concepts are now understood:

* terminal basics
* PowerShell basics
* filesystem structure
* directory navigation
* project organization
* VS Code workspaces
* Markdown basics
* Python file structure
* CLI workflows
* file extensions
* synchronization between terminal and VS Code

This setup phase established the foundation for the actual application development phase.

# Git, GitHub, and Virtual Environment Setup

## Git Initialization

Initialized Git repository inside the project folder.

Command used:

```powershell
git init
```

Learned:

* Git tracks project history and file changes.
* A Git repository stores snapshots (commits) of project progress.
* This allows collaboration, rollback, and version control.

---

# Git Status

Checked repository status.

Command used:

```powershell
git status
```

Learned:

* Git shows file states:

  * `U` = Untracked
  * `A` = Added/Staged
  * `M` = Modified
* Git does not automatically track files.
* Files must first be added before committing.

---

# Staging Files

Added project files to Git staging area.

Command used:

```powershell
git add .
```

Learned:

* `git add .` stages all current project files.
* Staging prepares files for commit.
* Git now begins tracking these files.

---

# First Commit

Created first project snapshot.

Command used:

```powershell
git commit -m "Initial project setup"
```

Learned:

* Commits are save points/checkpoints in project history.
* Commit messages should clearly describe meaningful progress.
* Professional developers commit after stable progress.

---

# GitHub Repository Creation

Created remote GitHub repository called:

```text
business-finance-dashboard
```

Repository was created without:

* README
* .gitignore
* license

because these already existed locally.

Learned:

* Local repository and remote GitHub repository are separate initially.
* GitHub acts as cloud storage + collaboration platform.

---

# Connecting Local Repo to GitHub

Connected local Git repository to remote GitHub repository.

Command used:

```powershell
git remote add origin https://github.com/USERNAME/business-finance-dashboard.git
```

Learned:

* `origin` is the nickname for the remote GitHub repository.
* `.git` is part of GitHub repository URLs.
* Remote repositories allow collaboration and cloud syncing.

---

# First Push to GitHub

Uploaded local project to GitHub.

Command used:

```powershell
git push -u origin main
```

Learned:

* `push` uploads commits to GitHub.
* `main` is the main branch.
* `-u` links local branch to remote branch for future pushes.

After successful push:

* GitHub repository updated successfully.
* Collaborators could now access the project.

---

# Adding Collaborators

Added teammates as collaborators on GitHub.

Learned:

* Collaborators can clone the repository to their laptops.
* Team members can contribute code from different locations.
* GitHub enables distributed software development.

---

# Virtual Environment Setup

Created isolated Python environment for the project.

Command used:

```powershell
python -m venv .venv
```

Learned:

* Virtual environments isolate project dependencies.
* Each project can have its own packages and versions.
* Prevents conflicts between projects.
* `.venv` is the standard naming convention.

---

# Understanding `.venv`

Inside `.venv` appeared:

* Include/
* Lib/
* Scripts/
* pyvenv.cfg

Learned:

* `.venv` contains a mini isolated Python installation.
* Python automatically manages most internal files.
* This folder should NOT be uploaded to GitHub.

---

# Why `.venv` is in `.gitignore`

Learned:

* `.venv` can become extremely large.
* It contains machine-specific files.
* Each teammate generates their own `.venv`.
* Only dependency lists should be shared.

---

# Virtual Environment Activation

Activated virtual environment.

Command used:

```powershell
.venv\Scripts\activate
```

Initial error encountered:

```text
running scripts is disabled on this system
```

Reason:

* PowerShell execution policy blocked script execution.

Fix used:

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

Then typed:

```text
Y
```

Activation succeeded afterward.

Terminal changed to:

```text
(.venv)
```

Learned:

* Activation switches terminal into project-specific Python environment.
* Package installations now happen INSIDE `.venv`.
* This is standard professional Python workflow.

---

# Installing Packages

Installed first package: pandas.

Command used:

```powershell
pip install pandas
```

Learned:

* `pip` is Python’s package manager.
* Installing pandas also installed dependencies:

  * numpy
  * python-dateutil
  * tzdata
  * six
* Software packages often depend on other packages.

---

# Requirements File

Saved installed dependencies into requirements.txt.

Command used:

```powershell
pip freeze > requirements.txt
```

Learned:

* `pip freeze` lists installed packages and versions.
* `>` redirects terminal output into a file.
* `requirements.txt` acts as the dependency recipe for the project.
* Teammates can recreate the same environment using:

```powershell
pip install -r requirements.txt
```

This is critical for collaboration and reproducibility.

---

# Current Understanding

The project now has:

* professional folder structure
* Git version control
* GitHub collaboration
* virtual environment isolation
* dependency management
* reproducible setup workflow
* project history tracking

This setup reflects real-world software engineering workflow.
