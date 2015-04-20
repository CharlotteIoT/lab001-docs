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
11. Set the audio to force the 3.5mm audio jack instead of HDMI audio
12. Install Python Tools

	**sudo apt-get install python-setuptools**

	**sudo easy_install pip**

14. Install Python MQTT module
	
	**sudo pip install paho-mqtt**

15. Install mp3player (might not really be needed)
	
	**sudo pip install mp3play**

15. Install Squeezelite client (TODO)

[Home](README.md)