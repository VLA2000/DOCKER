**Project: “Cloud Computing in European schools”**  
<img src="/media/cloud-computing-logoproject.jpg" height="100" width="170">

 Number: Project: 2017-1-ES01-KA202-038471

<img src="/media/cofinanciadoEN.png" height="50" width="200"> <img src="/media/logoIES-Modificado.png" height="75" width="200">  




# Introduction to PaaS: develop, deploy, run and manage apps on the Cloud  



#### Disclaimer
&nbsp;&nbsp;&nbsp;  *"The European Commission support for the production of this publication does not constitute an endorsement of the contents which reflects the views only of the authors, and the Commission cannot be held responsible for any use which may be made of the information contained therein."*




#### Autores

&nbsp;&nbsp;&nbsp;  Este trabajo está realizado por Manuel Santos, José Antonio Busto, José María Parrilla y Víctor López bajo la licencia Creative Commons :  <img src="/img/Licencia-Tipo2.png" height="25" width="75"/>  




### Objective
&nbsp;&nbsp;&nbsp; Platform as a Service (PaaS), is a cloud computing model that allows the users to develop, deploy, run and manage applications without taking care about the underlying layers. The alternatives used today focus on the use of containers which promote the **microservices based application** development approach (vs **monolithic applications**), because the different services into which we the application is separated can easily run in different containers. We will make a study of Docker, Kubernetes and OpenShift in order to develop, deploy, run and manage  microservices based applications.

&nbsp;&nbsp;&nbsp;This activity has been developed for developing the professional competence includes in the Erasmus+ project "Cloud Computing in European Schools".

# <big>Docker</big>

<h2>Instalación de Vagrant y VirtualBox </h2>
<p>Para utilizar Docker, primero tenemos que instalar Vagrant.<br>
Vagrant es una herramienta gratuita de línea de comandos, disponible para Windows,<br> MacOS X y GNU/Linux, que permite generar entornos de desarrollo reproducibles y<br> poderlas compartir de forma muy sencilla. Para ello, Vagrant crea y configura máquinas<br> virtuales a partir de simples ficheros de configuración.</p>
<p>El comando para instalar Vagrant es:</p>
<br>
<img src="media/1.Instalacion de vagrant y virtualbox/1-2.png" height="400" width="550"/>
<br>
<p>Ahora que tenemos Vagrant, tenemos que instalar una máquina virtual. 
<br>
En este caso, nosotros usamos Virtualbox (es un software de virtualización para arquitecturas x86/amd64. Ofrece algunas funcionalidades interesantes, como la ejecución de máquinas virtuales de forma remota, por medio del Remote Desktop Protocol)</p>
<br>
<img src="media/1.Instalacion de vagrant y virtualbox/1-4.png" height="400" width="550"/>
<p>Una vez instalado Vagrant y Virtualbox, enlazaremos un sistema operativo y lo haremos funcionar en los siguientes puntos.</p>

<br>

<h2>Instalación de Docker</h2>
<p>Ahora que tenemos la máquina virtual, tenemos que añadirle un sistema operativo<br> y en este caso lo haremos con el siguiente comando:</p>
<br>
<img src="media/2.Instalacion de docker/2-2.png" height="400" width="550"/>
<br>
<p>En la imagen anterior cuando se ha instalado el sistema operativo, después<br>
aparece otra línea de comando que sirve para comprobar el sistema que hemos<br> instalado.</p>
<br>
<p>A continuación, haremos un cd $HOME para ir a nuestra carpeta y aquí crearemos<br>
la carpeta vagrant. Después tenemos que entrar en esta carpeta y dentro crear un archivo llamado Vagrantfile:</p>
<br>
<img src="media/2.Instalacion de docker/2-3.png" height="400" width="550"/>
<br>
<p>Dentro del archivo Vagrantfile ponemos la siguiente información:</p>
<br>
<img src="media/2.Instalacion de docker/2-4.png" height="400" width="550"/>
<br>

<p>Una vez tenemos hecho lo anterior, arrancamos la máquina:</p>
<br>
<img src="media/2.Instalacion de docker/2-5.png" height="400" width="550"/>
<br>
<p>Cuando ya está funcionando nos conectamos mediante el siguiente comando:</p>
<br>
<img src="media/2.Instalacion de docker/2-6.png" height="400" width="550"/>
<br>
<p>Para ver la versión de docker que tenemos ponemos docker version:</p>
<br>
<img src="media/2.Instalacion de docker/2-7.png" height="400" width="550"/> 
<br>
<p>Por último, saldremos de la máquina y la apagaremos:</p>
<br>
<img src="media/2.Instalacion de docker/2-8.png" height="400" width="550"/>
<br>


<h2>Ciclo de Vida de la Aplicación</h2><br>

<p>Lo primero que debemos hacer es crear una aplicación, en este caso vamos a <br> crear una página web llamada ‘index.html’, que va a ser servida por un servidor web,<br> que se ejecutará en un contenedor Docker, para ello crearemos una carpeta <br> ‘public_html’ que contendrá nuestra página web, utilizamos los siguientes <br> comandos:</p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-3.png" height="400" width="550"/><br>

