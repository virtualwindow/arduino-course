# GDE_302 Game Technology (Arduino 1)

Welcome to this course. It's going to be a fun one.

Watch this video: [Youtube Arduino TED talk](https://www.youtube.com/embed/UoBUXOOdLXY)

Arduino senses the environment by receiving inputs from many sensors, and affects its surroundings by controlling lights, motors, and other actuators. We can use it to build almost any game controller, or arcade like interactive installations.



## Setup and blinking an LED light

Let's get your arduino up and running. Connect your arduino through USB to a computer. Get the arduino software from [arduino.cc](http://arduino.cc/)

If on Windows see [how to install the device driver](http://www.arduino.cc/en/Guide/UnoDriversWindowsXP)

**Connect an LED between pin 13 and GND**

Ideally you should put a resistor in between pin 13 and the LED to reduce the current draw that can cause damage to the arduino. For simplicity we disregard that for now.

![Imgur](http://i.imgur.com/bmLr5owm.jpg)

Run the Arduino software  
Go to Tools > Port > Choose your arduino **port**  
Go to File > Examples > 01.Basics > **Blink**  
**Upload the program** by clicking the round arrow button in the top left.

![Imgur](http://i.imgur.com/nw4fo2h.png)

Turns on an LED on for one second, then off for one second, repeatedly. Most Arduinos have an on-board LED you can control. On the Uno and Leonardo, it is attached to digital pin 13.

See the [Arduino Reference](http://www.arduino.cc/en/Reference/HomePage) documentation on [pinMode](http://arduino.cc/en/Reference/PinMode)(), [digitalWrite](http://arduino.cc/en/Reference/DigitalWrite)() and [delay](http://arduino.cc/en/Reference/Delay)()

**Further practice: Build a circuit and program the arduino to signal [SOS](http://en.wikipedia.org/wiki/SOS).**  
**Further practice: Build a circuit and program the arduino to control three LED lights, similar to a [traffic signal robot](http://georgefrancisonline.homestead.com/WALKER_BROS_ANIMATION.gif).**

## Measuring votage and light

The arduino can use the A0-A5 inputs to measure voltage between 0-5 Volts as a 10bit number. This results in 5 volts reading as 1023, the highest number that can be represented by 10bits.  For this lesson you'll need a LDR (Light sensor) and a resistor that has roughly the same resistance as the light sensor. In our case its 10k ohm.

The circuit we'll build is generally called a voltage divider circuit. It's called this because we have two resistors dividing the power and we measure inbetween them. With a LDR we'll measure a different voltage depending on how much light falls on the LDR.

![Imgur](http://i.imgur.com/31LEYXK.jpg)

Arduino  5V to LDR  
Arduino GND to Resistor  
Arduino  A0 to LDR and Resistor  

Go to **File > Examples > 01.Basics > AnalogReadSerial**

![Imgur](http://i.imgur.com/E9wIrAn.jpg)

Open **Tools > Serial Monitor** and you should see the output from the sensor change as you limit the amount of light that falls onto the LDR with your hand.

**Further practice: Build a circuit and program the arduino to switch a LED on or off when you block light to the LDR.**

## Measuring rotation and acceleration

For this lesson we use a [Pololu AltIMU 10 v3](https://www.pololu.com/product/2469).

First solder on some connecting pins to the AltIMU. Be sure not to connect VDD, as this pin is easily damaged with 5V power. Only connect VIN, GND, SDA, SCL.

![Imgur](http://i.imgur.com/QKgOI41.jpg)

Connect the AltIMU to your Arduino UNO. The Arduino UNO's A4 and A5 pins double as SDA and SCL pins.

AltIMU VIN to Arduino 5V  
AltIMU GND to Arduino GND  
AltIMU SDA to Arduino A4  
AltIMU SCL to Arduino A5  

![Imgur](http://i.imgur.com/JHv2nYV.jpg)

Download and install the arduino libraries for the AltIMU. Here are links to the [L3G library](https://github.com/pololu/l3g-arduino) and [LSM303](https://github.com/pololu/lsm303-arduino). These should be extracted to Documents/Arduino/Libraries.

Restart the arduino software to load the new libraries.

Open **File > Examples > L3G > Serial** for the gyro sensor which will show you rotational velocity. You'll see its not quite zero as gyro sensors do have a slight drift over time.

Alternatively open **File > Examples > LSM303 > Serial** for the accelerometer and magnetometer output.

Open **Tools > Serial Monitor** and you should see the output from the sensor change as you move it around with your hand.

![Imgur](http://i.imgur.com/jfcSzfl.jpg)

You can combine the code to use all the sensors at once to form a vector representation of the current orientation in relation to gravity. See the quaternion vector rotation article on bitlab.io for more.
