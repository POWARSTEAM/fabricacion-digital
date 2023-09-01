# Temperatura

Un sensor de temperatura es un dispositivo que se utiliza para medir la temperatura ambiental. Existen varios tipos de sensores de temperatura que se pueden utilizar con Arduino, algunos de los más comunes son:

<figure><img src="../../../.gitbook/assets/image (35).png" alt=""><figcaption></figcaption></figure>

* **Sensor de temperatura LM35:** Este sensor es un circuito integrado que convierte la temperatura en una señal analógica de voltaje. Es un sensor preciso y fácil de usar, pero solo puede medir temperaturas entre -55 y 150 grados Celsius.

<figure><img src="../../../.gitbook/assets/image (41).png" alt=""><figcaption></figcaption></figure>

* **Sensor de temperatura DS18B20:** Es un sensor de temperatura digital que utiliza el protocolo One-Wire para comunicarse con el Arduino. Es muy preciso y puede medir temperaturas entre -55 y 125 grados Celsius.

<figure><img src="../../../.gitbook/assets/image (140).png" alt=""><figcaption></figcaption></figure>

* **Sensor de temperatura TMP36:** Este sensor es similar al LM35, pero tiene un rango de medición de temperatura más amplio (-40 a 125 grados Celsius)

Para conectar un sensor de temperatura a un Arduino, se conecta el sensor a los pines de entrada analógica del Arduino y se utiliza el código para leer los valores de voltaje y convertirlos en una lectura de temperatura. Los sensores de temperatura son comúnmente utilizados en proyectos de control de clima, sistemas de seguridad, medición de temperatura en equipos industriales, entre otros.

Existen muchos otros tipos de sensores de temperatura de Arduino, otros dos también usados son el Infrarojo y el Analógico. A veces los sensores vienen sueltos (sin módulo) y en algunas otras ocasiones vienen en módulos ya con las resistencias y demás componentes necesarios para facilitarnos su uso.

<figure><img src="../../../.gitbook/assets/image (130).png" alt=""><figcaption></figcaption></figure>

**Los sensores de temperatura infrarrojos** (IR) se conectan al Arduino mediante un conector analógico o digital, y se utilizan para medir la temperatura de los objetos a través de la radiación infrarroja que emiten. Estos son muy precisos y tienen un rango de medición de temperatura amplio, desde -70 hasta 380 grados Celsius.

\\

<figure><img src="../../../.gitbook/assets/image (82).png" alt=""><figcaption></figcaption></figure>

Un termistor es un tipo de sensor de temperatura analógico que utiliza un cambio en la resistencia eléctrica para medir la temperatura. Los termistores son resistencias sensibles a la temperatura, es decir, su resistencia varía en función de la temperatura ambiente. Los termistores se dividen en dos tipos: NTC (Negative Temperature Coefficient) y PTC (Positive Temperature Coefficient).

Los termistores NTC tienen una resistencia que disminuye a medida que aumenta la temperatura. En general, su resistencia es muy alta a temperaturas bajas y disminuye a medida que aumenta la temperatura.

Por otro lado, los termistores PTC tienen una resistencia que aumenta a medida que aumenta la temperatura. En general, su resistencia es muy baja a temperaturas bajas y aumenta a medida que aumenta la temperatura.
