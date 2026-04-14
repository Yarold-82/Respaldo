# Paso 1: Preparar el Servidor.
## Iniciar sesión como root:

Como "sudo" no está instalado por defecto en algunas instalaciones mínimas de Debian tendremos que instalarlo, pero antes tendrás que acceder como root:

```
su -
```

Ingresa la contraseña de root cuando se te solicite.

Si no tienes la contraseña de root, puedes configurarla con sudo passwd root en sistemas donde sudo ya esté disponible.
## Actualizar el Servidor:

Ejecuta los siguientes comandos como root:

```
apt update && apt upgrade -y
```

Esto actualiza la lista de paquetes e instala sudo.
## Instalar sudo:

```
apt install sudo -y
```
## Agregar tu usuario al grupo sudo:

Para que tu usuario pueda usar "sudo", debes añadirlo al grupo sudo:

```
usermod -aG sudo tu_usuario
```

Reemplaza "tu_usuario" con tu nombre de usuario real (ejemplo: usermod -aG sudo admin).

Verificación:

```
groups tu_usuario
```

Debe aparecer sudo en la lista de grupos.
## Cerrar Sesión y Reiniciar:

Para aplicar los cambios:

```
reboot
```

O simplemente cierra y vuelve a abrir la terminal.
## Probar sudo:

Después de reiniciar, verifica que sudo funcione:

```
sudo whoami
```

Si te pide tu contraseña y muestra root, ¡todo está correcto!
# Paso 2: Instalar Fastfetch

Para instalar Fastfetch en Debian, estas son las opciones más comunes:
## Usar paquete .deb desde GitHub

1. Actualiza el sistema:

```
sudo apt update && sudo apt upgrade -y
```

2. Descarga la última versión de Fastfetch en formato .deb (reemplaza la URL si hay una versión más nueva):

```
wget https://github.com/fastfetch-cli/fastfetch/releases/download/2.34.1/fastfetch-linux-amd64.deb
```

3. Instala el paquete descargado:

```
sudo dpkg -i fastfetch-linux-amd64.deb
```

4. Verifica la instalación ejecutando:

```
fastfetch
```

## Para Ejecutar Automáticamente

1. Abre el archivo `.bashrc` con un editor de texto, por ejemplo usando nano:

```
nano ~/.bashrc
```

2. Al final del archivo, agrega la línea siguiente para lanzar Fastfetch automáticamente:

```
fastfetch
```

3. Guarda y cierra el archivo (`Ctrl+O` para guardar y `Ctrl+X` para salir en nano).

4. La próxima vez que abras una terminal nueva, Fastfetch se ejecutará y mostrará la información del sistema automáticamente.

Este método es sencillo y funciona para shells basados en bash en Debian. Si usas otro shell o entorno, el archivo de configuración puede variar.
# Paso 3: Instalar docker

Antes de instalar Docker primero debemos comprobar y desinstalar los paquetes que puedan causar conflicto, para esto, usamos el siguiente comando:

```
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done
```

`apt-get` podría informar que no tiene ninguno de estos paquetes instalado.

Imágenes, contenedores, volúmenes y redes almacenadas en `/var/lib/docker/` no se eliminan automáticamente cuando desinstalas Docker. Si desea comenzar con una instalación limpia y prefiere limpiar cualquier dato existente, lea el [desinstalar Docker Engine](https://docs.docker.com/engine/install/debian/#uninstall-docker-engine) sección.
## [Instalar usando el repositorio `apt`](https://docs.docker.com/engine/install/debian/#install-using-the-repository)

Antes de instalar Docker Engine por primera vez en una nueva máquina host, debe configurar el repositorio `apt` de Docker. Posteriormente, puedes instalar y actualizar Docker desde el repositorio.

Configure el repositorio `apt` de Docker.

```
# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```
## Instalar paquetes de docker

```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

Verifique que la instalación sea exitosa ejecutando la imagen `hello-world`:

```
sudo docker run hello-world
```

Este comando descarga una imagen de prueba y la ejecuta en un contenedor. Cuando el contenedor se ejecuta, imprime un mensaje de confirmación y sale.
## En dado caso para desinstalar docker

Desinstale los paquetes Docker Engine, CLI, containerd y Docker Compose:

```
sudo apt-get purge docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin docker-ce-rootless-extras
```

Las imágenes, contenedores, volúmenes o archivos de configuración personalizados de su host no se eliminan automáticamente. Para eliminar todas las imágenes, contenedores y volúmenes:

```
sudo rm -rf /var/lib/docker
sudo rm -rf /var/lib/containerd
```

Eliminar lista de fuentes y llaveros

```
sudo rm /etc/apt/sources.list.d/docker.list
sudo rm /etc/apt/keyrings/docker.asc
```

Debe eliminar manualmente cualquier archivo de configuración editado.
## Agregar usuario al grupo docker

```
sudo adduser tu_usuario docker
```

Para verificar, cierra la sesión al servidor y vuelve a conectarte.
