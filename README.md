REMOTE DESKTOP
==============

This is a GUIDE to setup a CLOUD DESKTOP machine.
The goal is to work anywhere with a Smartphone : main chat application as App on the Phone, a Full power linux Desktop on the cloud and used with a remote desktop protocol.

Configuration :

* Linux Desktop with XFCE
* NoMachine remote desktop software 

# Setup

create a Ubuntu Server machine 20.04

assign its IP to remote-desktop entry in /etc/hosts

Download NoMachine softwere [here](https://www.nomachine.com/download)

scp nomachine_7.9.2_1_amd64.deb root@remote-desktop:./


## Base setup

update it and xfce

```bash
ssh root@remote-desktop
apt-get update
apt-get upgrade
apt install tasksel
tasksel install xubuntu-desktop
adduser [USER]
dpkg -i nomachine_7.9.2_1_amd64.deb
dpkg-reconfigure keyboard-configuration
reboot
```

## Utilities

```bash
#change keyboard layout
setxkbmap it

#sudoers . Add user to group sudo
sudo vi /etc/group
```

## Custom RESOLUTION

```bash
xrandr --listmonitors
cvt -v 1920 1000
sudo su -
mkdir -v "/etc/X11/xorg.conf.d/"
vi /etc/X11/xorg.conf.d/10-monitor.conf
# MONITOR 
reboot
```

### MONITOR

```
Section "Monitor"
        Identifier "[YOUR_OUTPUT]"
        Modeline "1920x1000_60.00"  159.25  1920 2040 2240 2560  1000 1003 1013 1038 -hsync +vsync
EndSection
```