# the Software of ArchLinux

## install some necessary software

### after arch install finish

1. edit the pacman config file in `/etc/pacman.conf`

```bash
sudo nano /etc/pacman.conf

# add to the last of the file
---------------------------------------------------------------
[archlinuxcn]
Server = https://mirrors.tuna.tsinghua.edu.cn/archlinuxcn/$arch
---------------------------------------------------------------

```

2. import GPG key

```bash
sudo pacman -S archlinuxcn-keyring
```

3. install yay & paru & other

```bash
sudo pacman -S yay paru base-devel neovim 
```

4. clone config file repository

```bash
git clone https://github.com/IHHII/.dotfiles.git
git checkout -b altas origin/altas
```

5. cancel the sudo password and change the environment variable

```bash
sudo su
nvim /etc/sudoers.d/10-installer

# change file to this #
--------------------------------
%wheel ALL=(ALL) ALL
%lostecho ALL=(ALL) NOPASSWD:ALL
--------------------------------

nvim /etc/environment

# change the environment in it #
--------------------------------
BROWSER=microsoft-edge-stable 
EDITOR=nvim
--------------------------------

```

6. add the alhp source

- check and install keyring & mirrorlist

```bash
/lib/ld-linux-x86-64.so.2 --help
yay -S alhp-keyring alhp-mirrorlist
```

- add following source to `/etc/pacman.conf`


```bash
nvim /etc/pacman.conf

# add before [core] mirror #
----------------------------------------
[core-x86-64-v3]
Include = /etc/pacman.d/alhp-mirrorlist

[extra-x86-64-v3]
Include = /etc/pacman.d/alhp-mirrorlist

#[community-x86-64-v3]
#Include = /etc/pacman.d/alhp-mirrorlist
----------------------------------------
```

- update software

```bash
sudo pacman -Syuu
```

7. oh-my-zsh setup

- use script to install oh-my-zsh

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/z-shell/F-Sy-H.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/F-Sy-H
```

- replace `.zshrc` file

```zsh
yay -S dotdrop 
dotdrop --cfg=~/.dotfiles/config.yaml install
source ~/.zshrc

```

### install desktop environment

1. install hyprland

```zsh
sudo pacman -S \
hyprland xdg-desktop-portal-hyprland wofi \
kitty mako swaylock-effects udiskie thunar btop \
polkit-kde-agent waybar-hyprland-git sddm

yay -S wlogout swww
```

2. install fonts and fcitx5

- fonts

```zsh
sudo pacman -S \
ttf-jetbrains-mono-nerd noto-fonts-emoji wqy-zenhei \
wqy-microhei wqy-microhei-lite wqy-bitmapfont
```

- fcitx5

```zsh
sudo pacman -S \
fcitx5-im fcitx5-rime fcitx5-chinese-addons \
fcitx5-material-color fcitx5-configtool fcitx5-pinyin-zhwiki

yay -S fcitx5-input-support

```

3. install some tools

```zsh
sudo pacman -S \
blueman ufw network-manager-applet timeshift\
neofetch github-desktop-bin aria2 motrix \
zathura zathura-mu-pdf
```

4. documents view and edit
```zsh
sudo pacman -S kate okular jupyterlab

yay -S microsoft-edge-stable visual-studio-code-bin \
ttf-wps-fonts wps-office-cn
```

5. develop tools

```zsh
sudo pacman -S \
mariadb mariadb-libs \
clang go python-pip cargo npm jdk-openjdk

yay -S jetbrains-toolbox
```

6. install sound

> have some unknown problem

```zsh
alsa-utils pulseaudio pulseaudio-alsa pamixer pavucontrol
```

7. install note software
```zsh
yay -S \
obsidian notion-app-enhanced typora-free \
logseq-desktop-wayland-bin anytype-bin
```

### other software

- pacman

plasma-desktop

- yay

aliyunpan-odomu \

sddm-config-editor-git hyprland-autoname-workspace-git

### git init
git config --global user.name lostecho
git config --global user.email 752549025@qq.com
git config --global credential.helper store

### some git repositories

```zsh
git clone https://github.com/selfteaching/the-craft-of-selfteaching.git
git clone https://github.com/xiaolai/regular-investing-in-box.git
git clone https://github.com/xiaolai/everyone-can-use-english.git
git clone https://github.com/xiaolai/time-as-a-friend.git
```

# hyprload
curl -sSL https://raw.githubusercontent.com/Duckonaut/hyprload/main/install.sh | bash

ghp_0ykTi91rAkLtVnxhBcLssmIZaUxVvR2hWODQ
