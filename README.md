# Powerlevel10k
git clone https://github.com/romkatv/powerlevel10k.git \
~/.oh-my-zsh/custom/themes/powerlevel10k

# Plugins
git clone https://github.com/zsh-users/zsh-autosuggestions ~/.zsh/plugins/zsh-autosuggestions
git clone https://github.com/zdharma-continuum/fast-syntax-highlighting ~/.zsh/plugins/fast-syntax-highlighting
git clone https://github.com/zsh-users/zsh-completions ~/.zsh/plugins/zsh-completions
git clone https://github.com/Aloxaf/fzf-tab ~/.zsh/fzf-tab

sudo dnf install -y eza bat fd-find ripgrep fzf htop

curl -fsSL https://bun.sh/install | bash

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

curl -s "https://get.sdkman.io" | bash

sudo dnf install -y docker docker-compose speedtest-cli
