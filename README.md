# Remastering-Ubuntu-24
## Install Cubic
```
sudo apt-add-repository universe
sudo apt-add-repository ppa:cubic-wizard/release
sudo apt update
sudo apt install --no-install-recommends cubic
```
## Install Extension
```
apt-get update
apt-get install gnome-session fonts-cantarell adwaita-icon-theme-full -y
apt-get install gnome-shell-extensions gnome-tweaks -y
apt purge ubuntu-desktop gnome-shell-extension-ubuntu-dock ubuntu-session -y
apt autoremove --purge -y

apt-get install git flatpak -y
mkdir /etc/dconf/db/local.d/
echo user-db:user > /etc/dconf/profile/user
echo system-db:local >> /etc/dconf/profile/user
cd /tmp/
```
## Clone Whitesur
```
git clone https://github.com/vinceliuice/WhiteSur-gtk-theme.git --depth=1 
 cd WhiteSur-gtk-theme 
 ./install.sh -d /usr/share/themes
```
## Clone Icon Whitesur
```
git clone https://github.com/vinceliuice/WhiteSur-gtk-theme.git --depth=1 
 cd WhiteSur-gtk-theme 
 ./install.sh -d /usr/share/themes
```
## Clone Icon Whitesur
```
cd ..
git clone https://github.com/vinceliuice/WhiteSur-icon-theme.git --depth=1
cd WhiteSur-icon-theme
./install.sh -d /usr/share/icons/
```
## Clone Wallpaper
```
cd ..
git clone https://github.com/vinceliuice/WhiteSur-wallpapers.git --depth=1
cd WhiteSur-wallpapers
```
## Setting
```
nano install-wallpapers.sh
INI DI GANTI
WALLPAPER_DIR="$HOME/.local/share/backgrounds"
## PAKE INI
WALLPAPER_DIR="/etc/skel/.local/share/backgrounds"
^x
mkdir /etc/skel/.local/
cd /etc/skel/.local/
mkdir share
cd share/
mkdir backgrounds
cd /tmp/
cd WhiteSur-wallpapers
./install-wallpapers.sh
```
## Setting Tweaks
```
echo 'export GTK_THEME="WhiteSur-Light"' >> /etc/skel/.profile
flatpak override --filesystem=xdg-config/gtk-4.0
echo [org/gnome/shell/extensions/user-theme] > /etc/dconf/db/local.d/tweaks
echo "name= 'whitesur-Light-solid-pink'" >> /etc/dconf/db/local.d/tweaks
dconf update

echo [org/gnome/desktop/interface] >> /etc/dconf/db/local.d/tweaks
echo "clock-show-seconds=true" >> /etc/dconf/db/local.d/tweaks
echo "icon-theme='WhiteSur' " >> /etc/dconf/db/local.d/tweaks
echo "gtk-theme='WhiteSur-Light-solid-pink'" >> /etc/dconf/db/local.d/tweaks
dconf update
```
## Install Extension Dash Dock
```
cd ..
wget https://extensions.gnome.org/extension-data/dash-to-dockmicxgx.gmail.com.v92.shell-extension.zip -O dash.zip
mkdir -p /usr/share/gnome-shell/extensions/dash-to-dock@micxgx.gmail.com
unzip dash.zip -d /usr/share/gnome-shell/extensions/dash-to-dock@micxgx.gmail.com
chmod o+rx /usr/share/gnome-shell/extensions/dash-to-dock@micxgx.gmail.com/*
echo [org.gnome.shell.extensions.dash-to-dock] > /etc/dconf/db/local.d/dashdock
echo dock-fixed=false  >> /etc/dconf/db/local.d/dashdock
echo custom-theme-shrink=true >> /etc/dconf/db/local.d/dashdock
dconf update
```
## Setting Extension
```
cd ..
wget https://extensions.gnome.org/extension-data/dash-to-dockmicxgx.gmail.com.v92.shell-extension.zip -O dash.zip
mkdir -p /usr/share/gnome-shell/extensions/dash-to-dock@micxgx.gmail.com
unzip dash.zip -d /usr/share/gnome-shell/extensions/dash-to-dock@micxgx.gmail.com
chmod o+rx /usr/share/gnome-shell/extensions/dash-to-dock@micxgx.gmail.com/*
echo [org.gnome.shell.extensions.dash-to-dock] > /etc/dconf/db/local.d/dashdock
echo dock-fixed=false  >> /etc/dconf/db/local.d/dashdock
echo custom-theme-shrink=true >> /etc/dconf/db/local.d/dashdock
dconf update
```

