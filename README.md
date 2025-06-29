# AutomaticRailway-Gate-Control
""Arduino-based railway gate control system simulated in Tinkercad. Uses IR sensors, servo motor, and buzzer." simulated in Tinkercad. Uses IR sensors, servo motor, and buzzer."
# Automatic Railway Gate Control System

Simulated using Arduino and Tinkercad. Detects train using IR sensors and automatically closes/opens gate with a servo motor.

## 🔗 Tinkercad Simulation
[Click here to view the simulation](PASTE_YOUR_TINKERCAD_LINK_HERE)

## 💻 Tools Used
- Arduino UNO
- IR Sensors
- Micro Servo Motor
- Buzzer (optional)
- Tinkercad Circuits

## 👩‍💻 Code (Arduino Sketch)
```cpp
#include <Servo.h>
Servo gate;
int sensor1 = 2;
int sensor2 = 3;
int buzzer = 8;
void setup() {
  pinMode(sensor1, INPUT);
  pinMode(sensor2, INPUT);
  pinMode(buzzer, OUTPUT);
  gate.attach(9);
  gate.write(90);
}
void loop() {
  if (digitalRead(sensor1) == LOW || digitalRead(sensor2) == LOW) {
    digitalWrite(buzzer, HIGH);
    gate.write(0);
    delay(5000);
    gate.write(90);
    digitalWrite(buzzer, LOW);
  }
}

