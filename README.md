OVERVIEW
- Implemented an Arduino based system utilizing a combination of RTC Module (DS3231) and LDR for controlling the street lights.
- It is designed to automatically adjust the intensity of street lights depending on the ambient lighting conditions in order to save energy to some extent.


INTRODUCTION

Auto Intensity Control of Street Lights is a simple project where the intensity of the street lights is automatically controlled based on the sunlight conditions. 
Generally, street lights are turned on during evening time and continue to glow till morning. This might result is unnecessary usage of power as the lights will be 
glowing at full intensity all the times. But employing the Auto Intensity Control of Street Lights using Arduino project, you can control the intensity based on 
the ambient lighting conditions.

As an additional power saving feature, LEDs have been used for street lights.


COMPONENTS

1) Arduino UNO
2) DS3231 RTC Module
3) LDR
4) 16×2 LCD Display
5) LED
6)  10KΩ Potentiometer
7)  10KΩ Resistor
8)  Push Button
9)  Connecting Wires
10) Breadboard


WORKING

Basically, there are two modes of operation of this project: RTC Mode and LDR Mode. 
In RTC Mode, the street lights turn on automatically based on the ON Time set in the code and turn off based on the OFF Time. 
In the LDR Mode, the street lights have an intensity control based on the ambient light near the LDR.

After making the connections and uploading the code to Arduino, we have to turn on the Power supply to the project. 
Initially, the Arduino runs in RTC Mode where there are two times set in the code: the ON TIME and the OFF TIME. Arduino compares the ON TIME with the time from
RTC Module and when they match, the LED is turned ON. After this, the Arduino waits for the OFF TIME and once the time from RTC Module reaches the OFF TIME, the
LED is turned OFF. 

During anytime of this operation, if the button (connected as an external interrupt to Pin 2) is pushed, the Arduino enters LDR Mode. In this mode, the Arduino
reads the value of the LDR from A3 and based on the value, it adjusts the intensity of the LED. 

In order to switch back to RTC Mode, all we have to do is push the button.
