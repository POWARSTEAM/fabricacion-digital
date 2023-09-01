# LED y Botón

Para encender un LED con un botón en Arduino, puedes seguir estos pasos:

<figure><img src="../../.gitbook/assets/4 - 1 Led 1 botón_bb (1).png" alt=""><figcaption></figcaption></figure>

1. Conecta un extremo del LED al pin digital 13 de Arduino y el otro extremo al pin GND.
2. Conecta un extremo del botón al pin digital 10 de Arduino y el otro extremo al pin GND.
3. Escribir el código en el editor de Arduino:

```arduino
const int buttonPin = 10;   // define el pin del botón
const int ledPin = 13;      // define el pin del LED

int buttonState = 0;        // almacena el estado del botón

void setup() {
  pinMode(ledPin, OUTPUT);  // configura el pin del LED como salida
  pinMode(buttonPin, INPUT); // configura el pin del botón como entrada
  Serial.begin(9600);       // inicia la comunicación serie a 9600 baudios
}

void loop() {
  buttonState = digitalRead(buttonPin);   // lee el estado del botón

  if (buttonState == LOW) {              // si el botón está presionado
    digitalWrite(ledPin, HIGH);           // enciende el LED
    Serial.println("Botón presionado");
  } else {                                // si el botón no está presionado
    digitalWrite(ledPin, LOW);            // apaga el LED
    Serial.println("Botón no presionado");
  }
}

```

En este caso, el botón está conectado al pin 8 de Arduino y se ha configurado como entrada, al presionar el botón el estado del pin sera LOW, en ese momento se enciende el LED conectado al pin 9 de arduino. Además, se imprimirá "Botón presionado" o "Botón no presionado" en la consola serie de Arduino para indicar el estado del botón.
