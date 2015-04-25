### Step 4

Send a message when publishing a topic and then call google translate to play the message through the speakers.  Note: this step assumes you have completed all previous steps.

1. Open up 2 telnet sessions (if you don't already have 2 open) from your laptop to your Raspberry PI
2. In one of the telnet sessions change to the directory where your python scripts are

	**cd ~/Lab001-pi/Begin**

3. Edit the **pub_ring.py** script to send a special message when the doorbell button is pressed.

	```python
        publish.single("protosystem/door/1/ring", "Get the door", hostname="test.mosquitto.org")
	```
4. Execute the **pub_ring.py** script

	**sudo python pub_ring.py**

5. Press your doorbell button and verify that your message shows up on the audit program.

6. In another telnet session change to the directory where your python scripts are

	**cd ~/Lab001-pi/Begin**

7. Edit the **sub_ring.py** script to by adding a **say** function that takes a message and calls google translate to convert it to an mp3 file and play it.  Place this function before the **on_connect* function.


	```python
	def say(message):
	    # Use Google Translate Text To Speech
	    tts_text = message.replace(" ","+")
	    tts_url = "http://translate.google.com/translate_tts?ie=UTF-8&tl=en&q="+tts_text
	    cmd_line = ['wget', '-q', '-U', 'Mozilla', '-O', 'message.mp3',tts_url] 
	    p = subprocess.Popen(cmd_line, stdout=subprocess.PIPE)   
	    stdout, stderr = p.communicate() #wait
	    cmd_line = ['mpg321', 'message.mp3']
	    subprocess.Popen(cmd_line)
	```

8. Modify the **on_message** function to call the **say** function when the payload is not empty for the **ring** topic.

	```python
        if mode == 'disarmed' or mode == 'away' or mode == 'unknown':
            filenamering1 = r'../Media/doorbell-1.wav'
            subprocess.Popen([ "/usr/bin/aplay", '-q', filenamering1 ] )
            # New code goes here to test the payload and call the say function
            if msg.payload != '':
                    print msg.payload
                    say(msg.payload)    

	```

9. Execute the **sub_ring.py** script

	**sudo python sub_ring.py**

10. Press your doorbell button and verify that your message is played through the Raspberry PI audio jack.
11. Stop the **pub_ring.py** script using **ctrl-c**
12. Stop the **sub_ring.py** script using **ctrl-z**


[Home](README.md) | [Step 3](Step3.md) | [Step 5](Step5.md) 