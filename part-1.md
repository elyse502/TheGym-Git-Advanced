# Git Advanced Exercises - Part 1: Refining Git History

This repository documents my journey through 10 advanced Git challenges focused on refining Git history and mastering advanced version control techniques.

## 🎯 Challenges Completed

### 1. **Missing File Fix**
**Problem**: Forgot to add `test4.md` in the last commit  
**Solution**: Used `git add test4.md` + `git commit --amend` to fix the oversight  
**Command**: 
```bash
git add test4.md
git commit --amend
```

### 2. **Editing Commit History**
**Problem**: Inaccurate commit message ("Create another file")  
**Solution**: Interactive rebase to edit commit message to "Create second file"  
**Command**:
```bash
git rebase -i HEAD~2
# Changed 'pick' to 'reword' for target commit
```

### 3. **Keeping History Tidy - Squashing Commits**
**Problem**: Multiple related commits cluttering history  
**Solution**: Squashed "Create second file" into "Create initial file"  
**Command**:
```bash
git rebase -i --root
# Used 'squash' to combine commits
```

### 4. **Splitting a Commit**
**Problem**: Single commit contained too many changes  
**Solution**: Split "Create third and fourth files" into two separate commits  
**Command**:
```bash
git rebase -i HEAD~3
git reset HEAD~
git add test3.md && git commit -m "Create third file"
git add test4.md && git commit -m "Create fourth file"
git rebase --continue
```

### 5. **Advanced Squashing**
**Problem**: Needed to recombine commits after splitting  
**Solution**: Squashed "Create third file" and "Create fourth file" back together  
**Command**:
```bash
git rebase -i HEAD~4
# Used 'squash' to recombine commits
```

### 6. **Dropping a Commit**
**Problem**: Unwanted commit in history  
**Solution**: Created and then completely removed an unwanted commit  
**Command**:
```bash
# Create unwanted commit
touch unwanted.txt
git add unwanted.txt
git commit -m "Unwanted commit"

# Remove it
git rebase -i HEAD~2
# Changed 'pick' to 'drop' for unwanted commit
```

### 7. **Reordering Commits**
**Problem**: Commits in illogical order  
**Solution**: Rearranged commit history using interactive rebase  
**Command**:
```bash
git rebase -i HEAD~3
# Manually reordered commit lines in editor
```

### 8. **Cherry-Picking Commits**
**Problem**: Needed specific changes from another branch  
**Solution**: Cherry-picked a commit from `ft/branch` to `main`  
**Command**:
```bash
git checkout -b ft/branch
# Made changes and committed
git checkout main
git cherry-pick <commit-hash>
```

### 9. **Visualizing Commit History (Bonus)**
**Solution**: Explored various visualization tools  
**Commands**:
```bash
git log --oneline --graph --all
git log --graph --all --decorate --oneline
```

### 10. **Understanding Reflogs (Bonus)**
**Solution**: Learned to use reflog as a safety net  
**Commands**:
```bash
git reflog
git reset --hard HEAD@{1}  # Recovery example
```

## 🛠️ Techniques Mastered

- **Interactive Rebasing**: `git rebase -i`
- **Commit Amendment**: `git commit --amend`
- **Squashing Commits**: Combining multiple commits
- **Splitting Commits**: Breaking large commits into smaller ones
- **Dropping Commits**: Complete removal from history
- **Cherry-Picking**: Selective commit application
- **History Visualization**: Graph-based log viewing
- **Reflog Usage**: Operation history tracking and recovery

## 📊 Key Learnings

1. **History Rewriting**: Git allows flexible history modification through rebasing
2. **Atomic Commits**: Smaller, focused commits are easier to manage
3. **Safety Nets**: Reflog provides recovery options for mistakes
4. **Branch Management**: Cherry-picking enables selective changeset application
5. **Visualization**: Graph tools provide clarity on complex branch relationships

## 🚀 How to Reproduce

1. Clone this repository
2. Follow the challenge instructions above
3. Use the provided commands to practice each technique
4. Verify results with `git log --oneline --graph --all`

This exercise significantly improved my Git proficiency and understanding of advanced version control concepts!


