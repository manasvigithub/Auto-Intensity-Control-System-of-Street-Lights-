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
   • Function: Acts as the main controller of the project, processing inputs from the sensors (RTC and LDR) and controlling the output to the LEDs.
   • Role: Runs the program that determines when and how to adjust the street light intensity based on the inputs.
  
2) DS3231 RTC Module
   • Function: Provides real-time clock functionality, keeping accurate time even when the Arduino is powered off.
   • Role: Allows the system to operate in RTC Mode, where street lights turn on and off based on predefined times set in the code.
   
3) LDR (Light Dependent Resistor)
   • Function: Senses the ambient light levels.
   • Role: Enables the system to operate in LDR Mode, where the intensity of the street lights is adjusted based on the amount of natural light present.
     Higher ambient light leads to lower intensity of the LEDs and vice versa.

4) 16×2 LCD Display
   • Function: Displays information such as the current mode (RTC or LDR), time, and ambient light level.
   • Role: Provides a user interface to monitor the system’s status and operations.

5) LED
   • Function: Acts as the street light in the project prototype.
   • Role: Demonstrates how the intensity of the actual street lights would be controlled. Multiple LEDs can represent multiple street lights.

6)  10KΩ Potentiometer
   • Function: Adjusts the contrast of the LCD display.
   • Role: Ensures the display is readable by allowing the user to set the optimal contrast level.

7)  10KΩ Resistor
   • Function: Limits the current flowing through the LDR and the push button.
   • Role: Protects the components from excessive current, ensuring the circuit operates safely.

8)  Push Button
   • Function: Acts as a manual switch to change the mode of operation between RTC Mode and LDR Mode.
   • Role: Allows the user to switch the control mode of the street lights, providing flexibility in operation.

9)  Connecting Wires
    • Function: Connect all the components in the circuit.
    • Role: Facilitate the electrical connections necessary for the components to communicate and function together.

10) Breadboard
    • Function: Provides a platform to build the circuit without soldering.
    • Role: Allows for easy assembly and modification of the circuit during prototyping and testing.


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
