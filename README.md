# Arduino_serialdata


Arduino code:

#include <Servo.h>
int switchState = 0;
void setup() {
  Serial.begin(9600);
  pinMode(3, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(2, INPUT);
  
}

void loop() {
  delay(500);
  switchState = digitalRead(2);
  if(switchState == HIGH){
    for(int i=0;i<5;i++){
      digitalWrite(3, HIGH);
      Serial.println("Light 3: ON");
      delay(1000);
      digitalWrite(3, LOW);
      Serial.println("Light 3: OFF");
      delay(1000);
      digitalWrite(4, HIGH);
      Serial.println("Light 4: ON");
      delay(1000);
      digitalWrite(4, LOW);
      Serial.println("Light 4: OFF");
      delay(1000);
      digitalWrite(5, HIGH);
      Serial.println("Light 5: ON");
      delay(1000);
      digitalWrite(5, LOW);
      Serial.println("Light 5: OFF");
    }
  }
}
