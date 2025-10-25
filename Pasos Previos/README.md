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
Con esta práctica hemos ampliado nuestros conocimientos de la interfaz de4 Arduino, TinkerCad y hemos progresado en el control del lenguaje de código C++. 
