# Python Robotics on the Raspberry Pi Pico: Sensors, Motors, and Control

## Course Goals:
Learn how to use Python on a Raspberry Pi Pico to read sensors, control actuators, communicate with a host computer, and build real robotics projects step by step.

## General Course Topics
### Part 1 — Foundations
  * Pico
  * MicroPython
  * GPIO
  * sensors
  * PWM

### Part 2 — Robot behaviors
  * state machines
  * control
  * telemetry
  * sensor fusion basics
    
### Part 3 — Robotics ecosystem
  * host Python
  * serial protocols
    * UART
    * I2C/SPI
  * ROS 2 / micro-ROS intro


### Lesson 1 — “Your First Robot Signal”
Python Robotics with Raspberry Pi Pico
* Lab
  * plug in Pico
  * open Thonny
  * flash MicroPython (if needed)
  * setup comm
  * run LED blink

microPython Code:
```
from machine import Pin
import time

led = Pin(25, Pin.OUT)

while True:
    led.toggle()
    time.sleep(0.5)
```

### Lesson 2 — “Read the Real World”
Goal:
  * Input signal → decision → output

* Lab
  * add button or simple sensor
  * control LED with input
 
Code:
```
button = Pin(14, Pin.IN, Pin.PULL_DOWN)
led = Pin(25, Pin.OUT)

while True:
    if button.value():
        led.value(1)
    else:
        led.value(0)
```

### Lesson 3 — “Talk to Your Robot”
Goal:
  * Communication = real power

* Lab
  * print to serial
  * read simple input from PC
 
Code:
```
while True:
    cmd = input("Enter command: ")
    
    if cmd == "on":
        led.value(1)
        print("LED ON")
    elif cmd == "off":
        led.value(0)
        print("LED OFF")
```
Key take aways:
  * serial = communication between PC and robot
  * input() waits for user
  * print() sends data back


Similar Course Using the Arduino with Robotics
1. Arduino (C/C++)
* low-level
* deterministic
* classic robotics
* ROS 1 bridge
  
2. Pico (MicroPython)
* faster iteration
* easier learning curve
* modern workflow
* stepping stone to ROS 2 concepts
* dual processor cores

  
