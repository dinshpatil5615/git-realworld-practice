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

## Git Branching, Merging & Conflict Resolution – Day 3

### Objective  
Understand how Git supports parallel development using branches, how merging works, and how to resolve merge conflicts manually in real-world scenarios.

---

### Commands Used  
git branch  
git switch  
git checkout  
git merge  
git status  
git diff  
git log --graph --oneline  
git branch -d  

---

### Topics Covered  

### 1. Git Branching  
- Created multiple branches (feature-A, feature-B)  
- Learned how branches allow parallel development  
- Understood that branches are pointers to commits, not copies of code  
- Observed how branches diverge from a common base commit  

Example:
```
git branch feature-A  
git switch feature-A  
```

---

### 2. Fast-Forward Merge  

Fast-Forward Merge  
- Happens when the target branch has no new commits  
- Git simply moves the branch pointer forward  
- No new merge commit is created  

Example:
```
git switch main  
git merge feature-A  
```
---

### 3. Merge Commit  

Merge Commit  
- Happens when both branches have new commits  
- Git creates a new merge commit  
- Complete branch history is preserved  

Example:
```
git merge feature-B  
```

---

### 4. Merge Conflicts  

Merge Conflict  
- Occurs when the same file is modified differently in two branches  
- Git cannot decide which change to keep  
- Conflict must be resolved manually  

Conflict Resolution Steps  
1. Run merge command  
2. Identify conflicted files using git status  
3. Open the file and resolve conflicts  
4. Remove conflict markers  
5. Add the resolved file  
6. Commit the merge  

Commands:
```
git status  
git add <file-name>  
git commit  
```

---

Key Learnings  
- Branches are lightweight and efficient  
- Fast-forward merges keep history linear  
- Merge commits record branch integration  
- Merge conflicts are common in team environments  
- Git never resolves conflicts automatically  

---

Interview Notes  
- Teams use branches to isolate features and fixes  
- Fast-forward merge occurs when history is linear  
- Merge commits are created when histories diverge  
- Conflict resolution is a developer responsibility  
- Understanding git log --graph helps visualize branching  

---

## Git Remote Repositories (GitHub) - Day 4

### 📌 Objective
Learn how to connect a local Git repository to GitHub and sync code using remote commands.

---

### 🧠 Topics Covered

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

## Git Undoing Changes – Reset, Revert & Restore – Day 5

### Objective  
Understand how to undo changes safely and unsafely in Git using reset, revert, and restore commands, and know when to use each in real-world projects.

---

### Commands Used  
git reset --soft  
git reset --mixed  
git reset --hard  
git revert  
git restore  
git checkout -- <file>  
git commit --amend  

---

### Topics Covered  

### 1. Git Reset  
Used to move HEAD and optionally modify staging area and working directory.

Types of Reset  

Soft Reset  
- Moves HEAD to previous commit  
- Keeps changes in staging area  
- Commit is removed but code is safe  

Example:  
```
git reset --soft HEAD~1  
```

Mixed Reset (Default)  
- Moves HEAD and clears staging area  
- Keeps changes in working directory  

Example:  
```
git reset --mixed HEAD~1
``` 

Hard Reset  
- Moves HEAD and deletes all changes  
- Changes are permanently lost  

Example:  
```
git reset --hard HEAD~1  
```

---

### 2. Git Revert  
- Creates a new commit that reverses changes  
- Safe for shared and production branches  

Example:  
```
git revert <commit-id>  
```

---

### 3. Git Restore  
- Restores file content from last commit or staging area  
- Does not change commit history  

Restore unstaged file:  
```
git restore <file-name>
``` 

Restore staged file:  
```
git restore --staged <file-name>  
```

---

### 4. Amend Commit  
- Modifies the most recent commit  
- Used to fix commit message or add missed files  

Example:  
```
git commit --amend  
```
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

## Git Workflows, Best Practices & Interview Preparation – Day 6

### Objective  
Understand how Git is used in real-world team environments, common workflows followed in companies, and prepare Git concepts for technical interviews.

---

### Topics Covered  

### 1. Git Workflow (Real-World Usage)
- Feature-based development workflow
- Developers create feature branches
- Code is merged into main or develop branch after review
- Used widely in DevOps and CI/CD pipelines

Typical Flow:
- main → stable production-ready code
- feature/* → new features or fixes
- hotfix/* → urgent production fixes

---

### 2. Pull Request (PR) Concept
- Pull Request is a request to merge code from one branch to another
- Code is reviewed before merging
- Used in GitHub, GitLab, Bitbucket

Key Points:
- Improves code quality
- Enables team collaboration
- Prevents direct changes to main branch

---

### 3. Git Best Practices
- Make small and meaningful commits
- Write clear commit messages
- Pull or fetch before pushing
- Never use hard reset on shared branches
- Use revert for production fixes
- Delete merged branches to keep repo clean

---

### 4. Common Git Interview Questions (Conceptual)

- Difference between git fetch and git pull
- Difference between git reset and git revert
- What is a merge conflict and how do you resolve it?
- What happens during a fast-forward merge?
- When should you use git commit --amend?
- Why should history not be rewritten on shared branches?

---

### 5. Git in DevOps
- Git triggers CI/CD pipelines
- Infrastructure as Code stored in Git
- Git acts as a single source of truth
- Used with tools like Jenkins, GitHub Actions, ArgoCD

---

### Key Learnings  
- Git workflows help teams collaborate efficiently  
- Pull Requests are essential for controlled code merging  
- Best practices prevent data loss and conflicts  
- Git knowledge is critical for DevOps roles  

---

### Interview Notes  
- Git is not just a tool, it is a workflow enabler  
- Revert is preferred over reset in production  
- Fetch is safer than pull in team environments  
- Pull Requests improve collaboration and code quality
