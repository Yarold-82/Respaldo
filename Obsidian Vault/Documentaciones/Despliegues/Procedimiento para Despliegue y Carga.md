Para realizar el despliegue de servicio ya sean (.ear, .jar) o actualizar las plantillas (.fo), se han de realizar los siguientes pasos.
# PASO 1: Respaldo de los documentos actuales.

En las carpetas donde se encuentren dichos documentos (.jar, .ear, .fo), debe de estar una carpeta aparte de nombre "old", primero copiamos, al archivo en uso (.jar, .ear, .fo) y pegamos en dicha carpeta.
# PASO 2: Reemplazo de Archivo

Tomar el archivo a la mano otorgado por los desarrolladores y reemplazar el (.jar, .ear, .fo) correspondiente a la actividad.
# PASO 3: Desplegar Servicio (.jar)

Ingresar en el navegador para desplegar el (.jar), se debe ubicar el servicio y aplicar lo siguiente:

1. Undeploy: Para bajar el servicio.
2. Deploy: Para desplegar el servicio actualizado. (Se tendrá que buscar la ruta).

Luego de eso, se tendrá que validar con el DEV que los cambios aplicados estén funcionando, en caso contrario se tendrá que revertir.
# PASO 4: Respaldo en git.

Luego de verificar que todos los cambios estén operando de manera correcta junto con el dev, se tendrá que hacer un respaldo en git, abriendo el explorador de archivos donde se encuentre la carpeta ".git" y en la barra de búsqueda abrir el CLI, luego se tendrán que aplicar los siguientes comandos.

git add .:Agregar cambios al backstage.
git status: Verificar archivos a cambiar.
git commit "Cambios aplicados": Registrar cambios.
git log: Verificar commit aplicado
# PASO 5: Enviar Correo

Verificar respaldo previo antes de iniciar los cambios "git log", en la ruta del  servicio. Tener a la mano los documentos a reemplazar (.ear, .jar, .fo) de igual forma consultar con el dev los documentos a remplazar para el despliegue.

Cuando se reemplacen los archivos, se debe registrar el cambio en git usando los siguientes comandos:
   
git add . (Para agregar todos los archivos)
git status (Verificar el estatus de los archivos)
git log (Rectificar el histórico y cambios aplicados)