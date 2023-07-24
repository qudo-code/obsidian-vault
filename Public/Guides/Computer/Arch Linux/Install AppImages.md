**Install FUSE**
`sudo pacman -S fuse2`
To install files of type .AppImage, you need to install `fuse2` if you don't have it.
1. Download `.AppImage`
2. Make executable 
   `chmod +x ~/Downloads/.AppImage
3. Move executable to `/bin`
   `sudo mv /path/to/.AppImage /bin/appname
4. Call it by name.