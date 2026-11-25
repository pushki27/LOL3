#include <Servo.h>

Servo myServo;
int joystickPin = A0; // ADC0
int servoPin = 15;    // GP15 PWM

void setup() {
  myServo.attach(servoPin);
}

void loop() {
  int joystickValue = analogRead(joystickPin); // 0 - 1023
  int angle = map(joystickValue, 0, 1023, 0, 180); // Linear mapping
  myServo.write(angle);
  delay(15);
}
