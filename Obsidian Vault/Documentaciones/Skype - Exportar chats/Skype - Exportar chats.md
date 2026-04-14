#### Paso 1: Generar la Exportación

Primero debemos acudir al siguiente enlace para generar la exportación de la conversación.

URL: https://secure.skype.com/es/data-export

Una vez dentro de la web, es importante marcar los siguientes checks, seguidamente va a oprimir, "Enviar solicitud", ver *image-01* de ejemplo: 

![[Pasted image 20250331103228.png]]
*image-01*
#### Paso 2: Descargar la "Exportaciones Disponibles":

Para encontrar esta opción solo debes subir un poco más en la misma ventana, al ubicar las "Exportaciones Disponibles", oprime "Descargar" del archivo creado ver *image-02* de ejemplo.

![[Pasted image 20250331104111.png]]
*image-02*
#### Paso 3: Extraer el ".zip"

Al descargar el archivo puede tener el siguiente nombre "8_live_.cid.e6cb5e2f6ca42a6a_export", extraemos la carpeta y tendremos los siguientes archivos, en mi caso (*image-03*):

endpoints.json
messages.json
media(folder)
*image-03*
![[Pasted image 20250331110034.png]]
*image-03*
#### Paso 4: Ver las conversaciones exportadas 

Debe utilizar el vinculo directo al visor de mensajes de skype, el cual es el siguiente:

https://go.skype.com/skype-parser

Una vez hecho eso, se descargara el siguiente archivo (.zip), *image-04*.

![[Pasted image 20250331135938.png]]
*image-04*

Al descomprimirlo tendrás el siguiente documento *image-05*, donde tendrás que cargar los .json.
![[Pasted image 20250331135919.png]]
*image-05*


![[Pasted image 20250331140457.png]]*image-05*

Ya cuando veas la siguiente imagen, tendrás a tu disposición todas las conversaciones que tenias cuando utilizabas el skype, *image-06*.

![[Pasted image 20250331140604.png]]

Lo realmente importante en este caso es no perder la fuente de la información que vendrían siendo los (.json).