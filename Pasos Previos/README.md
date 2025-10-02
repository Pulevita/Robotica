# Pasos Previos - Realización de un doble intermitente.
## Introducción
El objeto de este primer proyecto, es comprender y recordar el funcionamiento y la programación de la placa de Arduino. Para esto hemso utilizado un único programas: Tinkercad. Ha sido para realizar la simulación del montaje, y a su vez, el programa. 

## Montaje
### Materiales
Para el montaje hemos necesitado los siguientes materiales: dos diodos led (de distinto color a poder ser), cables macho - macho, una resistencia como mínimo, una placa de prototipado donde colocar todos los materiales y la placa de Arduino donde van conectados todos los materiales.


![Montaje TinkerCad](Pasos Previos/imagenesproyecto1/Montaje1.png) Aquí se pueden ver todas las conexiones que han sido necesarias hacer. En este caso hemos optado por poner una única resistencia, lo que ha hecho que el montaje sea diferente al resto. Cada led tiene dos patas, la positiva y la negativa (ánodo y cátodo). Las positivas van a dos pines digitales de arduino distintos. Y las negativas están conectadas a tierra (GND). Finalmente la resistencia se puede conectar a cualquiera de las patas del diodo LED. En esta caso está conectado al negativo.

## Programación 
Para la programación de esta práctica, lo primero que tenemos que hacer es definir la variable tiempo, que van a ser los segundos que permanezcan encendidos los diodos LED. Una vez tenemos todas las variables definidas, que en este caso es tan sólo una, seguimos con el set up. El set up es una parte del programa que se ejecuta una única vez al iniciarse el programa. Aquí iniciamos el programa y además activamos los pines a los que los diodos están conectados. En el void loop, que se repite en bucle hasta que se termine el programa, hemos activado un pin de un diodo led y desactivado el otro. Y al réves después. Pero en el medio hemos puesto un pequeño delay que va a durar el tiempo que hayamos establecido al principio en la variable de tipo entera llamada tiempo. 

int tiempo = 75;

//Eva Espinosa Ortiz Robótica y Visión Artificial 4º
void setup()
{
  pinMode(8, OUTPUT);
  pinMode(7, OUTPUT);
  
}

void loop()
{
 digitalWrite(8, HIGH);  
  digitalWrite(7, LOW);    
  delay(tiempo);             
  digitalWrite(8, LOW);   
  digitalWrite(7, HIGH);  
  delay(tiempo);
}

