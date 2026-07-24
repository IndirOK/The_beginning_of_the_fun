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

Variables : 

int sensePin = A0; (line 1)

int sensorInput; (line 2)

double temp; (line 3)

Before starting to write any line of code in the void setup, we set up some variables that help us keep our code structured and understandable. We have three of them : the variable for the pin in which we connected the sensor to the Arduino (which is in our case the A0 pin), the variable that will store the sensor input and the variable that will store the output of our program, which is the temperature in degrees. Respectively, the variables are the ones that are from line 1 to 3 of our program. 

Void setup : 


Serial.begin(9600) (line7)

In order to understand why, it's necessary to know what Serial.begin is. Serial.begin is a function that sets the speed of communication, in bits per second. When our Arduino will communicate with us throughout the Serial Monitor, it needs to be at the same speed, or to an approximation at least. Or else, we wouldn't get a structure response that we can understand from the Arduino, just mixed up informations. And the sort of conventional speed is 9600 bits per second. 


Void loop

The heart of the code and what I consider as the part in which concentration is necessary. 


sensorInput = analogRead(sensePin); (line12)

Remember, we made a special variable to store the input of the sensor. The function "analogRead()" is the one that every sensor that reads analog signals use to get the voltage from the sensor. In the parenthesis of the analogRead, we store which pin connects the Arduino board and the sensor. Notice that the data in it is raw, and gives us a number that is between 0 and 1023. In here, 0 means 0V and 1023 means 5V


temp = (double)sensorInput / 1024; (line 13)

temp = temp * 5; (line 14)

Now we want to convert the raw data into a voltage. Since the ADC (Arduino's analog to digital converter) is 10 bit, it means that there is exactly 1024 possible values. And to get the percentage of a number, we want to divide this number by the number of possibilities. And as the maximum voltage is 5V, we want to multiply the result by 5 and still store everything in the variable temp. 

temp = temp-0.5; (line 15)

temp = temp * 100; (line 16)

With everything we did before, the TMP36 outputs 0.5V at 0degrees and with every +0.01V, we have +1degree. The line 15 is here to remove the offset and the line 16 converts the volt in degrees. 

Serial.print("Current Temperature: "); (line 18)

Serial.println(temp); (line 19)

We want to see the results on our serial monitor, and in order to do that, we need to use the "Serial.print()" function. It works just like the function "print()" for python. 

Physical's code : 

V/ Interpretation of the results 

VI/ Learning and improvements 

VII/ Sources

For the online and physical codes and circuits : 
https://bc-robotics.com/tutorials/using-a-tmp36-temperature-sensor-with-arduino/?srsltid=AfmBOopjzVlyGL8eqAWfAqI5LI2ZBR-qxCdXudqxl80-VI92XSLyxFDi
https://learn.adafruit.com/dht?view=all
