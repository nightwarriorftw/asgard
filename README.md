# Dot_Files

## About
i3wm is a tool which helps you to fast your speed and increase efficiency. It also uses less RAM of you system thus decreases workload on CPU. Set some shortcuts in your config file and you will be good to go. 

## Installation Process

- Install Dependencies
```
sudo apt install libxcb1-dev libxcb-keysyms1-dev libpango1.0-dev libxcb-util0-dev libxcb-icccm4-dev libyajl-dev libstartup-notification0-dev libxcb-randr0-dev libev-dev libxcb-cursor-dev libxcb-xinerama0-dev libxcb-xkb-dev libxkbcommon-dev libxkbcommon-x11-dev xutils-dev libxcb-shape0-dev autoconf
```

Now it’s time to grab Airblader‘s xcb-util-xrm and install it from source.

```
cd /tmp
git clone https://github.com/Airblader/xcb-util-xrm
cd xcb-util-xrm
git submodule update --init
./autogen.sh --prefix=/usr
make
sudo make install
```

Ok – everything’s setup, now we can pull down the repo for i3-gaps and install it!

```
cd /tmp 
git clone https://www.github.com/Airblader/i3 i3-gaps
cd i3-gaps
autoreconf --force --install
mkdir build
cd build
../configure --prefix=/usr --sysconfdir=/etc
make
sudo make install
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

