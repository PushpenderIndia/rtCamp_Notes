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
git config --global user.name "Pushpender Singh"
git config --global user.email "singhpushpender250@gmail.com"
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
