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

### Getting Started


1. Wire up the push button switch to the Raspberry Pi as follows:
TODO create a picture that shows the connections
2. Plug in your Speakers or Headphones into he Raspberry Pi
3. Plug in the Ethernet cable into the Pi
3. Plug in the USB power cable and power up the Pi
4. Listen for the IP Address to be announced through the speakers and make a note of it
5. Run Putty (or other telnet program) on your laptop and use the Pi's IP address to connect to it.
6. Use **pi** for the user name
7. Use **raspberry** for the password
8. You should be at the linux shell prompt after the credentials have been entered correctly
 
