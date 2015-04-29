### Step 5

Play music while also doing doorbell functions.  Note: this step assumes you have completed all previous steps.

1. Open up 3 telnet sessions (if you don't already have 3 open) from your laptop to your Raspberry PI
2. In one of the telnet sessions change to the directory where your python scripts are

	**cd ~/Lab001-pi/Begin**

3. Execute the **pub_ring.py** script

	**sudo python pub_ring.py**

4. In another telnet session change to the directory where your python scripts are

	**cd ~/Lab001-pi/Begin**

5. Execute the **sub_ring.py** script

	**sudo python sub_ring.py**

6. In another telnet session run the squeezelite client. The squeezelite client takes a **-n** parameter that tells the logitech media server the name of the client.  So pass in a **p** followed by the **Door Number** you were given when you got your PI from the instructor.
	
	Example: if your door number was 10
	
	**squeezelite-armv6hf -n p10**

5. Tell the instructor that you are ready for music to be streamed to your Raspberry PI.  The instructor will add your squeezelite client to the Logitech Media Server so that it receives the same streaming audio the other Raspberry PI clients are.
6. You should be hearing the music playing through your Raspberry PI's audio jack.
7. Press your Doorbell Button and the door bell should ring along with the music playing as well as the google translate text to speech audio.
8. Open up **Remote Desktop Connection** on your windows laptop and use your Raspberry PI's IP address to connect to the PI using X Windows.
9. Log into X Windows using **pi** and **raspberry**

Congrats you have completed the lap and you now have multiple things running on a single Raspberry PI.  This thing is awesome isn't it!!!! 
 

[Home](README.md) | [Step 4](Step4.md) 