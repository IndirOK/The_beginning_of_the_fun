PROJECT : Temperature monitor 

I/ Goals and effects of the project

When I chose to do this project, I thought it would be quite easy. With the confidence of knowing how to blink a LED, use a potentiometer and use a button, 
I thought it would be an easy task as the first sensor I use, but it was quite the contrary. Experimenting, studying and programming two distinct temperature sensors,
has been a both interesting and fascinating experience. The challenging understanding of the code and the divine taste
of finally underestanding what I am doing made me fall deeply in love with the concepts of microelectronics. I first built it simply to understand the concepts, but 
I then understood that a flame has appeared, one that makes me want to develop that project, and that gives this project a deeper meaning : to be the beginning of 
the usage of sensors, the starting point. 

II/ Materials 

Online (in TiknerCad) :
- 1 mini breadboard ;
- 1 Arduino board
- 1 TMP36 (temperature sensor)

Physical :
- 1 mini breadboard ;
- 1 Elegoo Uno 3 board ;
- 3 jumper wires ;
- 1 DHT11 (temperature and humidity sensor).

III/ Circuit's logic

Online circuit : 
The TMP36 is a temperature sensor that has 3 pins : one for alimentation, one that receives signals and one for the ground. The alimentation has been connected to the 5V of the Arduino board as the sensor needs to receive anywhere between 2.7VDC and 5.5VDC. With the simple principles of how a circuit works, the ground of the TMP36 should be connected to the ground of the Arduino. Finally, for the pin that receives the signals is connected to the analog pin 0 of the Arduino since the output voltage is an analog voltage that is proportional to the temperature. Thus, it makes the reading of the signals coming from the sensor easier. 

Physical circuit : 
The DHT11 is a temperature and humidity sensor that has 3 or 4 pins, depending on the model. The model I used has 3 pins : one for alimentation, one for the signal and one for the ground. Practically all the connections are the same as the TMP36, but instead of connecting the signal pin to an analog pin, the DHT11 is connected to a digital pin, because it outputs digital data instead of analog signals. 

IV/ Code explanation 

Online's code : 

Physical's code : 

V/ Interpretation of the results 

VI/ Learning and improvements 
