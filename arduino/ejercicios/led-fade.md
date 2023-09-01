# LED Fade

Para hacer que un LED "fade" (es decir, que aumente y disminuya su intensidad de manera gradual), puedes utilizar la función `analogWrite()` en lugar de `digitalWrite()`. La función `analogWrite()` permite controlar la intensidad del LED enviando un valor de 0 a 255 a un pin de salida PWM (modulación por ancho de pulso). Un valor de 0 hace que el LED esté apagado, mientras que un valor de 255 hace que esté al máximo de intensidad.

Aquí hay un código de Arduino para hacer un LED fade:

```arduino
const int LED_PIN = 9;  // Pin del LED conectado al Arduino

void setup() {
  // Configurar el pin del LED como una salida PWM
  pinMode(LED_PIN, OUTPUT);
}

void loop() {
  // Aumentar la intensidad del LED de 0 a 255
  for (int i = 0; i <= 255; i++) {
    analogWrite(LED_PIN, i);
    delay(10);
  }
  // Disminuir la intensidad del LED de 255 a 0
  for (int i = 255; i >= 0; i--) {
    analogWrite(LED_PIN, i);
    delay(10);
  }
}

```

Este código hace que los dos LED aumenten y disminuyan su intensidad de manera gradual en secuencia. Puedes modificar el tiempo de espera en la función `delay()` para cambiar la velocidad del fade. También puedes cambiar el orden en que los LED se encienden y apagan, o incluso hacer que ambos LED aumenten y disminuyan su intensidad al mismo tiempo, modificando el código de los bucles `for`.
