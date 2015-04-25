### Step 2

Modify the python script that subscribes to the ring topic and plays a sound.

1. In a telnet session run the pub_ring.py script that you modified in Step 1
2. Establish a 2nd telnet session to your Raspberry Pi
3. Change to the **Lab01-pi/Step2** directory

	**cd Lab01-pi/Step2**

4. Edit the **sub_ring.py** script and change the 1 in the subscribe command to be the **door number** you were given.

	**sudo nano sub_ring.py**

5. Use **ctrl-o** to save your changes and **ctrl-x** to exit the editor
6. Execute the python script and verify that when you press your doorbell button that the doorbell sound comes out of the speakers.
	
	**sudo pyhton sub_ring.py**

7. Use **ctrl-c** to exit your python script
8. Edit the **sub_ring.py** script and change the door number in the subscribe command to be the wild card character.

	```python
	client.subscribe("protosystem/door/+/ring")
	```

9. Execute the python script and verify that when any of the Raspberry PI's doorbell button is pressed then a ring sound is played by your Pi (and all other PI's that are using the same subscription wildcard.
   

[Home](README.md) | [Step 1](Step1.md) | [Step 3](Step3.md)