<p>Necesitaremos utilizar un fichero Dockerfile en el que definiremos como vamos a<br> crear nuestra imagen, la crearemos con este comando: <br></p> 
<img src="media/3.Ciclo de vida de la aplicacion/3-4.png" height="400" width="550"/><br>

 Dentro de este fichero indicamos:<br> 
-Qué imagen base utilizaremos<br>
-Qué paquetes vamos a instalar<br>
-La página de la que copiamos nuestro código fuente<br>
-Indicamos el servicio que ejecutará el contenedor <br> 

Editaremos el Dockerfile tal y como se muestra en la siguiente imagen:</p><br>

<img src="media/3.Ciclo de vida de la aplicacion/3-5.png" height="400" width="550"/><br>

<p>Ahora crearemos una imagen, utilizando el siguiente comando:<br></p>

<img src="media/3.Ciclo de vida de la aplicacion/3-6.png" height="400" width="550"/><br>

<p>Podemos listar todas las imágenes que tenemos creadas con el comando que se muestra a continuación</p><br>

<img src="media/3.Ciclo de vida de la aplicacion/3-7.png" height="400" width="550"/>
<br>
<p>Creamos y ejecutamos un contenedor y lo listamos para ver si realmente si han creado los contenedores</p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-8.png" height="400" width="550"/>
<br>
<p>Comprobaremos el funcionamiento de nuestra web mediante un navegador Web llamado links por lo que nos lo instalaremos</p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-9.png"
 height="400" width="550"/>
<br>
<p>Abrimos nuestra aplicación links</p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-10.png" height="400" width="550"/>
<br>
<p>Para que pueda ver todas la utilidades que tiene el programa lins tendremos que presionar la tecla ESC</p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-11.png" height="400" width="550"/>
<br>
<p>Una vez presionada la letra esc , nos vamos a file y a continuación vamos a go to URL</p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-12.png"
 height="400" width="550"/>
<br>
<p>Para comprobar el funcionamiento de nuestra web debemos poner la ip de la misma </p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-13.png" height="400" width="550"/>
<br>
<p>Para salir del navegador pulsamos la tecla q</p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-14(para salir del navegador links, darle a _q_ en el teclado).png" height="400" width="550"/>
<br>
<p>A continuación nos tendremos que registrar en DockerHub para poder entrar desde la consola con el siguiente comando <p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-15(crearse cuenta en dockerhub para iniciar sesion)).png" height="400" width="550"/>
<br>
<p>Pondremos nuestro usuario y contraseña para poder acceder a DockerHub</p><b>
<img src="media/3.Ciclo de vida de la aplicacion/3-16.png"
 height="400" width="550"/>
<br>
<p>Subimos la imagen con el nombre de v1</p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-17.png"
 height="400" width="550"/>
<br>
<p>Tendrá que aparecer una imagen similar a esta si se ha subido la imagen correctamente a DockerHub <p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-18.png" height="400" width="550"/>
<br>
<p>Comprobamos desde nuestro navegador que se ha subido correctamente al repositorio adecuado<p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-19.png"  height="400" width="550"/>
<br>
<p>Nos bajamos la imagen que nos habíamos creado y subido anteriormente<p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-20.png" height="400" width="550"/>
<br>




<p>Después de ejecutar el comando anterior nos debe aparecer una imagen similar a <br> esta:<br></p>
<img src="media/3.Ciclo de vida de la aplicacion/3-21.png"  height="400" width="550"/>
<br>

<p>Ahora modificaremos el contenido de la página web que hemos creado anteriormente con los siguientes comandos:<p><br>

<img src="media/3.Ciclo de vida de la aplicacion/3-22.png"  height="400" width="550"/>
<br>

<p>Y cambiaremos el contenido por ‘Prueba2’, como se muestra en la siguiente imagen:</p><br>

<img src="media/3.Ciclo de vida de la aplicacion/3-23.png" height="400" width="550"/>
<br>

<p>Ahora construiremos una nueva imagen con el nuevo contenido, utilizando el siguiente comando:</p><br>

<img src="media/3.Ciclo de vida de la aplicacion/3-24.png"  height="400" width="550"/>
<br>

<p>Después de crearla aparecerá algo similar a la siguiente imagen:</p><br>

<img src="media/3.Ciclo de vida de la aplicacion/3-25.png"  height="400" width="550"/>
<br>

<p>Listamos todas las imágenes que tenemos, con  el siguiente comando:</p><br>

<img src="media/3.Ciclo de vida de la aplicacion/3-26.png"  height="400" width="550"/>
<br>

<p>Subiremos la imagen que hemos creado con este comando:</p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-27.png"  height="400" width="550"/>
<br>

