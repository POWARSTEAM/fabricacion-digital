# Sirena con Luz y Sonido

Para hacer una sirena con dos LED y sonido en Arduino, necesitarás:

* 2 LED
* 2 resistencias
* 1 speaker o altavoz
* Algunos cables de conexión.

El esquema de conexión es el siguiente:

1. Conecta un extremo de un cable de conexión al pin del primer LED correspondiente (anodo o cátodo, según el tipo de LED).
2. Conecta el otro extremo del cable de conexión a una resistencia.
3. Conecta un extremo de la resistencia al pin GND (tierra) del Arduino.
4. Conecta el otro extremo de la resistencia a un pin digital de salida del Arduino.
5. Repite los pasos 1 a 4 para el segundo LED, utilizando una segunda resistencia y un segundo pin de salida del Arduino.
6. Conecta un extremo de un cable de conexión al pin + del speaker o altavoz.
7. Conecta el otro extremo del cable de conexión a un pin digital de salida del Arduino.
8. Conecta un extremo de otro cable de conexión al pin - del speaker o altavoz.
9. Conecta el otro extremo del cable de conexión al pin GND (tierra) del Arduino.

Una vez que hayas conectado los LED y el speaker al Arduino, puedes utilizar el siguiente código para hacer una sirena que parpadea los LED y reproduce un tono de sirena:

```arduino
const int LED1_PIN = 13;  // Pin del primer LED
const int LED2_PIN = 12;  // Pin del segundo LED
const int SPEAKER_PIN = 11;  // Pin del speaker o altavoz

void setup() {
  // Configurar los pines de los LED y el speaker como salidas
  pinMode(LED1_PIN, OUTPUT);
  pinMode(LED2_PIN, OUTPUT);
  pinMode(SPEAKER_PIN, OUTPUT);
}

void loop() {
  // Reproducir el tono de la sirena y parpadear los LED alternativamente
  tone(SPEAKER_PIN, 440, 1000);  // Frecuencia de 440 Hz durante 1 segundo
  digitalWrite(LED1_PIN, HIGH);
  digitalWrite(LED2_PIN, LOW);
  delay(1000);
  tone(SPEAKER_PIN, 880, 1000);  // Frecuencia de 880 Hz durante 1 segundo
  digitalWrite(LED1_PIN, LOW);
  digitalWrite(LED2_PIN, HIGH);
  delay(1000);
}

```

Este código hace que el speaker reproduzca un tono de sirena que cambia entre 440 Hz y 880 Hz cada segundo, mientras que los LED parpadean alternativamente. Puedes modificar las frecuencias y los tiempos de reproducción en las funciones `tone()`
