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

Example:
```bash
git merge feature-A

# Day 3 – Git Remote Repositories (GitHub)

## 📌 Objective
Learn how to connect a local Git repository to GitHub and sync code using remote commands.

---

## 🧠 Topics Covered

### 1. git remote
- View remote repositories
- Add a remote repository
```bash
git remote
git remote -v
git remote add origin <repository-url>
2. git clone
Clone an existing GitHub repository

bash
Copy code
git clone <repository-url>
3. git push
Push local commits to GitHub

bash
Copy code
git push -u origin main
git push
4. git pull
Fetch and merge changes from remote

bash
Copy code
git pull origin main
5. git fetch
Download remote changes without merging

bash
Copy code
git fetch origin
git branch -r
git diff origin/main
6. Difference: git pull vs git fetch
Feature	git fetch	git pull
Downloads changes	Yes	Yes
Auto merge	No	Yes
Safe for teams	Yes	Use carefully