<p>Borramos el contenedor actual con el siguiente comando:</p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-28(para eliminar el contenedor).png" height="400" width="550"/>
<br>
<p>Nos tendrá que aparecer algo similar a esta imagen:<p></br>
<img src="media/3.Ciclo de vida de la aplicacion/3-29.png" height="400" width="550"/>
<br>
<p>Y así comprobamos que nos sale prueba2</p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-30.png" height="400" width="550"/>
<br>

<p>También podemos ver desde DockerHub, las dos versiones que hemos<br> subido.</p></br>
<img src="media/3.Ciclo de vida de la aplicacion/3-31.png" height="400" width="550"/>
<br>


<h2>Volúmenes Persistentes</h2>
<br>
<p>Creamos un contenedor con un servidor MySQL , para que sus datos se almacenen en un contenedor persistente</p><br>
<img src= "media/4.Volumenes persistentes/4-1.png"  height="400" width="550"/>
<br>
<p>Para comprobar que hemos guardado correctamente la Base de Datos pondremos el siguiente comando</p><br>
<img src= "media/4.Volumenes persistentes/4-3(para comprobar que se ha guardado la base de datos en el host).png"  height="400" width="550"/>
<br>
<p> Creamos de nuevo otro contenedor con un servidor MySQL para ello pondremos este comando :  docker run - nombre some-mysql2 -v / opt / mysql: / var / lib / mysql -e MYSQL_ROOT_PASSWORD = asdasd -d mysql </p>
<br>
<p>Se comprueba que todavía sigue en pie el contenedor </p><br>
<img src  = "media/4.Volumenes persistentes/4-4.png" height="400" width="550"/>
 <br>
<p>Cuando presionamos enter en el comando anterior habrá que poner la contraseña que se definió en el MySQL</p><br>
<img src="media/4.Volumenes persistentes/4-5(en enter password hay que poner la contraseña que pusimos anteriormente en la primera captura).png"  height="400" width="550"/><br>
<p>Para crear un Base de Datos dentro del servidor de MySQL</p>
<img src = "media/4.Volumenes persistentes/4-6(para crear base de datos).png" height="400" width="550"/>
<br>
<p>Comprobamos si realmente ha sido creada la base de datos</p><br>
<img src = "media/4.Volumenes persistentes/4-7(comprobamos que ahí están creados los 2).png" height="400" width="550"/>
<br>
<p>Salimos de las dos Base de datos creadas </p><br>
<img src="media/4.Volumenes persistentes/4-8(exit para salir de los 2).png" height="400" width="550"/>
<br>
<p>Eliminamos el contenedor anterior y creamos otro</p><br>
<img src="media/4.Volumenes persistentes/4-9(eliminamos el contenedor anterior mysql y creamos otro).png" height="400" width="550"/>
<br>
<p>Creamos una nueva base de datos llamada dbTest y la visualizamos con el comando propio de MySQL show databases;</p>
<img src="/media/4.Volumenes persistentes/4-10(comprobamos que sigue estando las bases de datos creadas anteriormente).png"  height="400" width="550"/>
<br>
<h2>Wordpress</h2>
<br> 
<p>Para instalar Wordpress necesitamos crear 2 contenedores, uno de ellos para<br>  Wordpress y otro para la base de datos.</p><br>
<p>Primero crearemos el servidor para la base de datos, que será el contenedor<br>  ‘servidor_mariadb’, utilizaremos el siguiente comando:</p><br>

<img src="media/5.Wordpress/5-1(creamos un contenedor para el servidor de la base de datos).png" height="400" width="550"/><br>

<p>Cuando se instale nos debe salir una imagen parecida a esta:</p><br>

<img src="media/5.Wordpress/5-2.png" height="400" width="550"/> <br>

<p>También crearemos un contenedor para Wordpress, este contenedor se enlaza con<br> el contenedor de la base de datos, lo llamaremos ‘servidor_wp’. Para ello utilizamos<br> este comando:</p><br>
<img src="media/5.Wordpress/5-3(creamos un contenedor para wordpress).png" height="400" width="550"/><br>

<p>Cuando ejecutemos el comando nos debe aparecer algo parecido a la siguiente<br> imagen:</p><br>

<img src="media/5.Wordpress/5-4.png" height="400" width="550"/> <br>

<p>Podemos conectarnos a la URL desde la máquina virtual con docker, para ello<br>  necesitamos la ip del servidor, que la obtendremos mediante el siguiente comando:</p><br>

<img src="media/5.Wordpress/5-5(comprobamos que ip tiene asignada con el comando que aparece en la imagen).png" height="400" width="550"/><br>

<p>Utilizaremos la herramienta links, que hemos instalado anteriormente, en la esquina<br> superior izquierda nos aparece una opción ‘Go to URL’, ahora introduciremos la ip<br>
que hemos obtenido con el comando anterior: </p><br>

<img src="media/5.Wordpress/5-6(y comprobamos que funciona el wordpress).png" height="400" width="550"/><br>

<p>Por último nos aparece esta página con Wordpress y así vemos que funciona.</p><br>

<img src="media/5.Wordpress/5-7(funciona!).png" height="400" width="550"/><br>
