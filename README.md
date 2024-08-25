# Image
![image](https://cloud-q0d3f5bdc-hack-club-bot.vercel.app/0image.png)

this project using:
+ Raspberry pi pico
+ Buzzer
+ Led
+ HC-SR04

## you can try project on [wowki](https://wokwi.com/projects/407110353453578241)

# Source code:
```ino
#define trig_pin 16
#define echo_pin 17
#define buzzer_pin 4
#define led_pin 15

void setup() {
  Serial1.begin(9600);
  pinMode(trig_pin, OUTPUT);
  pinMode(echo_pin, INPUT); 
  pinMode(led_pin, OUTPUT);
  pinMode(buzzer_pin, OUTPUT);
}
void loop() {
  long distance, duration;
  digitalWrite(trig_pin, LOW);
  delayMicroseconds(2);
  digitalWrite(trig_pin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trig_pin, LOW);
  duration = pulseIn(echo_pin, HIGH);
  distance = (duration / 2) / 29.1;
  if(distance <= 100) {
    digitalWrite(buzzer_pin, HIGH);
    digitalWrite(led_pin, HIGH);
    delay(100);
    digitalWrite(buzzer_pin, LOW);
    digitalWrite(led_pin, LOW);
    delay(100);
  } 
  else if(distance <= 200) {
    digitalWrite(buzzer_pin, HIGH);
    digitalWrite(led_pin, HIGH);
    delay(500);
    digitalWrite(buzzer_pin, LOW);
    digitalWrite(led_pin, LOW);
    delay(500);
  } 
  else if(distance <= 300) {
    digitalWrite(buzzer_pin, HIGH);
    digitalWrite(led_pin, HIGH);
    delay(1000);
    digitalWrite(buzzer_pin, LOW);
    digitalWrite(led_pin, LOW);
    delay(1000);
  } 
  else {
    digitalWrite(buzzer_pin, LOW);
    digitalWrite(led_pin, LOW);
  }
}
```
