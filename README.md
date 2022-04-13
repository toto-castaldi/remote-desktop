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
reboot
```
