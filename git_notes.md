# 1. Introduction to Git

Git is a Distributed Version Control System (DVCS) used to track changes in source code, documents, and other files during software development. It allows multiple developers to work on the same project simultaneously without overwriting each other's work.

## Why Git is Used
- Tracks file changes over time
- Enables collaboration among developers
- Allows reverting to previous versions
- Supports branching and merging
- Maintains project history
- Works offline

# 2. Version Control System (VCS)

A Version Control System manages modifications to files and records every change.

## Types of VCS

## A) Local VCS

Stores revisions on a local computer.

### Example:

- RCS

### Advantages
- Simple
- Fast

### Disadvantages
- No collaboration
- Risk of losing data

## B) Centralized VCS (CVCS)

Uses a central server to store all versions.

### Examples:

- SVN
- CVS

### Advantages
- Easy collaboration
- Central backup

### Disadvantages
- Server failure affects everyone
- Requires internet access

## C) Distributed VCS (DVCS)

Each user has a complete copy of the repository.

### Examples:

- Git
- Mercurial

### Advantages
- Offline work possible
- Faster operations
- Better security

### Disadvantages
- Slightly more complex

# 3. Git Architecture

Git consists of three major areas.

## Working Directory-
The folder where files are created and edited.

### Example

Project Folder
│
├── index.html
├── style.css
└── script.js

## Staging Area
Temporary area where selected changes are stored before committing.
Also known as:
- Index
- Repository
Stores committed snapshots permanently.

### Two types:

- Local Repository
Present on the user's computer.

- Remote Repository
Stored on platforms like GitHub.

# 4. Installing Git

## Windows
Download Git from the official website.

### Verify installation

- git --version

### Example output
git version 2.50.1

## Linux
### Ubuntu
- sudo apt update
- sudo apt install git

### MacOS
- brew install git

# 5. Git Configuration
Git stores user information.

### Configure username
- git config --global user.name "John Doe"
### Configure email
- git config --global user.email "john@example.com"
### Check configuration
- git config --list

# 6. Creating a Repository

### Move into project folder
- cd project

### Initialize Git
- git init

### Output
- Initialized empty Git repository

# 7. Git File States
Git files pass through five states.

1. Untracked
Git does not know about the file.

Example- notes.txt

2. Tracked
Git tracks changes.

3. Modified
File contents changed.

4. Staged
Changes added to staging area.

5. Committed
Changes saved permanently.

## Flow Diagram

Untracked
    │
git add
    │
    ▼

Staged
    │
git commit
    │
    ▼

Committed

# 8. Checking Repository Status
- git status

### Example
- On branch main
- Changes not staged for commit
- new file: notes.txt

# 9. Adding Files
### Add single file
- git add file.txt

### Add multiple files
- git add file1.txt file2.txt

### Add all files
- git add .

# 10. Commit
A commit is a snapshot of the project.

### Create commit
- git commit -m "Added Git notes"

### Skip staging
- git commit -am "Updated notes"
(Only works for already tracked files.)

# 11. Viewing Commit History
### Show commits
- git log

### One line format
- git log --oneline

### Example

- 3298062 Added README
- 43ab91d Updated notes

### Graph format
- git log --oneline --graph

# 12. Difference Between Files

### Compare modified file
- git diff

### Compare staged changes
- git diff --staged

# 13. Ignoring Files
## Create
- .gitignore

- Example

*.log

node_modules/

.env

__pycache__/

# 14. Branching
Branches allow independent development.

### List branches
- git branch

### Create branch
- git branch feature-login

### Switch branch
- git checkout feature-login

### Create and switch
- git checkout -b feature-login

### Modern command
- git switch feature-login

### Create and switch
- git switch -c feature-login

### Delete branch
- git branch -d feature-login

# 15. Merging Branches

### Switch to main
- git switch main

### Merge
- git merge feature-login

Fast-forward merge occurs when no divergence exists.

# 16. Merge Conflicts

## Conflict example

### Branch A

- Hello World

### Branch B

- Hello Git

### Conflict markers

<<<<<<< HEAD

Hello World

=======

Hello Git

>>>>>>> feature

Resolve manually.


Then

- git add .
- git commit

# 17. Rebase
Moves commits to another base.

- git rebase main

## Advantages

- Cleaner history
- Linear commits

## Disadvantages

- Can rewrite history

# 18. Stashing
Temporarily saves changes.

### Save changes
- git stash

### List stashes
- git stash list

### Apply stash
- git stash apply

### Delete stash
- git stash drop

# 19. Tags
Used for versions.

### Create tag
- git tag v1.0

### Annotated tag
- git tag -a v1.0 -m "Version 1"

### View tags
- git tag

### Push tags
- git push origin --tags

# 20. Undoing Changes

### Discard modifications
- git restore file.txt

### Unstage file
- git restore --staged file.txt

### Remove last commit
- git reset --soft HEAD~1

### Delete commit permanently
git reset --hard HEAD~1

# 21. Remote Repositories
### View remotes
- git remote -v

### Add remote
- git remote add origin https://github.com/user/project.git

### Remove remote
- git remote remove origin

# 22. GitHub Workflow
### Clone repository
- git clone https://github.com/user/project.git

### Push changes
- git push origin main

### Pull changes
- git pull origin main

### Fetch changes
- git fetch origin

# 23. Pull Requests

Steps:

1. Create branch
- git switch -c feature-ui

2. Commit changes
- git add .
- git commit -m "Added UI"

3. Push branch
- git push origin feature-ui
4. Open GitHub
5. Click Compare & Pull Request
6. Review changes
7. Merge Pull Request

# 24. Forking
Forking creates a copy of another repository.

### Workflow

Original Repository

        ↓

Fork

        ↓

Clone

        ↓

Modify

        ↓

Commit

        ↓

Push

        ↓

Pull Request

# 25. Git Aliases

### Create shortcut
- git config --global alias.st status
- Use- git st

### Example aliases

- git config --global alias.co checkout
- git config --global alias.br branch
- git config --global alias.cm commit
- git config --global alias.lg "log --oneline --graph"
