# Cannelle

## Préparer le Raspberry

### Hardware

Get a Raspberry:

Get a Raspbian dist: https://www.raspberrypi.org/downloads/raspbian/

Get Etcher (to flash images) : https://www.balena.io/etcher/

Flash the Raspbian image for Raspberry.
TODO : Flash without Etcher

Enable SSH: https://www.raspberrypi.org/documentation/remote-access/ssh/README.md

Put the sd card in the Raspberry and turn it on.
Plug Ethernet + alim.

### SSH Login
Log in to the Raspberry:
* Find the ip of the Raspberry by connecting to your box: 192.168.1.1
Or
* Get the broadcast address of your local network: `ifconfig | grep broadcast`
* Ping it: `ping XXX.XXX.X.X`
* List all equipments and find the Raspberry: `arp -a`

Then `ssh pi@the-ip-of-your-ssh`


Fixed ip: https://www.modmypi.com/blog/how-to-give-your-raspberry-pi-a-static-ip-address-update
`sudo nano /etc/dhcpcd.conf`
`reboot`

### Bonus: SSH authentication
* SSH Alias
* SSH keys: http://kamilslab.com/2016/12/17/how-to-set-up-ssh-keys-on-the-raspberry-pi/


## Install [RocketChat](https://github.com/RocketChat/Rocket.Chat.RaspberryPi)
