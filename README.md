# Raspberry Pi Smart Doorbell Lab
This Lab will use Raspberry Pi's to build a smart doorbell that changes it's behavior based on the mode that a security system is placed in.  All the devices are connected together by a broker using the [MQTT](http://mqtt.org/ "MQTT") protocol.  The lab will take you through multiple steps to complete the entire project.  

### What will be provided to you
- Raspberry Pi 2
- Door Number - a number (1-15) that you will use in the code
- 8gb SD Card pre-loaded with Raspian and any other dependencies to complete the lab
- Ethernet Cable
- Micro USB Cable
- Push button Switch

### What should you bring
- Laptop preferably with an Ethernet connection
- USB Power Source or your Laptop
- Telnet Client such as putty
	- [Putty via Chocolatey](https://chocolatey.org/packages/putty "Putty via Chocolatey")
	- [http://www.chiark.greenend.org.uk/~sgtatham/putty/](http://www.chiark.greenend.org.uk/~sgtatham/putty/ "Putty website")   
- FTP Client such as FileZilla
	- [https://chocolatey.org/packages/filezilla ](https://chocolatey.org/packages/filezilla  "FileZilla via Chocolatey")
	- [https://filezilla-project.org/](https://filezilla-project.org/ "FileZilla website")
- Earphones or powered speakers with a 3.5mm jack

### Project Requirements
You will be building a doorbell device that will have a push button switch to simulate the doorbell.  This device will also respond to it's own doorbell or when another Raspberry Pi's doorbell is pressed by playing a sound.  This device will also pay attention to when the security system is placed in different modes (away, stay or disarmed) and the ring will change depending on this mode.


- If security mode is disarmed then the normal doorbell ring will be played through the speakers
- If the security mode is away then the normal doorbell ring will be played but 2 seconds later a barking sound will be played
- If the security mode is stay then no ring sound will be played

### Lab Steps
1. [Getting Started](GettingStarted.md) - Setup for the lab
2. [Step 1](Step1.md) - Read the doorbell button and publish a message
3. [Step 2](Step2.md) - Subscribe to the ring topic and play a sound
4. [Step 3](Step3.md) - Subscribe to the security mode topic and play a barking dog sound or suppress all sounds
5. [Step 4](Step4.md) - Send a message when publishing a topic and then call google translate to play the message through the speakers
6. [Step 5](Step5.md) - Play music while also doing doorbell functions

### Useful resources
- [Setting up the SD Image](SetupSDImage.md) - If you want to create your own image for this lab then follow these instructions
- [Logitech Media Server](http://allthingspi.webspace.virginmedia.com/lms.php) - How to guide on setting up a media server on the Raspberry PI
- [Logitech Media Sever Downloads](http://downloads.slimdevices.com/nightly/?ver=7.7) - You can get a windows install from here
- [Squeezelite Client](http://www.gerrelt.nl/RaspberryPi/wordpress/tutorial-installing-squeezelite-player-on-raspbian/) - How to guide on setting up a client that connects to Logitech Media Server