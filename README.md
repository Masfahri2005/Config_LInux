# Development Environment Installation & Configuration

This document explains how to install and configure the development environment based on the provided ZSH configuration.

## 📋 System Prerequisites

### Operating System
- **Linux** (recommended: Ubuntu 22.04+, Debian 11+, or other modern distributions)
- **macOS** (via Homebrew)
- **WSL2** (for Windows users)

### Minimum Requirements
- RAM: 4GB (8GB recommended)
- Storage: 20GB free space
- Internet connection to download packages

## 🚀 Installation Steps

### 1. **Install ZSH and Oh My ZSH**

```bash
# Install ZSH
sudo apt update && sudo apt install -y zsh

# Set ZSH as default shell
chsh -s $(which zsh)

# Install Oh My ZSH
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

**Explanation:** ZSH (Z Shell) is a powerful shell with richer autocomplete features, themes, and plugins than the default bash. Oh My ZSH is a framework for managing ZSH configuration.

### 2. **Install Powerlevel10k Theme**

```bash
# Clone Powerlevel10k to themes directory
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/.oh-my-zsh/custom/themes/powerlevel10k
```

**Explanation:** Powerlevel10k is a very fast ZSH theme that is customizable with informative and visually appealing prompts.

### 3. **Install ZSH Plugins**

```bash
# Create directory for plugins
mkdir -p ~/.zsh/plugins

# Clone required plugins
git clone https://github.com/zsh-users/zsh-autosuggestions ~/.zsh/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-completions ~/.zsh/plugins/zsh-completions
git clone https://github.com/zdharma-continuum/fast-syntax-highlighting ~/.zsh/plugins/fast-syntax-highlighting
git clone https://github.com/Aloxaf/fzf-tab ~/.zsh/plugins/fzf-tab
```

**Explanation:**
- **zsh-autosuggestions**: Provides automatic command suggestions based on history
- **zsh-completions**: Additional collection of completion definitions
- **fast-syntax-highlighting**: Fast syntax highlighting for ZSH
- **fzf-tab**: Uses fzf for interactive tab completion

### 4. **Install Modern Tools**

#### **Eza (Replacement for ls)**
```bash
# Install via Homebrew
brew install eza

# Or install from source
cargo install eza
```

**Explanation:** Eza is a modern replacement for `ls` with better colors, icons, and information.

#### **Bat (Replacement for cat)**
```bash
# Install via Homebrew
brew install bat

# Or install from Cargo
cargo install bat
```

**Explanation:** Bat is a replacement for `cat` with syntax highlighting, numbering, and pagination.

#### **Ripgrep (Replacement for grep)**
```bash
# Install via Homebrew
brew install ripgrep

# Or install from Cargo
cargo install ripgrep
```

**Explanation:** Ripgrep is a very fast search tool, better than traditional grep.

#### **fd (Replacement for find)**
```bash
# Install via Homebrew
brew install fd

# Or install from Cargo
cargo install fd-find
```

**Explanation:** fd is a faster and more user-friendly replacement for `find`.

### 5. **Install Package Managers**

#### **Homebrew (for Linux)**
```bash
# Install Homebrew for Linux
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Add to PATH
eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
```

#### **SDKMAN (for Java/Kotlin/Groovy)**
```bash
# Install SDKMAN
curl -s "https://get.sdkman.io" | bash

# Restart shell or source
source "$HOME/.sdkman/bin/sdkman-init.sh"
```

#### **Bun (JavaScript Runtime)**
```bash
# Install Bun
curl -fsSL https://bun.sh/install | bash

# Add to PATH
export BUN_INSTALL="$HOME/.bun"
export PATH="$BUN_INSTALL/bin:$PATH"
```

### 6. **Install Runtime & Development Tools**

#### **Node.js (via SDKMAN or nvm)**
```bash
# Via SDKMAN
sdk install nodejs

# Or via nvm
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
nvm install --lts
```

#### **PHP & Composer**
```bash
# Install PHP
sudo apt install -y php php-cli php-curl php-mbstring php-xml php-zip

# Install Composer
curl -sS https://getcomposer.org/installer | php
sudo mv composer.phar /usr/local/bin/composer
```

#### **Python**
```bash
# Install Python
sudo apt install -y python3 python3-pip python3-venv
```

#### **Docker**
```bash
# Install Docker
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh

# Add user to docker group
sudo usermod -aG docker $USER
```

#### **PostgreSQL & MongoDB**
```bash
# PostgreSQL
sudo apt install -y postgresql postgresql-contrib

# MongoDB
curl -fsSL https://pgp.mongodb.com/server-7.0.asc | \
   sudo gpg -o /usr/share/keyrings/mongodb-server-7.0.gpg \
   --dearmor
echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list
sudo apt update
sudo apt install -y mongodb-org
```

### 7. **Configuration Files**

#### **Copy Configuration Files**
1. Copy `.zshrc` to home directory:
   ```bash
   cp .zshrc ~/.zshrc
   ```

2. Create cache directory for Powerlevel10k:
   ```bash
   mkdir -p ~/.cache
   ```

3. Generate Powerlevel10k configuration file:
   ```bash
   p10k configure
   ```

#### **LS_COLORS Color File**
```bash
# Download color scheme for ls/eza
curl -fsSL https://raw.githubusercontent.com/trapd00r/LS_COLORS/master/LS_COLORS -o ~/.config/ls_colors
```

### 8. **Installation Verification**

After everything is installed, restart the terminal or run:
```bash
source ~/.zshrc
```

Verify with commands:
```bash
# Check tool versions
zsh --version
eza --version
bat --version
rg --version
fd --version
node --version
php --version
python3 --version
docker --version
```

## ⚙️ Main Environment Features

### 🎨 **UI/UX Enhancement**
- **Powerlevel10k**: Informative prompt with customizable segments
- **Eza**: File listing with icons and colors
- **Bat**: File preview with syntax highlighting
- **FZF**: Fuzzy finder for files and directories

### 🔧 **Development Tools**
- **Multi-language support**: Node.js, PHP, Python, Java
- **Package managers**: npm, bun, pnpm, composer, pip
- **Database tools**: PostgreSQL, MongoDB
- **Containerization**: Docker with useful aliases

### ⚡ **Performance**
- **Fast-syntax-highlighting**: Optimized highlighting for speed
- **Zsh-autosuggestions**: Responsive suggestions
- **Fzf-tab**: Fast and interactive tab completion

### 📁 **Useful Aliases**
- **File operations**: `ll`, `la`, `tree`, `lst`
- **Navigation**: `..`, `...`, `home`, `desk`
- **Development**: `php artisan`, `npm run`, `bun run`
- **Git**: `gs`, `ga`, `gco`, `gl`
- **System**: `myip`, `ports`, `disk`, `cpu`
