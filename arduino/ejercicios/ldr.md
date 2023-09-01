# LDR

<figure><img src="../../.gitbook/assets/5.1 - LDR Read (1).png" alt=""><figcaption></figcaption></figure>

```arduino
const int ldrPin = A0;
int ldrValue= 0;

void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  pinMode(ldrPin, INPUT);

}

void loop() {
  // put your main code here, to run repeatedly:
  ldrValue = analogRead(ldrPin);
  Serial.print("LDR value: ");
  Serial.println(ldrValue);

delay(1000);

}
```

<figure><img src="../../.gitbook/assets/5.1 - LDR Buzzer_bb.png" alt=""><figcaption></figcaption></figure>

```arduino
int sensorPin = A0;
int speakerPin = 9;

void setup() {

}

void loop() {
  tone(speakerPin,analogRead(sensorPin));
  delay(20);
}
```

<figure><img src="../../.gitbook/assets/6 - LDR 1 LED.png" alt=""><figcaption></figcaption></figure>

```arduino
const int ledPinRED = 13;
const int ldrPin = A0;
int ldrValue= 0;

void setup() {
  Serial.begin(9600);
  pinMode(ledPinRED, OUTPUT);
  pinMode(ldrPin, INPUT);
}

void loop() {
  ldrValue = analogRead(ldrPin);
  Serial.print("LDR value: ");
  Serial.print(ldrValue);
if(ldrValue <= 300){
  digitalWrite(ledPinRED, HIGH);
  Serial.println("LDR está OSCURO");
  }
else {
  digitalWrite(ledPinRED, LOW);
  Serial.println("LDR está ILUMINADO");
}
Serial.println();
delay(1000);
}
```

<figure><img src="../../.gitbook/assets/7 - LDR 2 LED_bb.png" alt=""><figcaption></figcaption></figure>

```arduino
const int ledPinRED = 13;
const int ledPinYELLOW = 12;
const int ldrPin = A0;
int ldrValue= 0;

void setup() {
  Serial.begin(9600);
  pinMode(ledPinRED, OUTPUT);
  pinMode(ledPinYELLOW, OUTPUT);
  pinMode(ldrPin, INPUT);
}

void loop() {
  ldrValue = analogRead(ldrPin);
  Serial.print("LDR value: ");
  Serial.print(ldrValue);
if(ldrValue <= 300){
  digitalWrite(ledPinRED, HIGH);
  digitalWrite(ledPinYELLOW, LOW);
  Serial.println("LDR está MUY OSCURO");
  }
if(ldrValue < 800 && ldrValue > 300){
  digitalWrite(ledPinRED, HIGH);
  digitalWrite(ledPinYELLOW, HIGH);
  Serial.println("LDR está NORMAL");
}
if(ldrValue >= 800){
  digitalWrite(ledPinRED, LOW);
  digitalWrite(ledPinYELLOW, HIGH);
  Serial.println("LDR está MUY ILUMINADO");
}
Serial.println();
delay(1000);
}
```
