const int irSensorPin = 2;
int i;
const int redLED = 3;
const int yellowLED = 4;
const int greenLED= 5;

void setup(){
  Serial.begin(9600);
  pinMode(irSensorPin,INPUT);
  pinMode(redLED,OUTPUT);
  pinMode(yellowLED,OUTPUT);
  pinMode(greenLED,OUTPUT);
}
void loop(){
  int irSensorState=digitalRead(irSensorPin);
  for(i;i<5;i++){
  if(irSensorState==LOW)
    {Serial.println("OBJECT DETECTED");
     digitalWrite(redLED,HIGH);
     digitalWrite(yellowLED,HIGH);
     digitalWrite(greenLED,HIGH);
     delay(1000);
     digitalWrite(redLED,LOW);
     digitalWrite(yellowLED,LOW);
     digitalWrite(greenLED,LOW);
     delay(1000);
    }
   else{
    Serial.println("NO OBJECT IS NOT DETECTED");
     digitalWrite(redLED,LOW);
     digitalWrite(yellowLED,LOW);
     digitalWrite(greenLED,LOW);
     delay(100);
   }
  }
 }
