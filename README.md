# Raspberry-Pi-4-NAS
Here I show you how I built a NAS using a Pi 4 and OpenMediaVault with SMB/CIFS enabled.

## Some Changes

Originally there was an image available for OpenMediaVault for the Pi 4 but that has been depreciated in favor of installing it on top of Raspbian Buster Lite. I used this tutorial [here](https://forum.openmediavault.org/index.php/Thread/28789-Installing-OMV5-on-Raspberry-PI-s-Armbian-Supported-SBC-s/) and this [video](https://www.youtube.com/watch?v=bpvlEbdA6qI) from Explaining Computers.

## How I got started

Here are the things I used to get started for the NAS:
* Raspberry Pi 4 2GB 
* 120 GB SSD
* 32 GB MicroSD Card
* 5.1V 3.5A USB-C PSU
* Sabrent USB 3 to SATA adapter
* Ethernet Cable

## Starting up the NAS

Here are the steps I took and this is based on the tutorial but I did it all in Lubuntu as opposed to Windows 10. I did use Windows 10 to access the NAS.
* Downloaded Raspbian Lite from [here](https://www.raspberrypi.org/downloads/raspberry-pi-os/). The OS name has been changed to Raspberry Pi OS since there is now an 8 GB Pi 4.
* Used etcher to write the image to the SD card.
* Ejected and reinserted the SD card
* Went to the root partition and added an empty file called ssh. You don't need to add an extension. In Windows it will ask you if you want to save it without an extension just click OK.
* Ejected the SD card again and then inserted it into the Pi. 
* Connected power, Ethernet, SATA adapter, and the SSD. 
* Once I did that, I ssh into the Pi once I was given an IP address. You can use Angry IP scanner to find your Pi. If it doesn't appear, power off and then power on again. If you use Windows, make sure to download PUTTY in order to ssh into your Pi.
* then run the following commands: `sudo apt update` and `sudo apt upgrade -y`. Once that's done you can run this command `sudo rm -f /etc/systemd/network/99-default.link`. 
* Type `sudo reboot` and the board should reboot. I did have to re-log in so make sure to do that. 
* Then I typed the following command: `wget -O -https://github.com/OpenMediaVault-Plugin-Developers/installScript/raw/master/install | sudo bash`. Took me about 10 minutes to install OMV but again it will depend on your network.
* The board rebooted and then I used the IP address assigned and logged into the GUI on a browser. So by default admin is the username and openmediavault is the password. Please change the password to avoid any issues. I followed along the tutorial that I provided from Explaining computers and it worked. 

I have attached the image of my NAS to this repo so you can see the final results. 
