# HyprV4, The script that makes so that you make your life easier.
## Welcome to HyprV4!
### Purpose:

This script was created for easily install Hyprland, making your life more easy.
### Status:

This script is in **BETA**, Proceed with caution.
### Notes:
IMPORTANT - You need to install this on a fresh install of Arch.

### Installation:
Clone the project, go to the root of the project and run this command:

```
.\set-hypr
```

And you're ready to go!

### Manual Installation
If you want to do manual installation, here it is.

NOTES: You need to install Paru! I don't know if this project will have an option where you can choose yay or paru, paru will be the default now.

#### NVIDIA: Do this if you have a nvidia card.
Run this command:

```
paru -Sy linux-headers nvidia-dkms qt5-wayland qt5ct libva libva-nvidia-driver-git
```

Write this in /etc/mkinitcpio.conf:

```
MODULES=(nvidia nvidia_modeset nvidia_uvm nvidia_drm)
```

Run these command:

```
sudo mkinitcpio --config /etc/mkinitcpio.conf --generate /boot/initramfs-custom.img
```

```
echo "options nvidia-drm modeset=1" | sudo tee /etc/modprobe.d/nvidia.conf
```

OPTIONAL: Verify command.

```
cat /etc/modprobe.d/nvidia.conf
```

It should return:

```
options nvidia-drm modeset=1
```

Now reboot your system!

#### General:
Run this command:

```
paru -Sy hyprland kitty jq mako waybar-hyprland swww swaylock-effects \
wofi wlogout xdg-desktop-portal-hyprland swappy grim slurp thunar \
polkit-gnome python-requests pamixer pavucontrol brightnessctl bluez \
bluez-utils blueman network-manager-applet gvfs thunar-archive-plugin \
file-roller btop pacman-contrib starship ttf-jetbrains-mono-nerd \
noto-fonts-emoji lxappearance xfce4-settings sddm-git sddm-sugar-candy-git 
```
