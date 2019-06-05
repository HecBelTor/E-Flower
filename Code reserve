#include <rgb_lcd.h>
#include <Wire.h>
rgb_lcd lcd;
const int rouge = 15;
const int vert = 16;
const int read = A0; 
int value;          

void setup()
{
  
  Serial.begin(9600);
  pinMode(rouge, OUTPUT);
  pinMode(vert, OUTPUT);
  digitalWrite(vert, HIGH);
  lcd.begin(16, 2);
  lcd.print("initialisation");



}

void loop()
{
  value = analogRead(read); 

  if (value <= 480) {
    lcd.clear();
    lcd.setRGB(255, 0, 0);
    lcd.print("Reserve vide !");
    lcd.setCursor(0, 1);
    lcd.print("Remplir reserve") ;
  }
  else if (value > 480 && value <= 620) {
    lcd.clear();
    lcd.setRGB(255, 0, 0);
    lcd.print("Niveau de la");
    lcd.setCursor(0, 1);
    lcd.print("reserve : BAS");
  }
  else if (value > 615 && value <= 620) {
    lcd.clear();
    lcd.setRGB(0, 255, 0);
    lcd.print("Niveau de la");
    lcd.setCursor(0, 1);
    lcd.print("reserve : MOYEN");
  }
  else if (value > 620) {
    lcd.clear();
    lcd.setRGB(0, 255, 0);
    lcd.print("Niveau de la");
    lcd.setCursor(0, 1);
    lcd.print("reserve : HAUT");
  }
  value = analogRead(read);
  if (value <= 615) {
    digitalWrite(vert, LOW);
    digitalWrite(rouge, HIGH);
  }
  else {
    digitalWrite(vert, HIGH);
    digitalWrite(rouge, LOW);
  }
Serial.println(value);
  delay(4000);
}


