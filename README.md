 ### Experiment No.: 06 – Interfacing DHT11 Sensor on Raspberry Pi
### NAME:
### ROLL NO:
### DEPARTMENT:
### DATE:

## AIM:
To interface the DHT11 temperature and humidity sensor with Raspberry Pi and read real-time environmental data using Python.

## APPARATUS REQUIRED:

1	Raspberry Pi board (any model)	1
2	MicroSD card with Raspberry Pi OS	1
3	DHT11 Sensor Module	1
4	Jumper wires (Male to Female)	3
5	Breadboard (optional)	1
6	Power adapter for Raspberry Pi	1
7	Computer/Laptop for coding	1
THEORY:
The DHT11 is a basic digital temperature and humidity sensor that outputs calibrated digital signals. It uses a capacitive humidity sensor and a thermistor to measure the surrounding air. This sensor is ideal for applications where moderate precision is acceptable, and low cost is important.

The Raspberry Pi reads data from DHT11 via GPIO pins using a Python library such as Adafruit_DHT.

## PROCEDURE:
Step 1: Wiring the DHT11 Sensor


DHT11 Pin	Connection
VCC	3.3V or 5V on Raspberry Pi
Data	GPIO pin (e.g., GPIO4)
GND	Ground (GND) on Raspberry Pi
Step 2: Installing Required Python Libraries

 
sudo apt update
sudo apt install python3-pip
pip3 install Adafruit_DHT
Step 3: Python Code to Read DHT11 Sensor

python code
 
import Adafruit_DHT
import time

sensor = Adafruit_DHT.DHT11
pin = 4  # GPIO pin where data line is connected

while True:
    humidity, temperature = Adafruit_DHT.read(sensor, pin)
    if humidity is not None and temperature is not None:
        print(f'Temp={temperature:.1f}°C  Humidity={humidity:.1f}%')
    else:
        print('Failed to read from DHT11 sensor.')
    time.sleep(2)
Step 4: Running the Code

Save the above code in a file named dht11_read.py and run:

 
python3 dht11_read.py

## CIRCUIT DIAGRAM 
![image](https://github.com/user-attachments/assets/4bef0dd6-9430-415f-bff6-354067121844)

## SCREEN SHOTS OF THE INTERFACE:

(Attach terminal output and GPIO wiring images here.)

## HARDWARE SETUP:
(Insert labeled images of the DHT11 connected to Raspberry Pi here.)

## RESULT:
The DHT11 sensor was successfully interfaced with the Raspberry Pi. Real-time temperature and humidity data were read and displayed using a Python script via the GPIO pins.

