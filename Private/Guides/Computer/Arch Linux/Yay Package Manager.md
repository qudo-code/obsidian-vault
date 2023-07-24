`pacman` and `yay` are the two ways you usually install stuff on arch. Our system has pacman, but you will definitely need yay to install a lot of things from AUR.
1. `sudo pacman -S git`
2. `cd /opt`
3. `sudo git clone https://aur.archlinux.org/yay-git.git`
4. `sudo chown -R qudo:qudo ./yay-git` (swap 'qudo')
5. `cd yay-git`
6. `makepkg -si`
7. Once installed upgrade everything.
	`yay -Syu`