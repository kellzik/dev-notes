# Git Commands Cheat Sheet

This page covers essential Git commands for everyday version control, repository management, and collaboration.

## Basic Setup & Information
Commands for configuring Git environment, cloning repository, checking version details, and getting help."

| Command | Description |
| :--- | :--- |
| `git config --global user.name "[name]"` | Sets the author name to be used with your commits. |
| `git config --global user.email "[email]"` | Sets the author email address to be used with your commits. |
| `git config --list` | Displays all the configuration settings for Git that are currently in effect. |
| `git clone [url]` | Downloads an existing remote repository (from GitHub) onto your local machine. |
| `git --version` | Displays the current version of Git installed on your system. |
| `git update-git-for-windows` | Updates Git on Windows. |
| `git help` | Displays the main help documentation, showing a list of commonly used Git commands. |
| `git help --all` | Displays a list of all Git commands, grouped by category. |
| `git help [command]` | Opens the manual page for a specific Git command. <br /> *Example:* `git help commit` |

## Repository Inspection & Status

Commands used to inspect the current state of your working directory, check file modifications, and review commit history.

| Command | Description |
| :--- | :--- |
| `git remote -v` | Displays existing remote repositories and the URLs associated with each remote. |
| `git remote show [remote]` | Show detailed information about a specific remote. <br /> *Example:* `git remote show origin` |
| `git status` | Checks the current state of the repository. |
| `git status -s` | Displays `status` command output in a short format. |
| `git log` | Displays the commit history of a Git repository. |
| `git log --oneline` | Displays commit information in one line (with shortened commit hashes). |
| `git diff --staged` | Shows what changes are staged for the next commit. |
| `git diff [local-branch] [remote-branch]` | Compares the changes between your local branch and the remote branch. <br /> *Example:* `git diff main origin/main` |
| `git show` | Shows the details of the most recent commit. |
| `git show [commit-hash]` | Shows the details of a specific commit by its hash. |

## File Manipulation, Staging & Committing

The core workflow commands for staging files, and committing them to your local repository history.

| Command | Description |
| :--- | :--- |
| `git add [file]` | Adds file changes to the staging area (index) for the next commit. <br /> *Example:* `git add FunCode.py` |
| `git add .` | Stages all new, modified, and deleted files in the current directory tree. |
| `git rm [file]` | Removes specified files from the working directory and stages the deletion for the next commit. <br /> *Example:* `git rm FunCode.py` |
| `git rm --cached [file]` | Tells Git to forget about a file without deleting it. |
| `git mv [old-file] [new-file]` | Renames a file, and automatically stages the change for the next commit. <br /> *Example:* `git mv FunCode.py MostFunnyCode.py` |
| `git mv [file] [new-directory]/[file]` | Moves a file into a new directory, and automatically stages the change for the next commit. <br /> *Example:* `git mv MostFunnyCode.py scripts/MostFunnyCode.py` |
| `git mv [old-directory]/[old-file] [new-directory]/[new-file]` | Renames and moves a file in a single step, and automatically stages the change for the next commit. <br /> *Example:* `git mv temp/FunCode.py scripts/MostFunnyCode.py` |
| `git mv [old-directory]/ [new-directory]/` | Renames a directory, and automatically stages the change for the next commit. <br /> *Example:* `git mv spring2026/ autumn2026/` |
| `git commit -m "[message]"` | Records staged snapshots permanently in the version history with a descriptive log message. |
| `git commit --amend` | Modifies the most recent commit (useful for updating the commit message or adding forgotten changes). |

## Branching & Merging

Commands for isolating feature development, switching between contexts, and integrating different history streams together.

| Command | Description |
| :--- | :--- |
| `git branch` | Lists all local branches in the current repository. |
| `git branch [branch]` | Creates a new branch (but don't switch to it). <br /> *Example:* `git branch new-feature` |
| `git branch -d [branch]` | Deletes a branch. <br /> *Example:* `git branch -d new-feature` |
| `git switch [branch]` | Switches to an existing branch (modern replacement for `git checkout`). <br /> *Example:* `git switch new-feature` |
| `git switch -c [branch]` | Creates a new branch and switches to it right away.|
| `git merge [branch]` | Combines the specified branch's changes into the currently active branch. <br /> *Example:* `git merge origin/main` |
| `git branch -d [branch]` | Deletes the specified local branch safely. |

## Synchronizing & Remote Repositories

Commands for interacting with remote repositories (like GitHub) to download updates or share your local commits.

| Command | Description |
| :--- | :--- |
| `git fetch` | Downloads the latest changes from a remote repository to local machine but doesn't automatically merge or modify current working files. |
| `git fetch [remote-repository]` | Downloads changes from a specific remote repository. <br /> *Example:* `git fetch upstream` |
| `git fetch --all` | Downloads changes from all remote repositories.|
| `git pull` | Integrates changes from a remote repository into the current branch. |
| `git push origin [branch]` | Transfers commits from your local repository to the specified remote repository. <br /> *Example:* `git push origin main` |

## Undoing Changes & History Rewriting

Commands for fixing errors, reverting commits, resetting local state, and temporarily shelving uncommitted work.

| Command | Description |
| :--- | :--- |
| `git restore [file]` | Discards local unstaged changes in the working directory to match the last commit. |
| `git restore --staged [file]` | Removes all changes from the staging area but leaves the working directory files as they were. <br /> *Example:* `git restore --staged FunCode.py` |
| `git revert [commit-hash]` | Undoes the changes from the specific commit while preserving the project's history (created a new commit that does the exact opposite). <br /> *Example:* `git revert a1b2c3d` |

## More Tips & Tricks

### Pulling with `rebase` 
Take the latest changes from the remote branch and put all of your recent commits on top of it. This can be achieved with 
`git pull --rebase`. But adding that option every time is tedious, so you can set rebase as the default behavior for git pull: `git config pull.rebase true`

### Solving `revert` Conflicts
Reverting may cause conflicts if later commits touched the same code. If a conflict occurs, Git pauses:
1. Resolve conflicts manually in the affected files.
2. Stage them with `git add .`
3. Run `git revert --continue` to finish (or git `revert --abort` to cancel).

`git revert` safely corrects history without altering past commits, making it ideal for collaborative projects.


