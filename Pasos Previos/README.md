# Pasos Previos - Realización de un doble intermitente.
## Introducción
El objeto de este primer proyecto, es comprender y recordar el funcionamiento y la programación de la placa de Arduino. Para esto hemso utilizado un único programas: Tinkercad. Ha sido para realizar la simulación del montaje, y a su vez, el programa. 

## Montaje 1
### Materiales
Para el montaje hemos necesitado los siguientes materiales: dos diodos led (de distinto color a poder ser), cables macho - macho, una resistencia como mínimo, una placa de prototipado donde colocar todos los materiales y la placa de Arduino donde van conectados todos los materiales.


![Montaje TinkerCad](imagenesproyecto1/Montaje1.png)

Aquí se pueden ver todas las conexiones que han sido necesarias hacer. En este caso hemos optado por poner una única resistencia, lo que ha hecho que el montaje sea diferente al resto. Cada led tiene dos patas, la positiva y la negativa (ánodo y cátodo). Las positivas van a dos pines digitales de arduino distintos. Y las negativas están conectadas a tierra (GND). Finalmente la resistencia se puede conectar a cualquiera de las patas del diodo LED. En esta caso está conectado al negativo.

## Programación 
Para la programación de esta práctica, lo primero que tenemos que hacer es definir la variable tiempo, que van a ser los segundos que permanezcan encendidos los diodos LED. Una vez tenemos todas las variables definidas, que en este caso es tan sólo una, seguimos con el set up. El set up es una parte del programa que se ejecuta una única vez al iniciarse el programa. Aquí iniciamos el programa y además activamos los pines a los que los diodos están conectados. En el void loop, que se repite en bucle hasta que se termine el programa, hemos activado un pin de un diodo led y desactivado el otro. Y al réves después. Pero en el medio hemos puesto un pequeño delay que va a durar el tiempo que hayamos establecido al principio en la variable de tipo entera llamada tiempo. 

![Programa.](imagenesproyecto1/programa.png) 

## Conclusión
Esta prueba nos ha permitido recordar las bases de la programación en Arduino, su sintaxis y además el control de un repositorio de Github. 

# Prueba 2 - Incorporación de un pulsador
## Introducción
Durante este trimestre, vamos a realizar una serie de pequeños proyectos o pruebas para poco a poco ir conociendo la interfaz de Arduino. En esta segunda prueba, hemos partido desde el montaje anterior y le hemos añadido un pulsador. De tal manera que al pulsarlo, se encienda uno de los dos ledes y al dejar de pulsarlo al contrario. 

## Montaje 2
### Materiales
Para este montaje hemos necesitado los mismos materiales que la práctica anterior. Sin embargo, le hemos añadido un pulsador y además ha sido necesario la incorporación de unos cuantos cables macho - hembra más.

![Montaje del pulsador.](imagenesproyecto1/Montaje2.png)

Para el cone4xionado de todos los componentes hemos utilizado cables macho - hembra. Ademas hemos aprovechado el anterior montaje para a partir de este seguir con la incorporación del pulsador. Es por esto que lo único nuevo ha sido conectar el pulsador. Uno de los conectores del pulsador va unido al 5V, el otro al GND y, el último, a un pin digital.


## Programa 
Antes de nada, establecemos las variables de tipo entero, que en este caso son los dos ledes y el pulsador. A parte también tenemos que crear otra variable, la cual he llamado "estado pulsador" que indica si el pulsador está siendo pulsado o no, para posteriormente programarlo. En el void set up hemos establecido los ledes como dispositivos de salida y el pulsador como dispositivo de entrada e iniciamos el puerto serie. A continuación, en el void loop especificamos que la variable de estado pulsador es igual a la lectura digital del estado real del pulsador (pulsado, 1; no pulsado, 0). Si el estado del pulsador es 1, entonces el led 1 se enciende y el 2 se apaga. Y si el estado del pulsador es 0, entonces se hace a la inversa y además en el puerto serie, indica que el pulsador no está siendo pulsado (No pulsado). 

![Programa con pulsador](imagenesproyecto1/programaint.png)

## Conclusión
Con esta práctica hemos ampliado nuestros conocimientos de la interfaz de Arduino, TinkerCad y hemos progresado en el control del lenguaje de código C++. 

