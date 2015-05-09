### Setting up the SD Image
The SD Image has already been setup for you in the lab but these instructions tell you how to setup your own image.

1. Start off by downloading the [Raspbian](https://www.raspberrypi.org/downloads/) base image and loading it onto an SD card.
2. Make sure you connect the Raspberry Pi to a USB Keyboard, an HDMI monitor and Ethernet
3. Install the SD card into a Raspberry Pi and power it up using a micro USB power source
4. Log into the Raspberry PI
5. Update the PI

	```
	sudo apt-get update
	sudo apt-get upgrade
	```
6. Install festival text to speech

	```
	sudo apt-get install festival
	```

7. Edit the **/etc/init.d/rc.local** file and add the following at the very end of the file:

	```
	sleep 5
	MY_IP=`hostname -I | sed -e 's/\./ dot /g' -e 's/[0123456789]/ & /g'`
	echo "My I P address is $MY_IP" | /usr/bin/festival --tts
	```

8. Run raspi-config
	
	```
	sudo raspi-config  
	```

9. Select the "Internationalisation Options" menu option
10. Change the locale by unchecking en_GB and checking en_US.UTF-8 UTF-8
11. Set the time zone
12. Set the keyboard
13. Select the "<Back>" menu option
14. Select the "Advanced Options" menu option"
15. Set the audio to force the 3.5mm audio jack instead of HDMI audio
16. Exit the raspi-config and reboot the PI
17. Install Python Tools

	```
	sudo apt-get install python-setuptools
	sudo easy_install pip
	```

18. Install Python MQTT module
	
	```
	sudo pip install paho-mqtt
	```

19. Install MPG321 to play MP3 audio files
	
	```
	sudo apt-get -y install mpg321
	```

20. Install Squeezelite client

	sets up the audio mixer and adjusts the sound level

	```
    sudo alsamixer
    # Hit escape to exit the curses application
    wget http://squeezelite-downloads.googlecode.com/git/squeezelite-armv6hf
    sudo mv squeezelite-armv6hf /usr/bin
    cd /usr/bin
    sudo chmod a+x squeezelite-armv6hf
	```

21. Install Remote Desktop Protocol server for X Windows over RDP (Optional)

	```
	sudo apt-get install xrdp
	```

22. Install FTP server (Optional)

	```
	sudo apt-get install vsftpd
	sudo nano /etc/vsftpd.conf
	```
	1. Change the following in the vsftpd config file

		```
		listen=YES
		anonymous_enable=NO
		write_enable=YES
		```
	2. Restart the FTP Service
	
		```
		sudo service vsftpd restart
		```


[Home](README.md)