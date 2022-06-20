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
4.<b>servo motor</b><br>
#include <Servo.h><br>
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


<b>servo motor using for loop</b><br>
// Include the Servo library <br>
#include <Servo.h> <br>
 int servoPin=3;<br>
 int i=0;<br>
Servo Servo1; <br>
               

void setup() {<br>
   // We need to attach the servo to the used pin number <br>
   Servo1.attach(servoPin);<br>
   
}<br>
  void loop() {<br>
  // put your main code here, to run repeatedly:<br>
   // Make servo go to 0 degrees <br>
   for(i= 0; i< 180; i += 1)  <br>
  {   <br>                              
    Servo1.write(i); <br>          
    delay(15);      <br>                
  } 
  for(i = 180; i>=1; i-=1)   <br> 
  {       <br>                         
   Servo1.write(i); <br>             
    delay(15);    <br>                   
  } <br>
  }<br>
  ![image](https://user-images.githubusercontent.com/97940277/174584875-35b401b7-55e5-4a0f-9f1f-1b2b7272c518.png)<br>

   
  



