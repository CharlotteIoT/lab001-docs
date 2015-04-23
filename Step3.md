### Step 3

Subscribe to the security mode topic and play a barking dog sound.  The new topic for security mode is:
        
      protosystem/security/mode

The payload for this topic is one of the following: away, stay, disarmed 

1. Edit the **sub_ring.py** script
2. Add a new call to the **client.subscribe** method to subscribe to the security mode topic right after the existing client.subscribe method

	```python
	client.subscribe("protosystem/security/mode")
	```

3. Add a variable before the **on_connect** function to hold the current mode of the security system

	```python
	mode = 'unknown'
	```

4. Add code to the top of the **on_message** function to declare the mode variable as global
 
	```python
	global mode
	```
  
5. Add code to the **on_message** function to test if the topic is /mode and assign the variable created in the previous step to the payload of MQTT msg.  
 
	```python
	if '/mode' in msg.topic:
		mode=str(msg.payload)
		print mode
	```

6. Add code to the **on_message** function to test if the topic is /mode and assign the variable created in the previous step to the payload of MQTT msg.  

	```python
	if '/ring' in msg.topic:
		if mode == 'stay':
			print('silent doorbell')
		if mode == 'disarmed' or mode == 'away' or mode == 'unknown':
			filenamering1 = r'../Media/doorbell-1.wav'
			subprocess.Popen([ "/usr/bin/aplay", '-q', filenamering1 ] )	
		if mode == 'away':
			time.sleep(2)
			filenamering1 = r'../Media/dog_bark4.wav'
			subprocess.Popen([ "/usr/bin/aplay", '-q', filenamering1 ] )	
	```
7. Execute the **pub_ring.py** script.
8. Open another shell prompt using putty
9. Execute the **sub_ring.py** script.
10. Test that your doorbell works, ask the instructor to put the security system in different modes to test all functions.  
11. Exit the **pub_ring.py** script using **ctrl-c**
12. Exit the **sub_ring.py** script using **ctrl-z**


[Home](README.md) [Step 2](Step2.md) [Step 4](Step4.md)