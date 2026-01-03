## Git Basics – Day 1

### Commands Practiced
- git status
- git add
- git commit
- git diff
- git log

### Key Learnings
- Git tracks file changes, not folders
- Staging area exists between working directory and repository
- Each commit is a snapshot

### Interview Notes
- git add moves changes to staging
- git diff shows unstaged changes

## Git Branching – Day 2

### Commands Used
- git branch
- git switch
- git merge
- git log --graph

### Key Learnings
- Branches are pointers, not copies
- Fast-forward merges don’t create new commits
- Merge commits appear when history diverges

### Interview Notes
- Teams isolate work using branches
- Merge strategy depends on team workflow

# Git Branching, Merging & Conflict Resolution - Day 3 

## Objective
Understand how Git handles branching, merging, and merge conflicts, and learn how to resolve conflicts manually like in real-world projects.

---

## Topics Covered

### 1. Git Branching
- Created multiple branches (`feature-A`, `feature-B`)
- Understood how branches allow parallel development
- Learned how branches diverge from a common base commit

---

### 2. Fast-Forward vs Merge Commit

#### Fast-Forward Merge
- Happens when the target branch has **no new commits**
- Git simply moves the branch pointer forward
- No merge commit is created

# Git Remote Repositories (GitHub) - Day 4

## 📌 Objective
Learn how to connect a local Git repository to GitHub and sync code using remote commands.

---

## 🧠 Topics Covered

### 1. git remote
- View remote repositories
- Add a remote repository
```
git remote
git remote -v
git remote add origin <repository-url>
```
---

### 2. git clone
Clone an existing GitHub repository
```
git clone <repository-url>
```
---
### 3. git push
Push local commits to GitHub
```
git push -u origin main
git push
```
---
### 4. git pull
Fetch and merge changes from remote
```
git pull origin main
```
---
### 5. git fetch
Download remote changes without merging
```
git fetch origin
git branch -r
git diff origin/main
```
---

Git Undoing Changes – Reset, Revert & Restore – Day 4

Objective  
Understand how to undo changes safely and unsafely in Git using reset, revert, and restore commands, and know when to use each in real-world projects.

---

Commands Used  
git reset --soft  
git reset --mixed  
git reset --hard  
git revert  
git restore  
git checkout -- <file>  
git commit --amend  

---

Topics Covered  

1. Git Reset  
Used to move HEAD and optionally modify staging area and working directory.

Types of Reset  

Soft Reset  
- Moves HEAD to previous commit  
- Keeps changes in staging area  
- Commit is removed but code is safe  

Example:  
git reset --soft HEAD~1  

Mixed Reset (Default)  
- Moves HEAD and clears staging area  
- Keeps changes in working directory  

Example:  
git reset --mixed HEAD~1  

Hard Reset  
- Moves HEAD and deletes all changes  
- Changes are permanently lost  

Example:  
git reset --hard HEAD~1  

---

2. Git Revert  
- Creates a new commit that reverses changes  
- Safe for shared and production branches  

Example:  
git revert <commit-id>  

---

3. Git Restore  
- Restores file content from last commit or staging area  
- Does not change commit history  

Restore unstaged file:  
git restore <file-name>  

Restore staged file:  
git restore --staged <file-name>  

---

4. Amend Commit  
- Modifies the most recent commit  
- Used to fix commit message or add missed files  

Example:  
git commit --amend  

---

Key Learnings  
- Reset rewrites commit history  
- Revert preserves history and is safer for teams  
- Hard reset should never be used on shared branches  
- Restore helps recover files without affecting commits  

---

Interview Notes  
- Use revert instead of reset in production  
- Soft reset is used when commit message or files need correction  
- Hard reset can cause data loss  
- Restore replaces checkout for undoing file changes  

---
