# Reame.md

## There is a few considerations that you have to take before.

- The directories as dwm, st and dmenu doesn't have any change until here, you just have to compile and run
    `make`
    `sudo make clean install`

- Find the libraries that are missing, you can use a tool like:
    `apt-file search <dependy-name>`

- It could be that there are many dependencies try to find that one that install all.


## Add autostart.h

There are some executable that require to be added to `~/.dwm/autostart.h` to make them work

`bash
#!/bin/bash
xrandr --output LVDS-1 --off &
exec slstatus &
nitrogen --restore &
exec comptopn &
`
The executables like slstatus and compton needs to be symlink so you have to do the next:

`sudo ls -sf ~/.config/suckless/slstatus/slstatus /usr/local/bin`
`sudo ls -sf ~/.config/suckless/comptopn/compton /usr/local/bin`

You have to change `autostart.h` permissions to exec

`chmod x+ autostart.sh`
