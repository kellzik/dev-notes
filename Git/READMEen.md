# Git Commands Cheat Sheet

A comprehensive quick-reference guide covering essential Git commands for everyday version control, repository management, and collaboration.

## Confugration & Setup
Commands for configuring user settings, system defaults, global aliases, and initializing new Git repositories.

| Command | Description |
| :--- | :--- |
| `git config --global user.name "[name]"` | Sets the author name to be used with your commits. |
| `git config --global user.email "[email]"` | Sets the author email address to be used with your commits. |
| `git config --list` | Displays all current, global and local Git configuration settings. |
| `git clone [url]` | Downloads an existing remote repository onto your local machine. |
| `git --version` | Display the main help documentation, showing a list of commonly used Git commands. |
| `git help` | Display the main help documentation, showing a list of commonly used Git commands. |
| `git help [command]` | Opens the manual page for the specified command (example: `git help commit`). |

## Repository Inspection & Status

Commands used to inspect the current state of your working directory, check file modifications, and review commit history.

| Command | Description |
| :--- | :--- |
| `git remote -v` | Displays the associated remote repositories and their stored name, like `origin`. |
| `git status` | Displays the state of the working directory and staging area (shows modified, staged, or untracked files). |
| `git log` | Shows the commit history for the currently active branch. |
| `git log --oneline` | Displays commit information in one line. |
| `git show [commit-hash]` | Shows the metadata and content changes of a specific commit. |

## Staging & Committing

The core workflow commands for tracking changes, staging files, and committing them to your local repository history.

## Branching & Merging

Commands for isolating feature development, switching between contexts, and integrating different history streams together.

## Synchronizing & Remote Repositories

Commands for interacting with remote repositories (like GitHub or GitLab) to download updates or share your local commits.


## Undoing Changes & History Rewriting

Commands for fixing errors, reverting commits, resetting local state, and temporarily shelving uncommitted work.