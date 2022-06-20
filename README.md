# IOT
1.void setup() {pinMode(12, OUTPUT);<br>
pinMode(13,OUTPUT);<br>
pinMode(8, OUTPUT);<br>
  // put your setup code here, to run once:<br>

}<br>

void loop() {digitalWrite(12, HIGH);<br>
delay(1000);<br>
digitalWrite(12, LOW);<br>
digitalWrite(13,HIGH);<br>
delay(1000);<br>
digitalWrite(13,LOW);<br>
digitalWrite(8, HIGH);<br>
delay(1000);<br>
digitalWrite(8, LOW);<br>
delay(1000);<br>
  // put your main code here, to run repeatedly:<br>

}<br>
![image](https://user-images.githubusercontent.com/97940277/174572324-03480b82-d883-404c-9309-0e20fb32557c.png)<br>

**************************************
4.#include <Servo.h><br>
int servopin=3;<br>
Servo Servo1;<br>
void setup()<br>
{<br>
  Servo1.attach(servopin);<br>
}<br>
void loop()<br>
{<br>
  Servo1.write(0);<br>
  delay(1000);<br>
  Servo1.write(90);<br>
  delay(1000);<br>
  Servo1.write(180);<br>
  delay(1000);<br>
}<br>


