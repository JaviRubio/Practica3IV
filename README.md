#Practica 3 de Infraestructuras virtuales#

##Por Javier Rubio Giménez##

###Elección de maquina:###

Para esta practica vamos a virtualizar un sistema Android(version Jellybean 4.3) bajo virtualbox, lo cual puede servir para ayudar a desarrollar aplicaciones para android usando la maquina como entorno de pruebas, ya que el emulador que trae el SDK de Android esta mal optimizado, ya que usa la version ARM y lo que hace es ir traduciendo las instrucciones ARM a x86, lo que provoca un rendimiento bajisimo. Ademas vamos a comparar el rendimiento de la maquina virtual con un dispositvo real.


###Hardware###

Para la maquina virtual se va a explorar dos configuraciones:

1)
Procesador:1 Nucleo
Memoria:1Gb de ram

2)
Procesador:2 Nucleos
Memoria:2Gb de ram

Maquina anfitriona:

Procesador:Intel core i7 3630qm
Memoria:16Gb DDR3

Smartphone:

Nexus 4 con Android Kitkat 4.4.2 y con maquina virtual para Java Dalvik de Motorola.

###Instalacion###

Para realizar la instalacion usaremos la version x86 bajada de la siguiente pagina:

https://code.google.com/p/android-x86/downloads/detail?name=android-x86-4.3-20130725.iso

En virtualbox crearemos una maquina virtual basada en Linux generico con kernel 2.6/3 o superior de 32 bits:

<img src="https://raw2.github.com/JaviRubio/Practica3IV/master/Practica3/m1.PNG">

Luego le asignaremos la memoria mencionada anteriormente:

<img src="https://raw2.github.com/JaviRubio/Practica3IV/master/Practica3/m2.PNG">

Para el disco usaremos 8 gigas, que ademas es el valor que virtualbox te sugiere por defecto:

<img src="https://raw2.github.com/JaviRubio/Practica3IV/master/Practica3/m3.PNG">

En cuanto el tipo de disco duro podemos escoger el que queramos,en nuestro caso usaremos el por defecto:

<img src="https://raw2.github.com/JaviRubio/Practica3IV/master/Practica3/m4.PNG">

Para la reserva nosotros vamos a escoger dinamica, si bien una fija deberia tener ligeramente mas rendimiento a cambio de usar todo el espacio asignado de inicio:

<img src="https://raw2.github.com/JaviRubio/Practica3IV/master/Practica3/m5.PNG">

En cuanto a nombre para el disco podemos dejar el por defecto:

<img src="https://raw2.github.com/JaviRubio/Practica3IV/master/Practica3/m6.PNG">

Llegados a este punto ya tenemos la maquina configurada. Ahora tenemos que añadir la iso descargada a la maquina, como hacemos usualmente. Luego ya podemos arrancar la maquina normalmente, encontrandonos con la siguiente pantalla.

<img src="https://raw2.github.com/JaviRubio/Practica3IV/master/Practica3/m7.PNG">

Aqui tenemos la opcion de arrancar un live, que funciona perfectamente, con el unico inconveniente de que al no tener persistencia cada vez que lo arranque nos pedira toda la configuracion inicial. Nosotros vamos a escoger la instalacion.
La instación es bastante sencilla. Lo unico mas delicado es el tema de las particiones, que realmente es lo unico por lo que nos va a preguntar el instalador:

<img src="https://raw2.github.com/JaviRubio/Practica3IV/master/Practica3/m8.PNG">

Para configurar la particiones nos da cfdisk, herramienta clasica de linux:

<img src="https://raw2.github.com/JaviRubio/Practica3IV/master/Practica3/m9.PNG">

Luego nos pregunta si queremos queremos que la carpeta de sistema tambien sea de escritura. Esto seria similar a tener un terminal rooteado:

<img src="https://raw2.github.com/JaviRubio/Practica3IV/master/Practica3/m10.PNG">

Yo solo nos queda esperar a que se instale:

<img src="https://raw2.github.com/JaviRubio/Practica3IV/master/Practica3/m11.PNG">

Y con eso finaliza la instalación, y nos preguntara si queremos reiniciar o arrancar directamente:

<img src="https://raw2.github.com/JaviRubio/Practica3IV/master/Practica3/m12.PNG">

Y ya podemos arrancar normalmente android:

<img src="https://raw2.github.com/JaviRubio/Practica3IV/master/Practica3/m13.PNG">

###Bugs conocidos###

Esta version de Android x86 virtualizado tiene un par de detalles que debemos tener en cuenta. Como notaremos nada mas arrancar no hay cursor para el raton, auqneu el raton funciona perfectamente. Esto es un problema de compatibilidad con la integracion de raton con virtualbox. Si la descativamos pasa a funcionar correctamente.

Por motivos de compatibilidad se recomienda que usamos para hardware de sonido el Blaster16.

###Benchmark###

Para cada configuracion vamos a ejecutar dos benchmarks:

-Qualcomm Vellamo

-CPU Prime Benchmark

Estos son los resultados:

Configuracion 1:

<img src="https://dl.dropboxusercontent.com/u/14147051/Practica3/benchPC3.PNG">

<img src="https://dl.dropboxusercontent.com/u/14147051/Practica3/benchPC4.PNG">

Configuracion 2:

<img src="https://dl.dropboxusercontent.com/u/14147051/Practica3/benchPC1.PNG">

<img src="https://dl.dropboxusercontent.com/u/14147051/Practica3/benchPC2.PNG.PNG">

Smartphone:

<img src="https://dl.dropboxusercontent.com/u/14147051/Practica3/benchN4-1.png">

<img src="https://dl.dropboxusercontent.com/u/14147051/Practica3/benchN4-2.png">

###Conclusiones###

Como se puede apreciar en los resultados, la maquina virtual es considerablemente mas potente que cualquier smartphone existente en el mercado actualmente, y de lejos mucho mas potente que el emulador integrado en el SDK de android. No obstante tenemos que señalar que la imagen probada aun tiene ciertas incompatibilidades, por lo que aun pudiendo sustituir al emulador integrado, sigue siendo mejor usar un dispositivo real.

Ademas, en cuanto a configuracion de la maquina virtual podemos apreciar que las pruebas arrojan los mismos valores. Esto se debe a que los factores que hemos modificado en la configuracion de la maquina virtual no producen cuellos de botella en las ejecuciones.











