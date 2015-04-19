# Raspberry Pi Smart Doorbell Lab
This Lab will use Raspberry Pi's to build a smart doorbell that changes it's behavior based on the mode that a security system is placed in.  All the devices are connected together by a broker using the [MQTT](http://mqtt.org/ "MQTT") protocol.  The lab will take you through multiple steps to complete the entire project.  

### What Should you Bring
- Laptop preferably with an ethernet connection
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

