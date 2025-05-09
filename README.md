# Potensiometer-Servo-Control

Bu layihədə, potensiometr istifadə edərək servo motorunun bucağını idarə edirik. Potensiometrin döndürülməsi ilə servo motorunun bucağı dəyişir.

## Komponentlər:
- Arduino Uno
- Potensiometr
- Servo Motor
- Breadboard
- Jumper Kabelləri

## Quruluş:
1. **Potensiometrin qoşulması:**
   - VCC -> 5V
   - GND -> GND
   - Sinyal -> A0

2. **Servo motorunun qoşulması:**
   - PWM pin -> D9
   - VCC -> 5V
   - GND -> GND
  
## Tinkercad Simulyasiya Linki:
https://www.tinkercad.com/things/f505NEH837B-incredible-tumelo

## Kod:

#include <Servo.h>  

Servo myServo;  

int potPin = A0;  
int potValue = 0;  
int angle = 0;  

void setup() {
  myServo.attach(9);  
}

void loop() {
  potValue = analogRead(potPin);  
  angle = map(potValue, 0, 1023, 0, 180);  
  myServo.write(angle);  
  delay(15); 
}

