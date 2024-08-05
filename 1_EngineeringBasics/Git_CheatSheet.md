## Version Control
- `Git`: `Distributed version control system` that enables groups of people to collaborate on the same code simultaneously, preventing them from accidentally overwriting each other’s changes.

- `Subversion`, often abbreviated as SVN, is a centralized software versioning and revision control system that shares similarities with Git.

# Git CheatSheet
- Link: https://training.github.com/downloads/github-git-cheat-sheet.pdf
- Branches: Any commits you make will be made on the branch you're currently “checked out” to. Use `git status` to see which branch that is
```
# Creates a new branch
git branch [branch-name]

# Switch to specific branch
git checkout [branch-name]

# Merge Current Branch with a particular branch
git merge [branch]

# Delete a specific branch
git branch -d [branch-name]
```

- Create Repos
```
# Turn existing dir into git repo
git init

# Download remote repo
git clone [url]

# Clone specific branch (e.g. gh-timeline)
git clone -b gh-timeline https://github.com/rtCamp/trainee-pushpender-singh.git
```

- `.gitignore` file: 
```
# Templates 
https://github.com/github/gitignore
```

- Synchronize Changes: `Local changes with remote repo`
```
# Download all history from remote tracking branches
git fetch

# Combines remote tracking branch into current local branch
git merge

# Uploads local changes to GitHub
git push

# Updates the local repo with all new commits from remote branch
git pull
```

- Makes changes
```
# Lists version history from current branch
git log

# Lists version history for a file, including renames
git log --follow [file]

# Shows content differences b/w two branches
git diff [first-branch] [second-branch]

# Output metadata & content changes of the specified commit
git show [commit]

# Snapshots the file in preparation of versioning
git add [file]

# Records file snapshots permanently in version history
git commit -m  "[descriptive msg]"

# Modify the last commit with current index changes
git commit --amend
```

- Redo commits
```
# Undoes all commits after [commit], preserving changes locally
git reset [commit]

# Discards all history & changes back to specified commit
git reset --hard [commit]
```