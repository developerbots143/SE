35192 gm.l.com

Q Introduction to Arduino uno and Breadboard blinking the LED’s.

// C++ code
//
void setup()

{

  pinMode(13, OUTPUT);
  
}

void loop()

{
  digitalWrite(13, HIGH);
  
  delay(1000); // Wait for 1000 millisecond(s)
  
  digitalWrite(13, LOW);
  
  delay(1000); // Wait for 1000 millisecond(s)
  
}

<p align="center"><a href="https://githu.coms"><img src="https://graph.org/file/5c85a3033ce7369908470-78935650020b33a24e.jpg" width="400"></a></p>

Q2 Program Arduino uno using Light Sensitive Sensor.

int sensorValue=0;

void setup(){

 pinMode(A0,INPUT);
 
 pinMode(9,OUTPUT);
 
 Serial.begin(9600);
 
}

void loop(){

 sensorValue=analogRead(A0);
 
 Serial.println(sensorValue);
 
 int 

fade=map(sensorValue,0,1023,255,0);

 Serial.println(fade);
 
 analogWrite(9,fade);
 
 delay(1000);
 
}

second 
// C++ code // int sensorValue=0; void setup() { pinMode(A0, INPUT); pinMode(9, OUTPUT); Serial.begin(9600); } void loop() { sensorValue=analogRead(A0); Serial.println(sensorValue); analogWrite(9,map(sensorValue,0,1023,255,0)); delay(1000); }

<p align="center"><a href="https://githu.com"><img src="https://graph.org/file/5fb511ef2fd4002910732-fc5a2841bebd05ab17.jpg" width="400"></a></p>

Q3 Program Arduino uno using Temperature Sensor.

char degree = 176; 

const int sensor = A1; 

void setup() {

  pinMode(sensor, INPUT); 
  
  Serial.begin(9600); 
  
}
void loop() {

  int temp = analogRead(sensor);
  
  float voltage = (temp * 5.0) / 1024.0; 
  
  float tempCel = (voltage - 0.5) * 100.0; 
  
  Serial.print("Celsius: ");
  Serial.print(tempCel); 
  Serial.print(" ");
  Serial.print(degree); 
  Serial.println("C"); 
  
  delay(1000); 
  
}

second
// C++ code // int sensorValue=0; void setup() { pinMode(A0, INPUT); pinMode(9, OUTPUT); Serial.begin(9600); } void loop() { sensorValue=analogRead(A0); Serial.println(sensorValue); analogWrite(9,map(sensorValue,0,1023,255,0)); delay(1000); }

<p align="center"><a href="https://githu.com"><img src="https://graph.org/file/701bbfb6f76c353d75972-6d2aeecd8b9a16ba1e.jpg" width="400"></a></p>

Q4 Program Arduino uno using Humidity Sensor

const int AnalogIn=A1;

int humiditySensorOutput=0;

void setup(){

Serial.begin(9600);

}

void loop(){

humiditySensorOutput=analogRead(AnalogIn);

  int 
  humidityPercentage=map(humiditySensorOutput,0,1023,10,70);
  
  Serial.print("humidity:=");
  
  Serial.print(humidityPercentage);
  
  Serial.println("%");
  
  delay(5000);
  
}
second

const int AnalogIn=A1; int humiditySensorOutput=0; void setup() { Serial.begin(9600); } void loop() { humiditySensorOutput=analogRead(AnalogIn); int humidityPercentage=map(humiditySensorOutput,0,1023,10,70); Serial.print("Humidity:= "); Serial.print(humidityPercentage); Serial.println("%"); delay(5000);//Wait for 1000 millisecond(a) }


<p align="center"><a href="https://githu.com"><img src="https://graph.org/file/09be165b1d83c6879cd99-c6f248f0bd45c2f885.jpg" width="400"></a></p>

Q5 Program Arduino uno using Ultra Sonic Sensor.

const int trigPin=9;
const int echoPin=10;

long duration;
float distance;

void setup(){

  Serial.begin(9600);
  
  pinMode(trigPin,OUTPUT);
  
  pinMode(echoPin,INPUT);
  
}

void loop(){

digitalWrite(trigPin,LOW);

delayMicroseconds(2);

digitalWrite(trigPin,HIGH);

delayMicroseconds(10);

digitalWrite(trigPin,LOW);

duration=pulseIn(echoPin,HIGH);

distance=(duration*0.0343)/2;
  
Serial.print("distance:");
Serial.print(distance);
Serial.println("cm");

delay(500);
}

second
const int trigPin=9; const int echoPin=10; long duration; float distance; void setup() { Serial.begin(9600); pinMode (trigPin, OUTPUT); pinMode (echoPin, INPUT); } void loop() { digitalWrite (trigPin, LOW); delayMicroseconds (2); digitalWrite(trigPin, HIGH); delayMicroseconds (10); digitalWrite(trigPin, LOW); duration= pulseIn(echoPin, HIGH); distance= (duration * 0.0343) / 2; Serial.print("Distance: "); Serial.print(distance); Serial.println("cm"); delay(500); }

<p align="center"><a href="https://githu.com"><img src="https://graph.org/file/2ee011df6e85dd603c541-53a081a2a95e801f11.jpg" width="400"></a></p>

Q6 Program Arduino uno using PIR Sensor.

const int pirpin = 2;
const int ledpin = 13;
int pirState = LOW;

void setup() {

  pinMode(pirpin, INPUT);
  
  pinMode(ledpin, OUTPUT);
  
  Serial.begin(9600);
}

void loop() {

  int motionDetected = digitalRead(pirpin);

  if (motionDetected == HIGH)
  
  {
  
    digitalWrite(ledpin, HIGH); 
    
    if (pirState == LOW) 
    
    {
    
      Serial.println("Motion Detected!");
      
      pirState = HIGH;
      
    }
    
  } 
  
  else {
  
    digitalWrite(ledpin, LOW);
    
    if (pirState == HIGH) {
      Serial.println("Motion Ended");
      
      pirState = LOW;
      
    }
    
  }
  
  delay(200);
}

second
const int pirpin=2; const int ledpin=13; int pirState=LOW; void setup() { pinMode(pirpin,INPUT); pinMode(ledpin,OUTPUT); Serial.begin(9600); } void loop(){ int motionDetected=digitalRead(pirpin); if(motionDetected==HIGH){ digitalWrite(ledpin,HIGH); if(pirState==LOW);{ Serial.println("Motion Detected!"); pirState=HIGH; } } else{ digitalWrite(ledpin,LOW); if(pirState==HIGH){ Serial.println("Motion Ended!"); pirState=LOW; } } delay(200); }

<p align="center"><a href="https://githu.com"><img src="https://graph.org/file/e782a5587c12d2a4de075-a3eb6452e1e29238ac.jpg" width="400"></a></p>

Q7 Program Arduino uno using Servo motor

#include<Servo.h>

Servo myServo;

void setup()

{

  myServo.attach(9);
  
}

void loop(){

  myServo.write(0);
  delay(1000);
  myServo.write(90);
  delay(1000);
  myServo.write(180);
  delay(1000);

}

second
#include<Servo.h> Servo myServo; void setup() { myServo.attach(9); } void loop() { myServo.write(0); delay(1000); myServo.write(90); delay(1000); myServo.write(180); delay(1000); }


<p align="center"><a href="https://githu.com"><img src="https://graph.org/file/e0717fddcce8fc3879a16-83486db5919150af31.jpg" width="400"></a></p>


