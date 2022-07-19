# conf-terminator-zsh-ohmyzsh-fonts-icons
## Update System
sudo apt update
## Install terminator
sudo apt install -y terminator
## Install zsh
sudo apt install -y zsh
echo $SHELL
sudo usermod -s /usr/bin/zsh $(whoami)
## Install Oh My Zsh
sudo apt install -y curl
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
## Install powerlevel10k
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k
nano .zshrc
ZSH_THEME="powerlevel10k/powerlevel10k”
source .zshrc
## Plugins ZSH
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

mkdir ~/.fonts
wget -P ~/.fonts 'https://github.com/ryanoasis/nerd-fonts/releases/download/v2.1.0/BitstreamVeraSansMono.zip' 
unzip ~/.fonts/BitstreamVeraSansMono.zip -d ~/.fonts
p10k configure
sudo apt install fonts-firacode