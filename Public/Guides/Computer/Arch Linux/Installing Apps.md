- [[#Common Apps]]
	- [[#Browsers]]
	- [[#Communication]]
	- [[#Dev/Util.]]
	- [[#File Managers]]
	- [[#Multimedia/Streaming]]
	- [[#Notes]]
 - [[#Alternative Package Management]]
	- [[#Installing AppImages]]
	- [[#Installing Yay]]
	- [[#Enabling pacman mirrorlist]]
### Common Apps
#### Browsers
|App    |Install Command     |Notes|
|:-----:|:-------------------|:----|
|Brave  |`yay -S brave-bin`     |     |
|Chrome |`yay -S google-chrome`  |launch with `google-chrome-stable` unless you add an alias|
|Firefox|`sudo pacman -S firefox`|     |
#### Communication
|App        |Install Command             |Notes|
|:---------:|:---------------------------|:----|
|Discord    |`sudo pacman -S discord`        |     |
|Signal     |`sudo pacman -S signal-desktop`  |     |
|Slack      |`yay -S slack-desktop`          |     |
|Telegram   |`sudo pacman -S telegram-desktop`|     |
|Thunderbird|`sudo pacman -S thunderbird`     |     |
#### Dev/Util.
|App         |Install Command           |Notes|
|:----------:|:------------------------:|:----|
|Flameshot   |`sudo pacman -S flameshot`    |Bind to <kbd>Print Screen</kbd> key by adding `bindsym Pint exec flameshot gui` to `~/.config/i3/config`. Hit <kbd>Print Screen</kbd> to open tool. Select screenshot area. You can <kbd>ctrl</kbd>+<kbd>c</kbd> selection to clipboard.|
|FUSE        |`sudo pacman -S fuse2`        |
|NordVPN     |`yay -S nordvpn-bin`          |Execute in order `sudo systemctl enable nordvpnd`, `sudo systemctl start nordvpnd`, `sudo usermod -aG nordvpn $USER`, `reboot`, `systemctl status nordvpnd`, `sudo nordvpn status`|
|Transmission|`yay -S transmission-cli transmission-gtk` (gtk is the gui package)|If you prefer gui, but isntalled both, you can add `` alias transmission=`transmission-gtk` `` to `~/.bashrc` or `~/.zshrc`
|Vim         |`sudo pacman -S vim`          |     |
|VS Code     |`yay -S visual-studio-code-bin`|     |
|xclip       |`sudo pacman -S xclip`        |     |
#### File Managers
|App   |Install Command    |Notes|
|:----:|:-----------------:|:----|
|Nemo  |`sudo pacman -S nemo`  |     |
|Thunar|`sudo pacman -S thunar`|     |
#### Multimedia/Streaming
|App     |Install Command        |Notes|
|:------:|:---------------------:|:----|
|Audacity|`sudo pacman -S audacity`  |     |
|OBS     |`sudo pacman -S obs-studio`|     |
|Spotify |`yay -S spotify`          |     |
|Steam   |`sudo pacman -S steam`     |You must [[#Enabling pacman mirrorlist\|enable pacman mirrorlist and update]] before using install command. Reboot after installation.|
|VLC     |`sudo pacman -S vlc`       |     |
#### Notes
|App     |Install command     | Notes                                 |
|:------:|:------------------:|:--------------------------------------|
|Notion  |`yay -S notion-app`    |                                       |
|Obsidian|[[#Installing AppImages]]|use `.AppImage` from [Obsidian's website](https://obsidian.md/download)|

### Alternative Package Management
#### Installing AppImages
>*An AppImage simplifies software distribution by packaging apps and their dependencies into a single, portable, self-contained executable.*
>
>FUSE is required to install `.AppImage` files
>	Install it via `sudo pacman -S fuse2`
>
>To install an `.AppImage`:
>	1. Download the `.AppImage` file
>	2. Make it executable 
>	`chmod +x ~/path/to/.AppImage`
>	4. Move to `/bin`
>	`sudo mv /path/to/.AppImage /bin/appname`
>	5. Call it by name



#### Installing Yay
>*Arch comes with Pacman package manager by default, but we will also use Yay. 
>Yay is an AUR (Arch User Repository) helper that wraps around Pacman.*
>
>To install Yay:
>	1. Ensure you have base-devel and git installed 
>	    `sudo pacman -S --needed git base-devel`
>	2. Clone yay repo `git clone https://aur.archlinux.org/yay.git`
>	3. `cd yay`
>	4. Build and install package `makepkg -si`

*if you want, you can chain all of these commands together as*
```
sudo pacman -S --needed git base-devel && git clone https://aur.archlinux.org/yay.git && cd yay && makepkg -si
```



#### Enabling pacman mirrorlist
>1. Edit the `/etc/pacman.conf` with your editor of choice
>	`vim /etc/pacman.conf`
>2. Uncomment the following lines:
>	```
>	#[multilib]
>	#Include = /etc/pacman.d/mirrorlist
>	```
>	so that they read
>	```
>	[multilib]
>	Include = /etc/pacman.d/mirrorlist
>	```
>1. Save and exit
>2. Update & upgrade package database
>	`sudo pacman -Syu`

