https://low-orbit.net/arch-linux-how-to-install-i3-gaps
If you want to open apps, you probably want a desktop or window manager. I like i3wm powered by xorg display server. Sway powered by wayland is cool but not many things run without a fuss.
### Setup i3wm
1. Update pacman `sudo pacman -Syyu`
2. Install i3-gaps `sudo pacman -S i3-gaps`
3. Install fonts and status bar `sudo pacman -S ttf-dejavu i3status`. Installing this font is important for apps to not look like shiiii, so make sure you at least do that part.
5. Install other required deps  `sudo pacman -S xorg xorg-xinit xterm rofi`
6. Optional install Nvidia drivers `sudo pacman -S nvidia nvidia-utils`
7. Launch with `startx` and go through the first time setup. Make Alt your mod key imo.
8. Locate `~/.config/i3/config`  and edit the following. These are the important edits or you alternatively copy/paste my whole config linked below. 
	1. Change `$mod + d` command to be similar to the one in my i3wm config so it uses `rofi.
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