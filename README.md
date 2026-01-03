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

# Day 3 – Git Branching, Merging & Conflict Resolution

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

