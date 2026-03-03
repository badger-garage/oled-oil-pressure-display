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

PS10 sensors usualy gets a 5v or 12v input, in this case i'm using the same 5v from wich the ESP get from de voltage regulator 

This is basically what's the package looks like in the end


<img width="552" height="431" alt="image" src="https://github.com/user-attachments/assets/6fdf23c1-2bec-43c3-9622-42bb750b863b" /> 
<img width="552" height="551" alt="image" src="https://github.com/user-attachments/assets/c7dcfd7d-55b0-4377-8189-f7cdd14ef701" />


## Files

There is 2 .ino files, with and without the boot image on it, nothing changes, it's for the gimmick of having a boot up imagem
to change de image on boot just change the array in "const unsigned char logo [] PROGMEM = {"
(everything between de {} )

With the splashscreen.ino : 

<img width="96" height="83" alt="image" src="https://github.com/user-attachments/assets/36107874-4095-4e0e-af45-1db3a36b9233" />


Whithout it's just go straight to the oil pressure reading.

Upload any image to esp converting it to a array 
with this: https://javl.github.io/image2cpp/
(you may or may not need to adjust the export setting to be display it correctly without distortion or being weird )

