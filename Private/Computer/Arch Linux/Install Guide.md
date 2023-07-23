## Install Arch Linux
1. Download .iso from Arch website.
2. On mac/win, flash it using Ethcher.
3. Boot from the USB and run `archinstall` util.
4. **Settings**
	1. **Drives:** When setting up drives, I chose ext filesystem and say NO to making home & root separate partitions.
	2. **Internet**: Under network settings, be sure to select networkmanager or you won't have internet. 
5. Go ahead and run it, let it do its thing and install OS. Once finished, it will ask if you want to chroot into your new system, you don't have to. At that point, you can run `shutdown now`, then remove the USB installer, and see if your new environment boots on its own.

## Window Manager
If you want to open apps, you probably want a desktop or window manager. I like i3wm powered by xorg display server. Sway powered by wayland is cool but not many things run without a fuss.
### Setup i3wm
1. Update pacman `sudo pacman -Syyu`
2. Install i3-gaps `sudo pacman -S i3-gaps`
3. Install fonts and status bar `sudo pacman -S ttf-dejavu i3status`
5. Install other required deps  `sudo pacman -S xorg xorg xterm rofi`
6. Optional install Nvidia drivers `sudo pacman -S nvidia nvidia-utils`
7. Launch with `startx` and go through the first time setup. Make Alt your mod key imo.
8. Locate `~/.config/i3/config`  and edit the following. These are the important edits or you alternatively copy/paste my whole config linked below. 
	1. Change `$mod + d` command to be similar to the one in my i3wm config so it uses `rofi
	2. Change `$mod + Enter` to open xterm with better theme. 
	3. Use font we installed by adding/uncommenting `font pango:DejaVu Sans Mono 12`
#### [[My i3wm Config]]
- Movement keys changed to be like vim
- Split horizontal with V since H now taken
- $mod key is Alt
- Open xterm with better theme
- Use rofi app launcher instead of dmenu
- Select new font
- Flameshot screenshot binding.

#### i3wm Cheat Sheet
https://i3wm.org/docs/refcard.html

#### Launch Apps in i3wm
You can launch and scroll through installed apps with `Alt + d` if you setup `rofi` or `dmenu`.

## Manage Audio
To manage audio I use `alsamixer`, it's a cool TUI. Once installed usually add a `sound` alias to my `.bashrc` to launch it. You could also add a i3wm shortcut and be even cooler.
**Install**
	`pacman -S alsa-utils
**Test Speakers**
	`speaker-test -c2
**Launch Mixer**
	`alsamixer`

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
- Obsidian (download `.AppImage` from their website)

## Tips n Snippets
#### Generate SSH Keys
`ssh-keygen -t rsa -b 4096 -C "you@you.com"

#### Copy File Contents to Clipboard
`cat thefile.txt | xclip -selection clipboard

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

#### Run Apps in Background
Run apps in background so you don't need to keep the terminal open. 
`appname & disown`




