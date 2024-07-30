# Analog-Digital-circuit


Electronics-week-4-tasks
Task 1: Building an arduino circuit for Analog input (Photoresistor sensor)

Building the Arduino circuit with analog input:

Click on create new Circuit.
From the search tool, get:
```
i. Breadboard 

ii. Arduino uno r3

iii. Oscilloscope

iv. resistor 220 ohm

v. two resistors 1k ohm

vi. Photoresistor

vii. LED
```


Connect the circuit as shown below:
Analog circuit



![Analog circuit](https://github.com/user-attachments/assets/297726d8-d1a1-4c81-ab91-088bb0f8c635)






use the following code to simulate the Analog input arduino circuit:
// Initialisation 
```
const int analogInPin = A0;     
const int analogOutPin = 9;     
const int analogBuzPin = 8;     

int sensorValue = 0;   
int outputValue = 0;  
int buzValue = 0;      

void setup() {
  
  Serial.begin(9600);
  
  
  pinMode(analogOutPin, OUTPUT);      
  
  pinMode(analogInPin, INPUT); 

  pinMode(analogBuzPin,OUTPUT);
}

void loop() {

  sensorValue = analogRead(analogInPin);            
  
  outputValue = map(sensorValue, 0, 1023, 0, 255);  
  
  analogWrite(analogOutPin, outputValue);           
  
  buzValue = map(sensorValue, 0, 1023, 50, 30000);     
  
  tone(analogBuzPin, buzValue);
  
 
  Serial.print("sensor = " );                       
  Serial.print(sensorValue);      
  Serial.print("\t output = ");      
  Serial.print(outputValue);
  Serial.print("\t frequence = ");
  Serial.println(buzValue);
}
  ```

   
Click on start Simulation if you change the light indicator on the Photoresistor, the osoloscope will show a signal for the analog input.


![output](https://github.com/user-attachments/assets/6c0c8c50-16bc-409d-b039-84463588f634)



Task 2: Building an arduino circuit for Digital input (Push button)



Building the Arduino circuit with digital input

Click on create new Circuit.
From the search tool, get:
```
i. Breadboard 

ii. Arduino uno r3

iii. resistor 1k ohm

iv. resistors 10k ohm

v. push button

vi. LED
```

Connect the circuit as shown below:
Copy of Blink and Read Digital Signal


![Digital circuit push button](https://github.com/user-attachments/assets/ed4a63c5-3fcb-426e-931d-0c4236a5b0bf)



use the following code to simulate the Analog input arduino circuit:
// C++ code
```
/*
  This program blinks pin 13 of the Arduino (the
  built-in LED)
*/

int buttonPin = 12;
int ledPin = 13;
int val = 0;

void setup()
{
  pinMode(ledPin, OUTPUT);
  pinMode(buttonPin, INPUT);
}

void loop()
{
  val = digitalRead(buttonPin);
  
  if(val == 1) // daca butonul este apasat
  	digitalWrite(ledPin, HIGH); // alimentam in continuare LED-u;
  else // altfel, daca butonul nu este apasat
  	digitalWrite(ledPin, LOW); // oprim alimentarea LED-ului
}```

Click on start Simulation if you change the light indicator on the Photoresistor, the osoloscope will show a signal for the analog input
![output](https://github.com/user-attachments/assets/7e29f9a8-0e4c-457e-81e3-d124112dd693)


