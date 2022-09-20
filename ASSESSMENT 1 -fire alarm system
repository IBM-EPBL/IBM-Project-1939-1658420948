#include <LiquidCrystal.h>
LiquidCrystal lcd(5,6,8,9,10,11);  

int Rled = 2;
int Gled = 3;
int piezo = 4;
int sensor = A0;
int sensorThresh = 400;

void setup()
{
pinMode(Rled, OUTPUT);
pinMode(Gled,OUTPUT);
pinMode(piezo,OUTPUT);
pinMode(sensor,INPUT);
Serial.begin(9600);
lcd.begin(16,2);
}

void loop()
{
 int analogValue = analogRead(sensor);
 if(analogValue>sensorThresh)
  {
    digitalWrite(Rled,HIGH);
    digitalWrite(Gled,LOW);
    tone(piezo,1000,10000);
    lcd.clear();
    lcd.setCursor(0,0);
    lcd.print("WARNING");
    delay(1000);
    lcd.clear();
    lcd.setCursor(0,1);
    lcd.print("SMOKE DETECTED");
    delay(1000);
    lcd.clear();
    lcd.setCursor(0,0);
    lcd.print("PLEASE CHECK");
    delay(1000);
    lcd.clear();
    lcd.setCursor(0,1);
    lcd.print("YOUR AREA");
    delay(1000);
    Serial.println("Smoke is detected");
    Serial.print("Analog Value is:");
    Serial.println(analogValue);
    Serial.println();
  }
  else
  {
    digitalWrite(Gled,HIGH);
    digitalWrite(Rled,LOW);
    noTone(piezo);
    lcd.clear();
    lcd.setCursor(0,0);
    lcd.print("SAFE");
    delay(1000);
    lcd.clear();
    lcd.setCursor(0,1);
    lcd.print("ALL CLEAR");
    delay(1000);
    Serial.println("No Smoke is detected");
    Serial.print("Analog Value is:");
    Serial.println(analogValue);
    Serial.println();
  }  
     
}
