# Cannelle

## Préparer le Raspberry

### Install

* Get a [Raspberry Pi](https://www.raspberrypi.org/products/)
* Get a [Raspbian distribution](https://www.raspberrypi.org/downloads/raspbian/)
* [Flash the distribution](https://www.raspberrypi.org/documentation/installation/installing-images/) on the SD card
  * Use [Etcher](https://www.balena.io/etcher/)
  * Or do it manually on [Mac](https://www.raspberrypi.org/documentation/installation/installing-images/mac.md) / [Linux](https://www.raspberrypi.org/documentation/installation/installing-images/linux.md)
* [Enable SSH](https://www.raspberrypi.org/documentation/remote-access/ssh/README.md) on the Raspberry
  * Create an empty `ssh` file on the boot partition of the SD card
* Put the sd card in the Raspberry and turn it on
* Power the Raspberry and plug it to your box via Ethernet

### Log in to the Raspberry

* Get the local IP address of your Raspberry
  * Find the ip of the Raspberry by connecting to your box: 192.168.1.1
  
Or

  * Get the broadcast address of your local network: `ifconfig | grep broadcast`
  * Ping it: `ping the-ip-of-your-broadcast`
  * List all equipments and find the Raspberry: `arp -a`

* Connect via SSH: `ssh pi@the-ip-of-your-raspberry`


* [Get a fixed IP for your Raspberry](https://www.modmypi.com/blog/how-to-give-your-raspberry-pi-a-static-ip-address-update)
  * `sudo nano /etc/dhcpcd.conf`
  * Uncomment and modify this part
  
```
interface eth0

static ip_address=the-fixed-ip-you-want-for-your-raspberry/24
static routers=192.168.1.1
static domain_name_servers=192.168.1.1
```

* Reboot: `reboot`

### Bonus: Change locale and timezone
`sudo raspi-config`

### Bonus: SSH stuff
* Create a [SSH Alias](https://www.howtogeek.com/75007/stupid-geek-tricks-use-your-ssh-config-file-to-create-aliases-for-hosts/)
* [SSH authentication](http://kamilslab.com/2016/12/17/how-to-set-up-ssh-keys-on-the-raspberry-pi/)


## Install [RocketChat](https://rocket.chat/)

* Install [snapd](https://github.com/snapcore/snapd): `sudo apt update && sudo apt install snapd`
* Prey it works
* Reboot: `sudo reboot`
* Install RocketChat: `sudo snap install rocketchat-server`

*[Detailed Instructions](https://github.com/RocketChat/Rocket.Chat.RaspberryPi#easy-and-fast-installation-via-raspbian-stretch)*
