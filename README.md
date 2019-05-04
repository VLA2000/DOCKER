**Project: “Cloud Computing in European schools”**  
<img src="/media/cloud-computing-logoproject.jpg" height="100" width="170">

 Number: Project: 2019-4-ES01-KA202-038471

<img src="/media/cofinanciadoEN.png" height="50" width="200"> <img src="/media/logoIES-Modificado.png" height="75" width="200">  




# Introducción a PaaS: desarrollar, implementar, ejecutar y administrar aplicaciones en la nube
  



#### Disclaimer
&nbsp;&nbsp;&nbsp;  *"El apoyo de la Comisión Europea para la producción de esta publicación no constituye una aprobación de los contenidos que refleje únicamente las opiniones de los autores, y la Comisión no se hace responsable del uso que pueda hacerse de la información contenida en el mismo."*




#### Autores

&nbsp;&nbsp;&nbsp;  Este trabajo está realizado por Manuel Santos, José Antonio Busto, José María Parrilla y Víctor López bajo la licencia Creative Commons :  <img src="/media/Licencia-Tipo2.png" height="25" width="75">
  



### Objetivo
&nbsp;&nbsp;&nbsp; Plataforma como servicio(PaaS), es un modelo de computación en la nube que permite a los usuarios desarrollar, implementar, ejecutar y administrar aplicaciones sin preocuparse por las capas subyacentes. Las alternativas utilizadas hoy se centran en el uso de contenedores que promueven el enfoque de desarrollo de **aplicaciones basado en microservicios** (frente a **aplicaciones monolíticas**), ya que los diferentes servicios en los que estamos separados de la aplicación pueden ejecutarse fácilmente en diferentes contenedores. Realizaremos un estudio de Docker, Kubernetes y OpenShift para desarrollar, implementar, ejecutar y administrar aplicaciones basadas en microservicios.

&nbsp;&nbsp;&nbsp; Esta actividad ha sido desarrollada para desarrollar la competencia profesional incluida en el proyecto Erasmus + "Cloud Computing en escuelas europeas".
<br>
## Indice
- Instalación de Vagrant y Virtualbox
- Instalación de Docker
- Ciclo de vida de la aplicación
- Volúmenes persistentes
- Wordpress

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
<p>Dentro del archivo Vagrantfile pondremos la siguiente información dada <a href="https://github.com/iesgn/cloudandrelated/blob/master/paas/doc/Vagrantfile">aquí</a>:</p>
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

<p>Ya con la máquina arrancada y conectados, lo primero que debemos hacer es crear una aplicación, en este caso vamos a<br> crear una página web llamada ‘index.html’, que va a ser servida por un servidor web, que se ejecutará en un contenedor Docker, para ello crearemos una carpeta ‘public_html’ que contendrá nuestra página web, utilizamos los siguientes comandos:</p><br>
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
<p>Para salir del navegador pulsamos la tecla "q":</p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-14(para salir del navegador links, darle a _q_ en el teclado).png" height="400" width="550"/>
<br>
<p>A continuación, previamente registrados en Dockerhub, tendremos que iniciar sesión con el siguiente comando para poder seguir trabajando:<p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-15(crearse cuenta en dockerhub para iniciar sesion)).png" height="400" width="550"/>
<br>
<p>Pondremos nuestro usuario y contraseña para poder acceder a DockerHub:</p><b>
<img src="media/3.Ciclo de vida de la aplicacion/3-16.png"
 height="400" width="550"/>
<br>
<p>Subimos la imagen como primera version de nuestro proyecto:</p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-17.png"
 height="400" width="550"/>
<br>
<p>Tendrá que aparecer una imagen similar a esta si se ha subido la imagen correctamente a DockerHub: <p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-18.png" height="400" width="550"/>
<br>
<p>Comprobamos desde nuestro navegador que se ha subido correctamente al repositorio adecuado:<p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-19.png"  height="400" width="550"/>
<br>
<p>Para descargarnos un proyecto de una cuenta de Dockerhub tenemos que utilizar el siguiente comando:<p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-20.png" height="400" width="550"/>
<br>




<p>Después de ejecutar el comando anterior nos debe aparecer una imagen similar a <br> esta:<br></p>
<img src="media/3.Ciclo de vida de la aplicacion/3-21.png"  height="400" width="550"/>
<br>

<p>Ahora realizaremos una segunda version de nuestro proyecto, modificando el contenido de la página web que hemos creado anteriormente, y lo actualizaremos en nuestro Dockerhub.<p><br>
 <p>Empezaremos utilizando el siguiente comando:

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

<p>Borramos el contenedor que anteriormente creamos de la primera version con el siguiente comando:</p><br>
<img src="media/3.Ciclo de vida de la aplicacion/3-28(para eliminar el contenedor).png" height="400" width="550"/>
<br>
<p>Y seguidamente, crearemos el contenedor "pruebadocker2" de la segunda version:<p></br>
<img src="media/3.Ciclo de vida de la aplicacion/3-29.png" height="400" width="550"/>
<br>
<p>Y comprobaremos que nos sale prueba2 en links:</p><br>
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
<p>Salimos de la Base de datos creada </p><br>
<img src="media/4.Volumenes persistentes/4-8(exit para salir de los 2).png" height="400" width="550"/>
<br>
<p>Ahora, veremos como creando un contenedor nuevo, seguirá estando las base de datos creadas en el antiguo contenedor, viendo que en los contenedores no se almacena la información.</p><br>
<p>Eliminamos el contenedor anterior y creamos otro llamado mysql2</p><br>
<img src="media/4.Volumenes persistentes/4-9(eliminamos el contenedor anterior mysql y creamos otro).png" height="400" width="550"/>
<br>
<p>Entraremos dentro de ese nuevo contenedor y comprobaremos que las bases de datos creadas en el anterior contenedor siguen estando en el nuevo contenedor:</p>
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
