# Pihole Firewall Setup
Low Cost Firewall for small scale industries

## Requirements
 - Raspberry Pi 3 or Better
 - SD Card 16 or better
 - Micro HDMI to HDMI cable or connector
 - RPI Power Cable
 - Monitor or TV with an HDMI Port

## Follow Through Steps
- Download the raspberry pi imager for windows or MAC , you can find the imager from the site here https://www.raspberrypi.com/software/
- Install the RPI Imager
- Open the Imager Software
- Download the Raspbian OS Image file from here https://www.raspberrypi.com/software/operating-systems/
(Pro Tip : You can directly download the image from the raspberry pi imager software but it will significantly increase the setting up time by a very large factor. So i tis better to download the image file separately and then customly flash the file into the sd card.)
- Take your SD card and connect it to the flashing system
- Open the raspberry pi imager and under Raspberrry pi device select you Raspberry pi version like Model 3, 4 etc
- Then in the Operating System settings select the Custom Image located at the bottom of the image list.
- Choose the downloaded Image of your choice.
- Set the settings as per your requirement , you can enable the SSH Connection or you can also set up the wifi before even flashing the image to the sd card.
- After all the settings have been configured , push the write button and it will start flashing the image onto the sd Card.

## One-Step Automated Install

Those who want to get started quickly and conveniently may install Pi-hole using the following command:

### `curl -sSL https://install.pi-hole.net | bash`

## Alternative Install Methods

Piping to `bash` is [controversial](https://pi-hole.net/2016/07/25/curling-and-piping-to-bash), as it prevents you from [reading code that is about to run](https://github.com/pi-hole/pi-hole/blob/master/automated%20install/basic-install.sh) on your system. Therefore, we provide these alternative installation methods which allow code review before installation:

### Method 1: Clone our repository and run

```bash
git clone --depth 1 https://github.com/pi-hole/pi-hole.git Pi-hole
cd "Pi-hole/automated install/"
sudo bash basic-install.sh
```

### Method 2: Manually download the installer and run

```bash
wget -O basic-install.sh https://install.pi-hole.net
sudo bash basic-install.sh
```

### Method 3: Using Docker to deploy Pi-hole

Please refer to the [Pi-hole docker repo](https://github.com/pi-hole/docker-pi-hole) to use the Official Docker Images.

## [Post-install: Make your network take advantage of Pi-hole](https://docs.pi-hole.net/main/post-install/)

Once the installer has been run, you will need to [configure your router to have **DHCP clients use Pi-hole as their DNS server**](https://discourse.pi-hole.net/t/how-do-i-configure-my-devices-to-use-pi-hole-as-their-dns-server/245). This router configuration will ensure that all devices connecting to your network will have content blocked without any further intervention.

If your router does not support setting the DNS server, you can [use Pi-hole's built-in DHCP server](https://discourse.pi-hole.net/t/how-do-i-use-pi-holes-built-in-dhcp-server-and-why-would-i-want-to/3026); be sure to disable DHCP on your router first (if it has that feature available).

As a last resort, you can manually set each device to use Pi-hole as their DNS server.

-----
