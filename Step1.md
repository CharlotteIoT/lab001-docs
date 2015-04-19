### Step 1

Modify the python script that reads the push button switch and publishes a message to MQTT.  You should have been given a number when you got your raspberry pi from the instructor.  Make sure you use this number in the topic when publishing to MQTT.  

The topic should be:

protosystem/door/**#**/ring

Where the **#** should be the **door number** you were given when you got your Pi from the instructor.

**NOTE:** linux is case sensitive in all commands so be careful when you type in any commands while on the Raspberry Pi telnet session.


1. Using the telnet program putty change to the directory that contains the Step1 code by entering the following:

	**cd Lab001-pi/Step1**

2. Use the nano editor to edit the python script and change the publish statement to use the correct door number.  To launch the nano editor use the following command:

	**sudo nano pub_ring.py**


3. Make the necessary changes and save the file by using **ctrl-o** and exit the editor by using **ctrl-x**. 

4. To run the python script use the following command:

	**sudo python pub_ring.py**


The instructor should be running an audit program on the classroom projector so you can use that to verify when you press the doorbell button that your topic does get sent to the broker and picked up by the audit program.

Use **ctrl-c** to exit the python script in the telnet program. 

[Home](README.md) [Previous](GettingStarted.md) [Next](Step2.md)