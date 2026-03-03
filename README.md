# ESP32 OLED Oil pressure display

<img width="700" height="500" alt="image" src="https://github.com/user-attachments/assets/edd5364a-c42d-4af4-92ee-88dbead7919e" />



## Overview 
It's a simple code running on a ESP32 board, more especificaly on a XIAO SEED STUDIO ESP32-C3, function exactly as a auto dash gauge, in this 
case using it to display the oil pressure reading from a PS10 type sensor in the engine.

Wokwi page: https://wokwi.com/projects/417101963463556097

## Everything that it need to work:

- ESP32 (any model will work, i am using de seed studio for its compact size, fit better inside de air vents on the console)
- OLED Display 128x64
- LM7805 Voltage regulator (or anything that it has a 5v output on ignition of the car will work)
- PS10 or similar pressure sensor
- 2x 10k resistor 


## Basic wiring diagram 

-Based on the SEED STUDIO ESP


<img width="528" height="437" alt="image" src="https://github.com/user-attachments/assets/61b93ba3-e852-4c05-9621-3bcba0de6d01" />



- D0 = Signal from sensor 
- D2 = SDA from OLED
- D3 = SCL from OLED
- Resistor in series from the signal of sensor (sensor returns a value from 0,5v to 4,5v, thats gets translated to pressure, since de ADC input in the ESP reads 3,3v, the resistor are there to step down the value from the sensor, its not the ideal, since the value would not be exactly, buts its close enough for my needs) 

Its not on the image but, the voltage regulator gets wired in at the 5v input from esp
- Pin 1 = Input from 12v (preferable a switch on ignition 12v)
- Pin 2 = Ground
- Pin 3 = 5v output


