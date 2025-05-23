# Árbol de directorios

![Arbol de directorios de Linux](https://media.geeksforgeeks.org/wp-content/uploads/20230516105759/151.webp)

1. / (Raiz): directorio raíz de toda la jerarquía del sistema de archivos, El único usuario root tiene derecho a escribir en este directorio.
2. /bin: Contiene ejecutables binarios, Los comandos utilizados por todos los usuarios del sistema se encuentran aquí e.g. ps, ls, ping, grep, cp
3. /boot: Archivos del cargador de arranque, archivos kernel initrd, vmlinux, grub
4. /dev: Archivos de dispositivo esenciales, dispositivos terminales, USB o cualquier dispositivo conectado al sistema, /dev/null.
   1. /dev/null, es como un agujero negro donde lo que se arroje no se podrá recuperar, muy usado para evitar mensajes de error. ¿Cómo especificamos que sea en caso de error?  Aquí entran los valores estándar de entrada, salida y error para un programa: STDIN, STDOUT y STDERR (que pueden ser sustituidos por 0, 1 y 2 respectivamente)
    ~~~bash
    usuario@laptop:~$ cat pruebas 2>/dev/null
    usuario@laptop:~$
    ~~~
5. /etc: Archivos de configuración de todo el sistema específicos del host. contiene scripts de shell de inicio y apagado utilizados para iniciar/detener programas individuales.
6. /home: Directorios de inicio para que todos los usuarios almacenen sus archivos personales
7. /lib: Bibliotecas esenciales para los binarios en /bin/ y /sbin/.
8. /media: Puntos de montaje para medios extraíbles como CD-ROM. Directorio de montaje temporal para dispositivos extraíbles.
9. /mnt: Directorio de montaje temporal donde los administradores de sistemas pueden montar sistemas de archivos.
10. /opt: Paquetes de software de aplicación opcionales. Contiene aplicaciones complementarias de proveedores individuales.
11. /sbin: Binarios esenciales del sistema, por ejemplo, fsck, init, route. Al igual que /bin, /sbin también contiene ejecutables binarios. Los comandos de Linux que se encuentran en este directorio suelen ser utilizados por los administradores de sistemas con fines de mantenimiento del sistema.
12. /srv: Datos específicos del sitio servidos por este sistema, como datos y scripts para servidores web, datos ofrecidos por servidores FTP y repositorios para sistemas de control de versiones. Contiene datos relacionados con servicios específicos del servidor.
13. /tmp: Archivos temporales. A menudo no se conserva entre los reinicios del sistema y puede tener un tamaño muy restringido. Los archivos de este directorio se eliminan cuando se reinicia el sistema.
14. /usr: Jerarquía secundaria para datos de usuario de solo lectura; Contiene la mayoría de las utilidades y aplicaciones (multi)usuario. Contiene binarios, bibliotecas, documentación y código fuente para programas de segundo nivel.
    1.  /usr/bin contiene archivos binarios para programas de usuario. Si no puede encontrar un binario de usuario en /bin, busque en /usr/bin. Por ejemplo: at, awk, cc, less, scp
    2.  /usr/sbin contiene archivos binarios para los administradores del sistema. Si no puede encontrar un binario del sistema en /sbin, busque en /usr/sbin. Por ejemplo: atd, cron, sshd, useradd, userdel
    3.  /usr/lib contiene bibliotecas para /usr/bin y /usr/sbin
    4.  /usr/local contiene los programas del usuario que se instalan desde el código fuente. Por ejemplo, cuando instala apache desde el código fuente, va a /usr/local/apache2
    5.  /usr/src contiene las fuentes del kernel de Linux, los archivos de cabecera y la documentación.
15. /proc: Sistema de archivos virtual que proporciona información sobre el proceso y el kernel como archivos. Se trata de un sistema de archivos virtual con información de texto sobre los recursos del sistema. Por ejemplo: /proc/uptime.

## ¿Cómo se estructura el árbol de directorios en Linux?
El árbol de directorios en un sistema operativo Linux puede parecer complicado al principio, pero conocer su estructura es vital si deseas administrar eficientemente el sistema. En este artículo, desglosaremos algunas de las carpetas más importantes, cómo explorar estos directorios y su propósito en el sistema.

## ¿Cuál es el propósito del directorio bin?
El directorio bin es crucial ya que almacena todos los archivos binarios ejecutables necesarios para el funcionamiento del sistema operativo. Aquí es donde el sistema busca los programas ejecutables, como bash. Si queremos instalar un nuevo programa para que sea ejecutable a nivel de sistema, deberíamos colocarlo en esta carpeta.

~~~bash
cd /bin
ls -la
~~~

## ¿Qué contiene la carpeta boot?
La carpeta boot alberga importantes archivos de configuración necesarios para el arranque del sistema. Un archivo de especial interés es grub-config, el cual no debería ser editado directamente ya que contiene las directrices de arranque del sistema operativo.

~~~bash
cd /boot
ls -la
cat grub/grub-config
~~~

## ¿Cuál es la función del directorio dev?
A diferencia de lo que podría sugerir su nombre, el directorio dev no está relacionado con el desarrollo sino con los "devices" (dispositivos). Contiene archivos que se refieren a los dispositivos conectados al sistema. Un archivo notable es dev/null, útil para redirigir salidas no deseadas sin dejar rastro:

~~~bash
cd /dev
ls -la
echo "hola mundo" > /dev/null
~~~

## ¿Qué tipos de archivos y configuraciones se encuentran en etc?
El directorio etc es vital ya que contiene todos los archivos de configuración críticos del sistema. Entre estos se encuentra sudoers, que gestiona los permisos de superusuario, y hostname, que define el nombre del host del sistema:

~~~bash
cd /etc
ls -la
~~~

## ¿Qué se guarda en la carpeta home?
En home, se almacenan los archivos personales de cada usuario del sistema. Al crear un usuario, se le asigna un directorio aquí, que puede contener subcarpetas para organizar documentos, música, descargas, etc.

~~~bash
cd /home
ls
~~~

## ¿Por qué son importantes las carpetas lib y lib64?
Las carpetas lib y lib64 contienen librerías necesarias para que las aplicaciones ubicadas en bin o sbin puedan funcionar correctamente. Son esencialmente dependencias que las aplicaciones buscan y utilizan.

~~~bash
cd /lib
ls -la
cd /lib64
ls -la
~~~

## ¿Cuál es el rol de media y mount?
Media y mount son directorios designados para montar dispositivos de almacenamiento. Mientras que media suele usarse para discos que se van a usar a largo plazo, mount frecuentemente se reserva para dispositivos temporales como USBs.

~~~bash
cd /media
ls -la
cd /mount
ls -la
~~~

## ¿Cómo se utiliza el directorio opt?
La carpeta opt se reserva para aplicaciones opcionales de terceros, como programas que no vienen por defecto en el sistema, por ejemplo, herramientas de auditoría de seguridad.

~~~bash
cd /opt
ls -la
~~~

## ¿Cómo se maneja la carpeta proc y para qué sirve?
Proc contiene archivos en forma de referencias que muestran los procesos activos en el sistema. No es un sistema mágico; cada proceso tiene su representación aquí.

## ¿Qué tipo de información se encuentra en var?
Var es un directorio destinado a archivos e información que cambia constantemente, como logs, correos y archivos de spool. Los logs de cada crash del sistema se guardan aquí.

~~~bash
cd /var
ls -la
~~~

## ¿Qué procesos se encuentran en run y qué papel juegan?
Run contiene información sobre procesos y demonios que se ejecutan al inicio del sistema. Es esencial para gestionar qué servicios están activos tras cada arranque.

## ¿Es segura la modificación en system y qué contiene?
El directorio system resguarda archivos vitales del sistema operativo, como configuraciones de firmware y del kernel. Se recomienda no modificar su contenido a menos que sepas lo que estás haciendo.

Por cada directorio mencionado, es esencial recordar su propósito y contenido, ya que juegan un papel clave en el mantenimiento y funcionamiento adecuado de un sistema Linux. Si alguna vez duda sobre qué acción tomar, consulte siempre documentación de confianza o siga aprendiendo en cursos especializados.