# Prueba 3 - Potenciómetro y mapeo
## Introducción
Como todas las prácticas de este trimestre, partimos del anterior proyecto para ir aumentando nuestros conocimientos sobre la interfaz de Arduino y sobre algunos componentes tecnólogicos y su respectivo funcionamiento. El objetivo final de esta prueba es incorporar un potenciómetro al circuito de ledes para que así, la intensidad de los ledes o el LED vaya disminuendo o aumentado según gires el potenciómetro.

## Montaje
### Materiales
Para este circuito hemos necesitado los mismos materiales que antes: 
- Cables macho-macho.
- Un diodo LED.
- La placa de Arduino.
- Además de la reciente incorporación del potenciómetro.

![Montaje del potenciómetro](imagenesproyecto1/IMG_8490.JPEG)

### Programa

Al principio del programa lo primero que hacemos es establecer las variables como es ya de costumbre. Establecemos el pin del LED y el pin del potenciómetro, el cuál está conectado en un pin analógico; y además creamos la variable de lo que lee el potenciómetro y del valor que se guardará en el mapeado. 

Empezando con el void set up, ponemos al LED como dispositivo de salida y establecemos la comunicación con el puerto serie. Gracias a esta comunicación con el puerto serie vamos a poder ver los valores a tiempo real. 

En el void loop, lo primero que hacemos, es igualar la variable de la lectura del potenciómetro a lo que lee el potenciometro conectado al pin analógico. Después convertimos el valor de la salida del led con el mapeo, de tal manera que pasamos del rango (0 - 1023) al (0-255) que es el rango de la luminosidad del LED. Mas tarde, le decimos al LED que tome el valor de la salida LED, el cual hemos establecido antes gracias a la función del mapeo. De tal manera que cuando fuera 0 el led estará totalmente apagado y conforme se vaya acercando al 255 estará más iluminado. El programa podría acabarse aquí, sin embargo, hemos optado por añadir la lectura dek monitor serie también para así saber si está fallando el potenciómetro.


![Montaje del potenciómetro](imagenesproyecto1/programamapeo.png)

### Conclusión
Con este programa hemos aprendido cómo funciona el potenciómetro y cómo es su programación. Además hemos aprendido una nueva función de Arduino: el mapeo. Gracias a esta práctica hemos adquirido muchos conocimientos y hemos ampliado nuestras habilidades de programación de Arduino. 

# Prueba 4 - Ultrasonidos
## Introducción 
El propósito de esta práctica es conocer el conexionado de un sensor de ultrasonidos y cómo programarlo de tal manera que mida distancias y estas se muestren en el monitor serie.

## Montaje
El montaje de este programa es demasiado sencillo. Únicamente consta de un sensor de ultrasonidos conectado a una placa arduino. El conexionado es el siguiente:
1. VCC: va al 5V (proporciona la corriente)
2. TRIGGER: va a un pin digital (es lo que emite una señal)
3. ECHO: va a otro pin digital (es lo que recibe la señal)
4. GND: terminal tierra.

![Montaje del sensor ultrasonidos](imagenesproyecto1/Ultrasonidos.png)

## Programa
El programa es muy sencillo ya que solo vamos a estar manipulando un único dispositivo. Para ello vamos a estar jugando con el monitor serie, que sería el lugar donde aparecerían las lecturas del sensor de ultrasonidos. Primero incluimos la librería del ultrasonidos. Después, como siempre, se establecen las variables que en este caso son el pin donde están conectados el TRIGGER y el ECHO del ultrasonidos; aprovechamos y establecemos que el sensor de ultrasonidos está compuestos por ese TRIGGER y ese ECHO. En el void set up lo único que hacemos es activar el puerto serie. Y en el void loop le decimos al puerto serie que mida la distancia en centímetros y que las muestre en el puerto serie. 

![Montaje del sensor ultrasonidos](imagenesproyecto1/programaultra.png)

## Conclusión 
Con este programa, hemos recordado como utilizar el monitor serie. Esta practica nos ha ayudado a afianzar nuestros conocimientos sobre los sensores de ulrasonidos medidores de distancias, cosa que es muy útil ya que es muy relevante a la hora de hacer proyectos con Arduino.


