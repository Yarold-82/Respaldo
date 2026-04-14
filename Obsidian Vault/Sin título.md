# Módulos HTB: Principios de los SO (Linux)

*Creado en 1991 por Linus Torvald

*Es un kernel que posteriormente fue hecho sistema operativo

Filosofía:

1. Todo es un archivo
2. Pequeño, programa de un propósito único
3. Capacidad de encadenar programas para rendir en tareas complejas
4. Interfaz captativa para el usuario.
5. Datos de configuración en un archivo de texto

Componentes:

1. Bootloader: Gestor de carga para el sistema operativo
2. OS kernel: Maneja los recursos de un sistema a un nivel de hardware
3. Daemon: Son los servicios que corren en segundo plano, lo que hacen utilizables los programas.
4. OS Shell (Terminal): Es lo que nos permite colocar comandos para poder interactuar con el OS
5. Servidor Grafico: Subsistema grafico que nos permite ejecutar aplicaciones que necesiten de un entorno grafico para ejecutarse
6. Windows manager: Se podría considerar como el escritorio grafico, donde podemos encontrar las aplicaciones y archivos que ahí se encuentran.
7. Utilidades: Aplicaciones de utilidad para el usuario

**Arquitectura**:

1. Hardware: Dispositivos físicos, mouse, procesador, RAM, etc.
2. Kernel: Núcleo de Linux, es lo que permite que se comuniquen el hardware y software, además de monitorear los recursos del CPU
3. Shell: Es donde se colocan los comandos para interactuar con el kernel
4. System Utility: Es lo que permite a todos los usuarios utilizar todas las utilidades.

Jerarquía de documentos del sistema.

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/d19c2d3c-741b-442a-9c76-14e94d9fc132/6337ce58-76b6-46c1-ac59-d1e98e44ee92/image.png)

Rutas/Path:

/ : Directorio root, aqui encontraremos todos los archivos necesarios para iniciar el SO

/bin: Contiene los comandos binarios escenciales para el SO

/boot: Contiene los archivos necesarios para iniciar el SO de linux

/dev: Contiene los archivos para facilitar el acceso a los dispositivos externos. /etc: Aqui se encuentran los archivos para la configuración local del sistema. También se guardan los archivos de configuración de algunas aplicaciones. /home: Contiene los subsdirectorios de cada usuario /lib: librerias compartidas necesarias para iniciar el sistema

/media: Aqui se guardan los dispositivos removibles como los USB /mnt: Punto de montura para los archivos regulares del sistema /opt: Aqui se guardan los archivos de herramientas de terceros /root: El directorio principal para el usuario root /sbin: Directorio que contiene los ejecutables usados por el sistema /tmp: Directorio donde se guardan los archivos temporales, tanto del sistema como de aplicaciones de terceros. /usr: Contiene ejecutables, librerias y archivos /var: Directorio que contiene archivos de datos variables, como logs, emails, txt relacionados a aplicaciones, etc.

# Distribuciones:

Son SO basados en el kernel de Linux.

*Ubuntu *Parrot

*Kali *Fedora *CentOS *Debian *Red hat

### Distribuciones orientadas la ciberseguridad:

*Debian *Parrot OS *Kali *CentOS

*BlackArch OS *Raspberry Pi OS

*Ubuntu *Pentoo *BackBox

# **Introducción al shell de Linux**

Es crucial aprender a usar el Shell de Linux, debido a que, en este se basa la mayoría de servidores web.

También conocida como terminal o linea de comando, es la que se encarga de interpretar la entrada y salida de código interactivo con el Kernel del SO. Podemos pensar que el Shell es la herramienta que nos ayuda a navegar a través del SO y a comunicarnos con el.

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/d19c2d3c-741b-442a-9c76-14e94d9fc132/8d353d46-c2c9-4c7a-bdf1-e9f762eb7344/image.png)

## Emuladores de Shell

Es aquel software que tiene como finalidad replicar la función de un terminal, nos permite usar una interfaz grafica de usuario, por sus siglas (GUI). En pocas palabras, es un interpretador de Shell.

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/d19c2d3c-741b-442a-9c76-14e94d9fc132/dfb61442-02bd-41d4-8726-f8bdcc63d704/image.png)

## Shell

El Shell mas usado comúnmente en Linux es el Born Again Shell o (BASH) por sus siglas en ingles. El Shell nos permite mas posibilidades de interactuar con programas y software del sistema. Por otra parte, también nos permite hacer scripts para procesos automáticos para hacer el trabajo manual mucho mas sencillo.

# Descripción de Prompts

El prompt bash es fácil de usar y entender, incluye información sobre el usuario, el directorio activo y el hostname. Normalmente se el prompt se ejecuta en una nueva linea de comando donde el cursor de dirigirá al extremo izquierdo.

Puede ser customizado con la finalidad de proveer de mas información al usuario. El formato se deberia ver de la siguiente manera:

<username>@<hostname><Current Working directory>$

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/d19c2d3c-741b-442a-9c76-14e94d9fc132/9fcbd37e-01c7-4aa1-9985-d3d80aaeee28/image.png)

El directorio de home de un usuario esta tildado como <~> y es la carpeta por default cuando nos logeamos.

<username>@<hostname>[~]$

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/d19c2d3c-741b-442a-9c76-14e94d9fc132/de1c8ea2-495a-46c4-b687-cf2ecb734ca6/image.png)

El signo de dolar en este caso quiere decir que estamos logeados como un usuario normal, tan pronto como nos loguemos como usuarios root nos aparecerá el hash (#) y se vera de la siguiente manera:

root@htb[/htb]#

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/d19c2d3c-741b-442a-9c76-14e94d9fc132/4b596d57-bac0-4318-bc90-a14bae3bd483/image.png)

Por ejemplo, cuando corremos un shell en el sistema objetivo, puede que no veamos el usuario, el hostname o el directorio activo. Puede ser debido a la variable PS1 en el entorno del sistema. En este caso, veremos el siguiente prompt:

$

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/d19c2d3c-741b-442a-9c76-14e94d9fc132/8d989208-d19a-4fb2-818f-5c7ffa3d8ef1/image.png)

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/d19c2d3c-741b-442a-9c76-14e94d9fc132/037b481c-da24-4aa6-9f43-6da146013190/image.png)

En adicción a la información ya dada, podemos customizar el display para que contenga mas información en el prompt. tal como la dirección ip, date, time, el estatus de salida del ultimo comando, etc. Esto es especialmente importante en los pen-testing podemos utilizar varias herramientas y utilidades tales como los scripts o el .bash_history para visualizar todos los comando que utilizamos filtrando por fecha y hora.

Otro ejemplo es que el prompt se puede personalizar para que nos muestra toda la ruta del directorio actual en vez de solo el nombre del directorio, lo cual también puede incluir la dirección ip si trabajamos de manera organizada.