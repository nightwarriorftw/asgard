# Dot_Files

## About
i3wm is a tool which helps you to fast your speed and increase efficiency. It also uses less RAM of you system thus decreases workload on CPU. Set some shortcuts in your config file and you will be good to go. 

## Installation Process

- Install i3-gaps

```BASH
sudo add-apt-repository -y ppa:regolith-linux/stable
sudo apt install i3-gaps
```

- Install ```i3blocks``` for showing status bar
- Install ```feh``` for background image
- Install ```compton``` for transparent background of terminal
- Install ```rofi``` which can be used as search tool.
- Install ```i3lock-fancy``` to lock your system.
- Install ```acpi```


Don't forget to install ```xbright```(alternative for xbacklight) and ```pulse audio```(for audio).

## Setup
So the process for setting i3wm is simple. Use the above configs of ```i3```, ```compton``` and ```rofi``` for setting thing up. Place these folder in you ```~/.config``` folder. Press ```Mod+Shift+R``` and you are good to go. 

## General Hacks
While installing Buster 10 I faced some general issues, so following are some tips and tricks

- Touchpad not working
```
$ mkdir -p /etc/X11/xorg.conf.d
$ echo 'Section "InputClass"
        Identifier "libinput touchpad catchall"
        MatchIsTouchpad "on"
        MatchDevicePath "/dev/input/event*"
        Driver "libinput"
        Option "Tapping" "on"
EndSection' > /etc/X11/xorg.conf.d/40-libinput.conf
$ systemctl restart lightdm
```

- Installing ZSH and changing default shell to zsh

Install zsh with
```
sudo apt install zsh
```
Now install oh-my-zsh
```
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
While installing the installer will ask about the default shell to choose, type 'y' if you want zsh to be default then just simply logout and login.

