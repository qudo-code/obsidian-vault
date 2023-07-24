## Install Arch Linux
1. Download .iso from Arch website.
2. On mac/win, flash it using Ethcher.
3. Boot from the USB and run `archinstall` util.
4. **Settings**
	1. **Drives:** When setting up drives, I chose ext filesystem and say NO to making home & root separate partitions.
	2. **Internet**: Under network settings, be sure to select networkmanager or you won't have internet. 
5. Go ahead and run it, let it do its thing and install OS. Once finished, it will ask if you want to chroot into your new system, you don't have to. At that point, you can run `shutdown now`, then remove the USB installer, and see if your new environment boots on its own.

## [[Window Manager]]

## Screenshots
Flameshot is pretty sweet.
**Install**
	`sudo pacman flameshot`
**Bind to Print Screen Key**
Add to `~/.config/i3/config`
	`bindsym Pint exec flameshot gui`
**Usage**
Hit the Print Screen key which will bring up a selection tool. Selected what you want to screenshot. `ctrl + c` to copy result to clipboard.

## Yay Package Manager
`pacman` and `yay` are the two ways you usually install stuff on arch. Our system has pacman, but you will definitely need yay to install a lot of things from AUR.
1. `sudo pacman -S git`
2. `cd /opt`
3. `sudo git clone https://aur.archlinux.org/yay-git.git`
4. `sudo chown -R qudo:qudo ./yay-git` (swap 'qudo')
5. `cd yay-git`
6. `makepkg -si`
7. Once installed upgrade everything.
	`yay -Syu`

## Brave Browser
You can install Brave using `yay -S brave`, but when I did, it worked, but it took like 4 hours, not exaggerating. It takes this long because it clones all of chromium and builds Brave from source. There's an alternative package you can install, `brave-bin` which I would try next time. 

## Common Apps
- `sudo pacman -S discord`
- `sudo pacman -S telegram-desktop` (go into settings and turn on system status bar)
- `sudo pacman -S signal-desktop`
- `sudo pacman -S obs-studio`
- `yay -S slack-desktop`
- `sudo pacman -S vim`
- `sudo pacman -S xclip`
- `yay -S notion-app`
- `yay -S spotify`
- `yay -S visual-studio-code-bin`
- Obsidian (download `.AppImage` from their website)

## Tips n Snippets
#### [[Generate SSH Keys]]
#### [[Copy File to Clipboard]]

#### Install `.AppImage`s
**Install FUSE**
`sudo pacman -S fuse2`
To install files of type .AppImage, you need to install `fuse2` if you don't have it.
1. Download `.AppImage`
2. Make executable 
   `chmod +x ~/Downloads/.AppImage
3. Move executable to `/bin`
   `sudo mv /path/to/.AppImage /bin/appname
4. Call it by name.




