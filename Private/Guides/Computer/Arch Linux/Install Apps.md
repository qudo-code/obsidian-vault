## Brave Browser
You can install Brave using `yay -S brave`, but when I did, it worked, but it took like 4 hours, not exaggerating. It takes this long because it clones all of chromium and builds Brave from source. There's an alternative package you can install, `brave-bin` which I would try next time. 

## Steam
1. `vim /etc/pacman.conf`
2. Uncomment the following lines:
	`#[multilib]
	`#Include = /etc/pacman.d/mirrorlist`
3. `sudo pacman -Syu`
4. `sudo pacman -S steam`
5. `reboot`

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