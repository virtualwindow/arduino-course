# GDE_302 Game Technology (Arduino 1)

Welcome to this course. It's going to be a fun one. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/UoBUXOOdLXY" frameborder="0" allowfullscreen></iframe>

Arduino senses the environment by receiving inputs from many sensors, and affects its surroundings by controlling lights, motors, and other actuators. We can use it to build almost any game controller, or arcade like interactive installations.



## Setup and blinking an LED light

Let's get your arduino up and running. Connect your arduino through USB to a computer. Get the arduino software from [arduino.cc](http://arduino.cc/)

If on Windows see [how to install the device driver](http://www.arduino.cc/en/Guide/UnoDriversWindowsXP)

**Connect an LED between pin 13 and GND** 

![Imgur](http://i.imgur.com/bmLr5owm.jpg)

Run the Arduino software  
Go to Tools > Port > Choose your arduino **port**  
Go to File > Examples > 01.Basics > **Blink**  
**Upload the program** by clicking the round arrow button in the top left.

![Imgur](http://i.imgur.com/nw4fo2h.png)

Turns on an LED on for one second, then off for one second, repeatedly. Most Arduinos have an on-board LED you can control. On the Uno and Leonardo, it is attached to digital pin 13. 

See the [Arduino Reference](http://www.arduino.cc/en/Reference/HomePage) documentation on [pinMode](http://arduino.cc/en/Reference/PinMode)(), [digitalWrite](http://arduino.cc/en/Reference/DigitalWrite)() and [delay](http://arduino.cc/en/Reference/Delay)()


