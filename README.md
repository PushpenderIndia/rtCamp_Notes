## Install Brew 
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## If Brew Already Installed, Update it
```
brew doctor
```

## Install Node.js
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"\n[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
source ~/.zprofile

# Find latest version of node.js 
nvm ls-remote
nvm install v22.5.1
```

# Install Composer 
```
brew install composer
```

# Install wget
```
brew install wget
```

# GitHub Cli
```
brew install gh
gh auth login
```

# Install LocalWP
- https://localwp.com/

# Install PHP_CodeSniffer
```
brew install php-code-sniffer
phpcs -i
git clone https://github.com/WordPress-Coding-Standards/WordPress-Coding-Standards.git ~/wpcs
phpcs --config-set installed_paths ~/wpcs\n\n
phpcs -i
composer global require "squizlabs/php_codesniffer=*"
phpcs --version
```

# Install Oh-My-Zsh
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

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
git checkout

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

# Upload local repo with all new commits from remote branch
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
git commit -m  "[descriptive msg]

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

