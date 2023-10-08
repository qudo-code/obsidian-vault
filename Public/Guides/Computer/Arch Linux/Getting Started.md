## Installing Arch Linux
1. Download .iso from [Arch website](https://archlinux.org/download/)
2. Use [Etcher](https://etcher.balena.io/#download-etcher) to flash .iso to a USB drive (4GB is more than enough)
3. Boot from USB
4. Use ```iwctl``` to open network config
	1. Find wireless adapter device name
	    `device list`
	2. Scan for wireless networks (this will not output anything)
	    `station`*`device`*`scan`
	    If you don't know your SSID you can list available networks with `station`*`device`*`get-networks`
	3. Connect to your network
	    `station`*`device`*`connect`*`SSID`*
	    you will be prompted for the network password
	4. You can use `station list` to confirm you are connected and use <kbd>Ctrl</kbd>+<kbd>C</kbd> to quit network config
5. Run `archinstall`
	Settings
    1. Adjust keyboard layout if necessary (default is `us`, entering `?` will enable a search)
    2. Mirror region can probably be left at default
    3. Locale language: `en_US`
    4. Select correct install drive and follow partition wizard
		- I chose `ext4` for filesystem said `No` to creating separate home and root partitions 
    1. Bootloader: `grub-install`
    2. Swap: `True`
    3. Set hostname and root password
    4. Set up a user account with the wizard
    5. Profile: probably `Desktop`
    6. Audio: choose `pipewire` or `pulseaudio`
    7. Network Configuration: set to copy config from ISO (that we set up in step 4)
    8. Set timezone
    9. `Install`
6. Once install finishes, either chroot into your new system or <kbd>ctrl</kbd>+<kbd>c</kbd>
7. `shutdown now`, remove USB installer, then try to boot into new environment (you may have to adjust BIOS settings)

## Configs
#### [[i3wm Config]]
### [[bashrc]]

## Add All These
### [[Yay Package Manager|Yay Package Manager (depricated)]]
### [[Installing Apps#Installing Yay|Install Yay]]
### [[Window Manager]]
### [[Manage Audio]]
### [[Installing Apps#Dev/Util.|Screenshots]]
### [[Installing Apps]]

## Tips n Snippets
#### [[Generate SSH Keys]]
#### [[Copy File to Clipboard]]
#### [[Installing Apps#Alternative Package Management#Installing AppImages|Installing .AppImage Files]]
### [[Resume]]





