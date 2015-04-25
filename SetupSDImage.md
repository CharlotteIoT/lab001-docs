### Setting up the SD Image
The SD Image has already been setup for you in the lab but these instructions tell you how to setup your own image.

1. Start off by downloading the [Raspbian](https://www.raspberrypi.org/downloads/) base image and loading it onto an SD card.
2. Make sure you connect the Raspberry Pi to a USB Keyboard, an HDMI monitor and Ethernet
3. Install the SD card into a Raspberry Pi and power it up using a micro USB power source
4. Log into the Raspberry PI
5. Update the PI

	**sudo apt-get update**

	**sudo apt-get upgrade**
6. Install festival text to speech

	**sudo apt-get install festival**
7. Edit the **/etc/rc.local** file and add the following before the exit 0:

	**hostname -I | festival --tts**

8. Run raspi-config
	
	**sudo raspi-config**  

9. Change the local by unchecking en_GB and checking en_US.UTF-8 UTF-8
10. Set the time zone
11. Set the keyboard
11. Set the audio to force the 3.5mm audio jack instead of HDMI audio
12. Expand the file system
13. Exit the raspi-config and reboot the PI
12. Install Python Tools

	**sudo apt-get install python-setuptools**

	**sudo easy_install pip**

14. Install Python MQTT module
	
	**sudo pip install paho-mqtt**

15. Install MPG321 to play MP3 audio files
	
	**sudo apt-get -y install mpg321**

16. Install Squeezelite client

	sets up the audio mixer and adjusts the sound level

    **sudo alsamixer** 

    **mkdir squeezelite**

    **cd squeezelite**

    **wget http://squeezelite-downloads.googlecode.com/git/squeezelite-armv6hf**

    **sudo mv squeezelite-armv6hf /usr/bin**

    **cd /usr/bin**

    **sudo chmod a+x squeezelite-armv6hf**

17. Install Remote Desktop Protocol server for X Windows over RDP (Optional)

	**sudo apt-get install xrdp**

[Home](README.md)