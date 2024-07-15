# Reame.md

## There is a few considerations that you have to take before.

Installation libraries

- xorg
- gcc
- libX11-devel
- libXft-devel
- libXinerama-devel

Besides any desktop you are using you gonna need to create one

- `/usr/share/xsessions`
- `touch dwm.desktop`

Add the next

```
[Desktop Entry]
Encoding=UTF-8
Name=Dwm
Comment=Dynamic window manager
Exec=dwm
Icon=dwm
Type=XSession
```

- The directories as dwm, st and dmenu doesn't have any change until here, you just have to compile and run
    - `make`
    - `sudo make clean install`

## Add autostart.sh

There are some executable that require to be added to `~/.dwm/autostart.sh` to make them work

```
#!/bin/bash
xrandr --output eDP-1 --off &
exec slstatus &
nitrogen --restore &
exec compton &
```

You gonna need to install and run compton in the next path `~/.config/suckless/`
- `got clone https://github.com/chjj/compton`

Dependencies when Fedora is use as distro

- `sudo dnf install libXcomposite-devel`
- `sudo dnf install libXdamage-devel`
- `sudo dnf install libXrandr-devel`
- `sudo dnf install libconfig-devel`
- `sudo dnf install debus-devel`
- `sudo dnf install libGL-devel`
- `sudo dnf install pcre-devel`

The executables like slstatus and compton needs to be symlink so you have to do the next:

- `sudo ls -sf ~/.config/suckless/slstatus/slstatus /usr/local/bin`
- `sudo ls -sf ~/.config/suckless/compton/compton /usr/local/bin`

You have to change `autostart.sh` permissions to exec

- `chmod +x autostart.sh`

## For patching

Example:

- `mkdir patches`
- `cd patches`
- `curl -O <github-url-of-diff>`
- `cd ../`
- `patch -p1 < patches/<diff-file>`
- `sudo vim patches`
- `make`
- `sudo make clean install`
