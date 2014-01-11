#Practica 1 de Infraestructuras virtuales#

##Por Javier Rubio Giménez##

###Elección de plataforma:###

La practica la hemos realizado en openshift.

OpenShift es una plataforma que nos provee servicios PaaS propiedad de RedHat.

Nos permite trabajar con Java,PHP,Ruby,Node.js,Python,Perl,MySQL,MongoDB,PostgreSQL y nos permite instalar los principales
cms como Wordpress,Drupal o joomla. Tambien nos permite trabajar con frameworks que se apoyen en esas tecnologias.

Como se aprecia es una solucion muy completa, y de forma gratuita nos permite tener hasta 3 proyectos funcionando
simultaneamente.

Ademas,esta respaldada por un gran empresa como RedHat, lo que siempre añade un plus de confianza.

Por lo expuesto anterior nos hemos decantado por OpenShift para alojar nuestra aplicación.

###Despligue###

Para desplegar nuestra aplicación lo primero que hacemos es crear una aplicación en OpenShift vacia:

<img src="https://dl.dropboxusercontent.com/u/14147051/CreateOpenShift.png">

<img src="https://dl.dropboxusercontent.com/u/14147051/CrearOpen.png">

Luego introducimos el nombre que queremos darle a la aplicación

<img src="https://dl.dropboxusercontent.com/u/14147051/openpaso2.png">

Y por ultimo pulsamos al final el boton de crear.

Una vez que los tenemos creado ya solo nos queda descargar el repositio GIT a nuestro entorno de trabajo.

El propio openshift nos proporciona los comandos en cuestión, en este caso seria

<pre>git clone ssh://52642fae50044636fd000457@practicaiv1-javirubioapps.rhcloud.com/~/git/practicaiv1.git/
cd practicaiv1/</pre>

Y una vez tenemos los archivos en local, ya solo nos queda hacer los cambios oportunos. OpenShift tambien nos
provee de los comandos oportunos:

<pre>git add .
git commit -m 'My changes'
git push</pre>

Y con eso tenemos nuestra aplicación montada :)

Un ejemplo de la aplicación:

<img src="https://dl.dropboxusercontent.com/u/14147051/Calculadora.png">
