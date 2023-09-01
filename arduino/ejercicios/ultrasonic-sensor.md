---
description: HC-SR04
---

# Ultrasonic Sensor

<figure><img src="../../.gitbook/assets/8 - Ultrasonic Distance 2 LED_bb.png" alt=""><figcaption></figcaption></figure>

```arduino
int trigPin = 10; //Pin que emite los sonidos, Trig
int echoPin = 11; //Pin que va a recibir de vuelta la onda
int ledRojo = 13; //LED rojo va en pin 5
int ledAmarillo = 12; //LED verde va en pin 7

int zonaSegura = 10;

void setup(){
  pinMode(trigPin, OUTPUT);
  pinMode(ledRojo, OUTPUT);
  pinMode(ledAmarillo, OUTPUT);
  pinMode(echoPin, INPUT);
  Serial.begin(9600);
}

void loop(){
  long duracion, distanciaEnCm;
  /*
  Hacemos un pulso bajo-alto-bajo para encender el sensor.
  Al encender y apagar esperamos en microsegundos,
  de esta manera enviaremos nuestra primer onda
  */
  digitalWrite(trigPin, LOW); // Envía un pulso bajo
  delayMicroseconds(2);       // Espera dos microsegundos
  digitalWrite(trigPin, HIGH);// Envía un pulso alto
  delayMicroseconds(5);       // Espera 5 microsegundos
  digitalWrite(trigPin, LOW); // Se queda en espera
  
  duracion = pulseIn(echoaPin, HIGH);
  
  /*
  Convertimos la duracion del tiempo a distancia
  La velocidad del sonido es de 340metros/segundo que
  es igual a 29 microsegundos por centimetro es por eso
  que vamos a dividir la duracion entre 29. 
  Despues se divide entre 2 porque es el tiempo
  que viaja el sonido de ida y de vuelta,
  solo queremos un valor pero ambos son iguales,
  es por eso que solo dividimos entre 2
  */
  distanciaEnCm = (duracion/29)/2;
  
  //Imprimimos la distancia en consola
  Serial.print(distanciaEnCm);
  Serial.print("cm");
  Serial.println();
  
  /*Prendemos los LED's, cuando la distancia es
  mayor a la zona segura se prende el LED verde y
  se apaga el rojo. Cuando la distancia es menor
  a la zona segura se prende el LED rojo y se apaga el LED
  verde
  */
  if(distanciaEnCm > zonaSegura){
    digitalWrite(ledAmarillo, HIGH);
    digitalWrite(ledRojo, LOW); 
  }
  else{
    digitalWrite(ledAmarillo, LOW);
    digitalWrite(ledRojo, HIGH);
  }
  delay(100);
}
```

<figure><img src="../../.gitbook/assets/9 - Ultrasonic Distance 2 LED BUZZER_bb (1).png" alt=""><figcaption></figcaption></figure>

{% embed url="https://hardwarehackingmx.wordpress.com/2013/08/28/leccion-18-arduino-sensor-ultrasonico/" %}
