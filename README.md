#   Git Cheat Sheet - README

This document contains a compilation of essential Git commands for quick reference, extracted from the provided "git-cheat-sheet-education.pdf".

##   Installation & GUIs

Git is a free and open-source distributed version control system. GitHub provides platform-specific installers for Git and a graphical user interface for easier interaction. [cite: 1, 2, 3, 4, 5]

* **GitHub for Windows:** https://windows.github.com [cite: 4]
* **GitHub for Mac:** https://mac.github.com [cite: 4]
* **Git for All Platforms (Linux and Solaris):** http://git-scm.com [cite: 5]

##   Setup

Configuring user information for local repositories:

```bash
git config --global user.name "[firstname lastname]" # Sets the name for credit when reviewing version history.
git config --global user.email "[valid-email]" # Sets the email address associated with each history marker.
git config --global color.ui auto # Enables automatic command line coloring for Git.

git init # Initializes an existing directory as a Git repository.
git clone [url] # Retrieves an entire repository from a hosted location via URL.

git status # Show modified files in working directory, staged for your next commit
git add [file] # Stages the file for the next commit.
git add . # Stages all changes in the working directory.
git reset [file] # Unstages the file but preserves its contents.
git reset .  # Unstages all staged files but preserves their contents.
git reset --hard # Unstages all changes and discards the working directory.
git diff # diff of what is changed but not staged
git diff-staged # diff of what is staged but not yet committed
git commit -m "[descriptive message]" # Commits staged files with a descriptive message.


git branch # Lists all local branches in the current repository.
git branch [branch-name] # create a new branch at the current commit
git checkout [branch] # Switches to the specified branch.
git checkout -b [new-branch] # Creates a new branch and switches to it.
git merge [branch] # Merges the specified branch's history into the current one
git branch -d [branch] # Deletes the specified branch.
git log # show all commits in the current branch's history


git log # Shows commit history, branch points, and more.
git log --follow [file] # Shows commit history for a specific file, even across renames.
git diff [branch1] [branch2] # Shows content differences between two branches.
git show [commit] # Shows metadata and content changes of the specified commit.
git log branchB..branchA # show the commits on branchA that are not on branchB
git diff branchB...branchA # show the diff of what is in branchA that is not in branchB

git rm [file] # delete the file from project and stage the removal for commit
git mv [existing-path] [new-path] # change an existing file path and stage the move
git log--stat -M # show all commit logs with indication of any paths that moved
echo [pattern] >> .gitignore # Adds a pattern to ignore specific files and directories.
git config --global core.excludesfile [file] # Sets a system-wide ignore pattern for all local repositories.


git remote add [alias] [url] # Adds a Git URL as an alias.
git fetch [alias] # Downloads all branches from the remote repository.
git merge [alias]/[branch] # Merges a remote branch into the current branch.
git push [alias] [branch] # Transmits local branch commits to the remote repository branch.
git pull # Fetches and merges commits from the tracking remote branch.

git rebase [branch] # Applies commits of the current branch ahead of the specified one.
git reset --hard [commit] # Clears the staging area and rewrites the working tree from the specified commit. 



git stash # Saves modified and staged changes.
git stash list # Lists the stack order of stashed file changes.
git stash pop # Applies the changes from the top of the stash stack.
git stash drop # Discards the changes from the top of the stash stack.
