# Ultrasonic Sensor Task

Welcome to the Ultrasonic Sensor task! This task demonstrates how to use an ultrasonic sensor with an Arduino to measure distances. Ultrasonic sensors are commonly used in robotics and automation for obstacle detection, distance measurement, and more. This task will guide you through the basics of ultrasonic sensor interfacing and help you get started with your own distance sensing tasks.

## Introduction

The Ultrasonic Sensor task aims to provide a practical example of using an ultrasonic sensor with an Arduino microcontroller to measure distances. Ultrasonic sensors work by emitting high-frequency sound waves and measuring the time it takes for the sound waves to bounce off an object and return to the sensor. By calculating the time difference, the sensor can determine the distance to the object.

## How it Works

The task works by sending a trigger signal to the ultrasonic sensor to initiate a measurement. The sensor then emits ultrasonic pulses and waits for the reflected pulses to return. By measuring the time it takes for the pulses to return, the Arduino can calculate the distance to the object in front of the sensor using the speed of sound.

## Getting Started

To get started with this task, you will need the following components:

- Arduino board (e.g., Arduino Uno)
- Ultrasonic sensor (e.g., HC-SR04)
- Jumper wires

## Steps

Follow these steps to set up the task:

1. Connect the VCC pin of the ultrasonic sensor to the 5V pin on the Arduino.
2. Connect the GND pin of the ultrasonic sensor to the GND pin on the Arduino.
3. Connect the TRIG pin of the ultrasonic sensor to a digital pin on the Arduino pin 12.
4. Connect the ECHO pin of the ultrasonic sensor to another digital pin on the Arduino pin 11.
5. Ensure all connections are secure.

| Arduino Pin    | Ultrasonic Sensor Pin |
| -------------- | ----------------------|
| 5V             | VCC                   |
| GND            | GND                   |
| Digital (12)   | TRIG                  |
| Digital (11)   | ECHO                  |

## Connection

The following table summarizes the wiring connections between the Arduino and the ultrasonic sensor:

 ![screen-gif](https://github.com/ItsRawanMoha/Ultrasonic-Sensor/blob/main/UltraSDia.png)

## Output

Once the circuit is set up and the code is uploaded to the Arduino board, the ultrasonic sensor will be able to measure distances to objects in front of it.

## Code
```
// defines arduino pins numbers
const int trigPin = 12;
const int echoPin = 11;
long duration;
int distance;
void setup() 
{
pinMode(trigPin, OUTPUT); // Sets the trigPin as an Output
pinMode(echoPin, INPUT); // Sets the echoPin as an Input
Serial.begin(9600); // Starts the serial communication
}
void loop() {
// Clears the trigPin
digitalWrite(trigPin, LOW);
delayMicroseconds(2);
// Sets the trigPin on HIGH state for 10 micro seconds
digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);
// Reads the echoPin, returns the sound wave travel time in microseconds
duration = pulseIn(echoPin, HIGH);
// Calculating the distance
distance= duration*0.034/2;
// Prints the distance on the Serial Monit
Serial.print("Distance from the object = ");
Serial.print(distance);
Serial.println(" cm");
delay(1000);

}
```
## Pictures 

<img src="https://github.com/ItsRawanMoha/Ultrasonic-Sensor/blob/main/UltraS.jpeg" alt="Alt text" width="300" height="300">

![screen-gif](https://github.com/ItsRawanMoha/Ultrasonic-Sensor/blob/main/UltraS.png)

## Conclusion

The Ultrasonic Sensor task provides a hands-on introduction to using ultrasonic sensors for distance measurement with Arduino. By understanding the principles behind ultrasonic sensing, you can explore more advanced applications and tasks involving obstacle detection, navigation, and more.
