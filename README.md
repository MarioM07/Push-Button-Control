#include <Servo.h>
Servo servo1;
void setup() {
pinMode(13,OUTPUT);
pinMode(2,INPUT);
servo1.attach(9);
}


void loop() {
  servo1.write(0);
  delay(1000);
  servo1.write(90);
  delay(1000);
  servo1.write(180);
  delay(1000);
  servo1.write(90);
  delay(1000);
 int botton=digitalRead(2);
 if (botton==LOW){  //Read the botton state
 digitalWrite(13,HIGH);
 int dial = analogRead(0);
 tone(9,440);
 delay(500);
 delay(dial);
 }else{ // Botton is not pressed
 digitalWrite(13,LOW);
 noTone(9);
 delay(200);
 //delay(dial);
}
}
