Para instalar Fastfetch en Debian, estas son las opciones más comunes:

## Opción 1: Usar paquete .deb desde GitHub

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