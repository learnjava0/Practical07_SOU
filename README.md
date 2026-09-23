# Practical07_SOU


Git Essentials: Command Reference Guide

This reference guide details the 10 fundamental Git commands required for version control and GitHub collaboration, complete with detailed explanations, usage syntax, common flags, and workflow best practices.

1. Local Repository Setup

git init

Initializes a brand-new, empty Git repository in your current working directory. It creates a hidden .git folder containing all version tracking metadata.

When to use: Starting a new project from scratch on your local machine.

# Initialize a repository in the current directory
git init

# Initialize a repository in a specific directory
git init <project-name>


git clone

Copies an existing repository—along with its entire commit history, branches, and tags—from a remote source (like GitHub) to your local machine.

When to use: Joining an existing project or downloading code from GitHub.

# Clone a repository using HTTPS
git clone https://github.com/username/repository.git

# Clone into a specific local folder name
git clone https://github.com/username/repository.git custom-folder-name


2. Tracking & Staging Changes

git status

Displays the current state of your working directory and staging area. It highlights modified files, untracked files, and files prepared for the next commit.

When to use: Regularly throughout your development process to verify what changes have been made.

# Display detailed status
git status

# Display status in a concise format
git status -s


git add

Adds modified or newly created files from the working directory to the staging area (index), preparing them to be included in the next commit.

When to use: After creating or editing files that you want to commit.

# Stage a specific file
git add filename.ext

# Stage all modified and new files in the current directory
git add .

# Stage files interactively (chunk by chunk)
git add -p


3. Saving & Synchronization

git commit -m "message"

Saves a snapshot of the staged changes to the local repository history. The -m flag allows you to attach a concise, descriptive message summarizing the modifications.

When to use: After reaching a logical milestone or completing a task.

# Commit staged changes with a descriptive message
git commit -m "Add user authentication feature"

# Stage all tracked modified files and commit in one command
git commit -am "Fix mobile responsiveness on landing page"


git push

Uploads your local branch commits to a remote repository (e.g., GitHub), making your updates available to collaborators.

When to use: After committing changes locally and ready to share or back them up remotely.

# Push local commits to the main branch on the remote server
git push origin main

# Set default upstream branch during your initial push
git push -u origin <branch-name>


git pull

Fetches the latest commits from the remote repository and automatically merges them into your active local branch.

When to use: Before starting new work or pushing local changes to ensure you have the latest updates.

# Fetch and merge changes from the remote main branch
git pull origin main


Note: git pull is essentially a combination of git fetch (downloading remote updates) and git merge (applying them to your local branch).

4. Branching & Merging

git branch

Manages branches in your repository. Branches allow you to isolate development work without affecting the main codebase.

When to use: To list existing branches, create new feature branches, or delete obsolete branches.

# List all local branches (active branch is marked with *)
git branch

# Create a new branch (does not switch to it automatically)
git branch <branch-name>

# Delete a branch locally (safe delete)
git branch -d <branch-name>

# Force-delete an unmerged branch
git branch -D <branch-name>


git checkout

Switches your working environment between different branches or restores working tree files.

When to use: Moving to another branch to work on a different feature.

# Switch to an existing branch
git checkout <branch-name>

# Create a new branch AND switch to it immediately
git checkout -b <new-branch-name>


Modern Alternative: In Git 2.23+, git switch <branch-name> can be used to switch branches, and git switch -c <new-branch-name> to create and switch.

git merge

Integrates the commit history and changes from a specified branch into your currently active branch.

When to use: Combining completed feature branch work back into the main branch.

# Step 1: Switch to the receiving branch (e.g., main)
git checkout main

# Step 2: Merge the feature branch into main
git merge feature-branch


5. Typical Daily Git Workflow

Pull Latest Changes:

git pull origin main


Create a Feature Branch:

git checkout -b feature/login-page


Make Changes, Stage, and Commit:

git status
git add .
git commit -m "Implement login form layout and validation"


Push Changes to Remote:

git push -u origin feature/login-page
