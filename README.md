# Reame.md

## There is a few considerations that you have to take before.

- The directories as dwm, st and dmenu doesn't have any change until here, you just have to compile and run
    - `make`
    - `sudo make clean install`

## Add autostart.sh

There are some executable that require to be added to `~/.dwm/autostart.sh` to make them work

`
#!/bin/bash
xrandr --output eDP-1 --off &
exec slstatus &
nitrogen --restore &
exec compton &
`
The executables like slstatus and compton needs to be symlink so you have to do the next:

- `sudo ls -sf ~/.config/suckless/slstatus/slstatus /usr/local/bin`
- `sudo ls -sf ~/.config/suckless/compton/compton /usr/local/bin`

You have to change `autostart.sh` permissions to exec

- `chmod +x autostart.sh`
