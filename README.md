# HyprV4
This is V4 of the Hyprland install script

It contains a collection of dot config files for hyprland with a simple install script.
IMPORTANT - This script is meant to run on a clean fresh Arch install on physical hardware

You can grab the config files and install packages by hand with the command listed below

Do this ONLY if you need Nvidia support (do this first)
```
yay -S linux-headers nvidia-dkms qt5-wayland qt5ct libva libva-nvidia-driver-git

```
/etc/mkinitcpio.conf
```
MODULES=(nvidia nvidia_modeset nvidia_uvm nvidia_drm)
```
generate a new initramfs image
```
sudo mkinitcpio --config /etc/mkinitcpio.conf --generate /boot/initramfs-custom.img
```
Create NVIDIA Configuration
```
echo "options nvidia-drm modeset=1" | sudo tee /etc/modprobe.d/nvidia.conf
```
verify
```
cat /etc/modprobe.d/nvidia.conf
```
shoud return: 
```
options nvidia-drm modeset=1
```
now reboot
```
reboot
```

Now install the below for Hyprland

```
yay -S hyprland kitty jq mako waybar-hyprland swww swaylock-effects \
wofi wlogout xdg-desktop-portal-hyprland swappy grim slurp thunar \
polkit-gnome python-requests pamixer pavucontrol brightnessctl bluez \
bluez-utils blueman network-manager-applet gvfs thunar-archive-plugin \
file-roller btop pacman-contrib starship ttf-jetbrains-mono-nerd \
noto-fonts-emoji lxappearance xfce4-settings sddm-git sddm-sugar-candy-git 
```

Or you can use the attached script "set-hypr" to install everything for you.
