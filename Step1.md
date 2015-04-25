### Step 1

Modify the python script that reads the push button switch and publishes a message to MQTT.  You should have been given a number when you got your raspberry pi from the instructor.  Make sure you use this number in the topic when publishing to MQTT.  

The topic should be:

protosystem/door/**#**/ring

Where the **#** should be the **door number** you were given when you got your PI from the instructor.

**NOTE:** linux is case sensitive in all commands so be careful when you type in any commands while on the Raspberry Pi telnet session.


1. Using the telnet program putty change to the directory that contains the Step1 code by entering the following:

	**cd ~/Lab001-pi/Begin**

2. Use the nano editor to edit the python script and change the publish statement to use the correct door number.  To launch the nano editor use the following command:

	**sudo nano pub_ring.py**
3. Edit the **publish.single("protosystem/door/1/ring", "", hostname="test.mosquitto.org")** by replacing the 1 in the topic to the door number that was given to you when you got your PI from the instructor.
4. Make the necessary changes and save the file by using **ctrl-o** and exit the editor by using **ctrl-x**. 
5. To run the python script use the following command:

	**sudo python pub_ring.py**


The instructor should be running an audit program on the classroom projector.  This audit program is monitoring all published messages sent to the **protosystem/#** topic.  The **#** in the topic is a wildcard character that tells the MQTT broker that the audit program wants to subscribe to all topics that start with **protosystem/**.  Watch the audit program on the projector when you press the doorbell button on your PI.  You should see your topic show up on the audit program.

Use **ctrl-c** to exit the python script in the telnet program. 

[Home](README.md) | [Getting Started](GettingStarted.md) | [Step 2](Step2.md)