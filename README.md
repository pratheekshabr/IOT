# IOT
<B><h2>1.Using 3LED and registers</b></h2><BR>
void setup() {<br>
pinMode(12, OUTPUT);<br>
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
******************************
   <b><h2>2.RGB</h2></b><br>
  void setup() {<br>
  // put your setup code here, to run once:<br>
  pinMode(13, OUTPUT);<br>
  pinMode(10, OUTPUT);<br>
  pinMode(8, OUTPUT);<br>
  }
void loop() {<br>
  // put your main code here, to run repeatedly:<br>
 displayColor(0b100);<br>
 delay(1000);<br>
 displayColor(0b010);<br>
 delay(1000);<br>
displayColor(0b001);<br>
delay(1000);<br>
displayColor(0b101);<br>
delay(1000);<br>
displayColor(0b011);<br>
delay(1000);<br>
displayColor(0b110);<br>
delay(1000);<br>
displayColor(0b111);<br>
delay(1000);<br>
}<br>
void displayColor(byte color) {<br>
 digitalWrite(13, !bitRead(color, 2));<br>
 digitalWrite(10, !bitRead(color, 1));<br>
 digitalWrite(8, !bitRead(color, 0));<br>
}<br>
  output:<br>
  ![image](https://user-images.githubusercontent.com/97940277/175903580-a0b0a926-0ca1-478d-b6e3-f0308ef8a8d5.png)<br>

  
**************************************
<h1>4.<b>servo motor</b></h1><br>
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
<h2><b>5.servo motor using for loop</b></h2><br>
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
 <h2><b> 6.servo motor and slide potentiometer</b></h2><br><br>
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

<h2>.<b>Buzzer arduino resistor</b></h2><br>
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
<h2><b>buzzer with button</b></h2><br><br><br>
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
<h2>6.<b>Ultrasonic sensor</b></h2><br>
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

<h2><b>Ultrasonic sensor with buzzer</b></h2><br>
// constants won't change<br>
const int TRIG_PIN   = 6; // Arduino pin connected to Ultrasonic Sensor's TRIG pin<br>
const int ECHO_PIN   = 7; // Arduino pin connected to Ultrasonic Sensor's ECHO pin<br>
const int BUZZER_PIN = 3; // Arduino pin connected to Piezo Buzzer's pin<br>
const int DISTANCE_THRESHOLD = 50; // centimeters<br>
<br>
// variables will change:<br>
float duration_us, distance_cm;<br>

void setup() {<br>
  Serial.begin (9600);         // initialize serial port<br>
  pinMode(TRIG_PIN, OUTPUT);   // set arduino pin to output mode<br>
  pinMode(ECHO_PIN, INPUT);    // set arduino pin to input mode<br>
  pinMode(BUZZER_PIN, OUTPUT); // set arduino pin to output mode<br>
}

void loop() {<br>
  // generate 10-microsecond pulse to TRIG pin<br>
  digitalWrite(TRIG_PIN, HIGH);<br>
  delayMicroseconds(10);<br>
  digitalWrite(TRIG_PIN, LOW);<br>

  // measure duration of pulse from ECHO pin<br>
  duration_us = pulseIn(ECHO_PIN, HIGH);<br>
  // calculate the distance<br>
  distance_cm = 0.017 * duration_us;<br>

    if(distance_cm < DISTANCE_THRESHOLD)
   { digitalWrite(BUZZER_PIN, HIGH);
    tone(BUZZER_PIN,1000);
 } // turn on Piezo Buzzer
  else
  {
    digitalWrite(BUZZER_PIN, LOW); 
   noTone(BUZZER_PIN);    
  }    // turn off Piezo Buzzer


  // print the value to Serial Monitor<br>
  Serial.print("distance: ");<br>
  Serial.print(distance_cm);<br>
  Serial.println(" cm");<br>

  delay(500);<br>
}<br>

![image](https://user-images.githubusercontent.com/97940277/174784004-d5f12b64-16ed-44f1-8695-d5b3cc4fdb96.png)<br>
************************
<br> <b><h2>11.Ultrasonic sensor with buzzer</h2></b><br>
  *************************
  int const trigPin = 9;<br>
int const echoPin = 10;<br>
int const buzzPin = 2;<br>
int const ledPin = 3;<br>
long duration;<br>
int distance;<br>
const int DISTANCE_THRESHOLD = 100; <br>
void setup()<br>
{<br>
Serial.begin (9600); <br> <br>
pinMode(trigPin, OUTPUT); // trig pin will have pulses output<br>
pinMode(echoPin, INPUT); // echo pin should be input to get pulse width<br>
pinMode(buzzPin, OUTPUT);<br>
pinMode(ledPin, OUTPUT); // buzz pin is output to control buzzering<br>
}<br>
void loop()<br>
{<br>
// Duration will be the input pulse width and distance will be the distance to the obstacle in centimeters<br>
int duration, distance;<br>
// Output pulse with 1ms width on trigPin<br>
digitalWrite(trigPin, HIGH);<br>
delay(1);<br>
digitalWrite(trigPin, LOW);<br>
// Measure the pulse input in echo pin<br>
duration = pulseIn(echoPin, HIGH);<br>
// Distance is half the duration devided by 29.1 (from datasheet)<br>
distance= 0.017 * duration;<br>
// if distance less than 0.5 meter and more than 0 (0 or less means over range)<br>
if (distance>DISTANCE_THRESHOLD) <br>
{<br>
// Buzz<br>
tone(2,500);<br>
digitalWrite(buzzPin, HIGH);<br>
digitalWrite(ledPin, HIGH);<br>
} else {<br><br>
// Don't buzz<br>
noTone(2);<br>
digitalWrite(buzzPin, LOW);<br>
digitalWrite(ledPin, LOW);<br>
}<br>
// Waiting 60 ms won't hurt any one<br>
//Serial.print("distance: ");<br>
//Serial.print(distance);<br>
//Serial.println(" cm");<br>

delay(100);<br>
}<br>
 Output:<br>
  ![image](https://user-images.githubusercontent.com/97940277/175915676-8df399a4-e320-49a7-bc20-cf6443a1425f.png)<br>

  








  



