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

********************************************
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
*********************************
 <b> servo motor and slide potentiometer</b><br><br>
  #include <Servo.h><br>
Servo Servo1;<br>
int potpin=A0;<br>
int val;<br>

void setup()<br>
{<br>
  Servo1.attach(3);<br>
}<br>
void loop()<br>
{<br>
 val=analogRead(potpin);<br>
 val=map(val,A0,1023,0,180);<br>
 Servo1.write(val);<br>
 delay(15);<br>
}<br>
output:<br>
![image](https://user-images.githubusercontent.com/97940277/174588958-e1243d5b-fd7e-4f3a-b3a1-ff40647dadcd.png)<br>
***********************************

5.<b>Buzzer arduino resistor</b><br>
void setup() {pinMode(5, OUTPUT);<br>
  // put your setup code here, to run once:<br>

}<br>

void loop() {<br><br>
tone(5,1000);<br>
delay(10000);<br>
noTone(5);<br>
delay(1000);  // put your main code here, to run repeatedly:<br>
}<br>
![image](https://user-images.githubusercontent.com/97940277/174762286-3f8858b0-13d7-4f22-a71f-e1a40d2c6bdf.png)<br>

**************************************************
<b>buzzer with button</b><br><br><br>
const int Button_Pin=7;<br><br>
const int Buzzer_Pin=3;<br><br>
void setup() {<br><br>
  Serial.begin(9600);<br><br>
  pinMode(Button_Pin,INPUT_PULLUP);<br><br>
  pinMode(Buzzer_Pin,OUTPUT);<br>

  // put your setup code here, to run once:<br>

}<br>
<br>
void loop() {<br>
  int buttonState=digitalRead(Button_Pin);<br>
  if(buttonState==LOW)<br>
  {<br>
    //Serial.println("the button is being pressed");<br>
    digitalWrite(Buzzer_Pin,HIGH);<br>
    tone(Buzzer_Pin,1000);<br>
  
  }<br>
  else<br>
  if(buttonState==HIGH)<br>
  {<br>
     //Serial.println("the button is being unpressed");<br>
      digitalWrite(Buzzer_Pin,LOW);<br>
      noTone(Buzzer_Pin);<br>
      
  }<br>
 
  // put your main code here, to run repeatedly:<br>

}<br>
![image](https://user-images.githubusercontent.com/97940277/174771113-952423cd-a099-4c5d-976d-09ac6ca05445.png)<br>
**************
6.<b>Ultrasonic sensor</b><br>
<br>const int pingPin = 2; // Trigger Pin of Ultrasonic Sensor<br>
const int echoPin = 5; // Echo Pin of Ultrasonic Sensor<br>
<br>
void setup() {<br>
   Serial.begin(9600); // Starting Serial Terminal<br>
}<br>

void loop() {<br>
   long duration, inches, cm;<br>
   pinMode(pingPin, OUTPUT);<br>
   digitalWrite(pingPin, LOW);<br>
   delayMicroseconds(2);<br>
   digitalWrite(pingPin, HIGH);<br>
   delayMicroseconds(10);<br>
   digitalWrite(pingPin, LOW);<br>
   pinMode(echoPin, INPUT);<br>
   duration = pulseIn(echoPin, HIGH);<br>
   inches = microsecondsToInches(duration);<br>
   cm = microsecondsToCentimeters(duration);<br>
   Serial.print("the distance is");<br>
   Serial.print(inches);<br>
   Serial.print("in, ");<br>
   Serial.print(cm);<br>
   Serial.print("cm");<br>
   Serial.println();<br>
   delay(100);<br>
}<br>

long microsecondsToInches(long microseconds) {<br>
   return microseconds / 74 / 2;<br>
}<br>

long microsecondsToCentimeters(long microseconds) {<br>
   return microseconds / 29 / 2;<br>
}<br>


![image](https://user-images.githubusercontent.com/97940277/174776916-0086423f-0e71-4610-b8d2-87bf6066ecf4.png)<br>









  



