El procedimiento para los respaldos para el 10.130.0.7 como para el 10.130.0.8 es el mismo.

1. Primeramente debemos ingresar al servidor donde queremos hacer el respaldo, luego de eso nos ubicamos en el Disco Local (D:).

2. Ubicamos la carpeta "BACKUP", en dicha carpeta están los ".db" de todos los clientes.

3. En este paso tenemos 2 tipos de respaldos que aplicar, individual y grupal.
   
- **RESPALDO GRUPAL:**
     - Si tienes varios archivos del mismo cliente, selecciónalos y agrégalos al WinRAR con la siguiente estructura:
       
     - **EN LA PESTAÑA "GENERAL":*
     - **Archivo de formato / Archive Format:** Colócalo en (ZIP).
     - **Opciones de Archivo / Archiving options:** Marca "eliminar archivos después de archivarlos" / "delete files after archiving".
       
     - ![[Pasted image 20250910104131.png]]
    
     **EN LA PESTAÑA "BACKUP":**
     **Opciones de Backup / Backup Options:** Marca la casilla, "Generate archive name by mask" / "Generar nombre de archivo por máscara" y establece el siguiente formato: ¨_dd-mm-yyyy¨.
     
     ![[Pasted image 20250910104633.png]]
     ![[Pasted image 20250910104633.png]]
     
     *Luego de eso aplica los cambios, ejecuta el ".bat" que se encuentra en el escritorio para iniciar el proceso de respaldo.*
     
- **RESPALDO INDIVIDUAL:**
	- Si tienes varios archivos de diferentes clientes, selecciónalos con WinRAR y aplica la siguiente configuración.
	  
	  **EN LA PESTAÑA "GENERAL":**
	- **Archivo de Formato / Format Archive:** Colócalo en (ZIP).
	- **Opciones de Archivo / Archiving options:** Marca "eliminar archivos después de archivarlos" / "delete files after archiving".
	  
	- ![[Pasted image 20250910104131.png]]
	  
	  **EN LA PESTAÑA "FILES":**
	- **Archive / Archivo:** Selecciona "Put each file to separate archive" / "Coloque cada archivo en un archivo separado".
	  
	  ![[Pasted image 20250910145800.png]]
	  
	  **EN LA PESTAÑA "BACKUP":** 
	 **Opciones de Backup / Backup Options:** Marca la casilla, "Generate archive name by mask" / "Generar nombre de archivo por máscara" y establece el siguiente formato: ¨_dd-mm-yyyy¨.
	 
	 ![[Pasted image 20250910104633.png]]
	 
	 *Luego de eso aplica los cambios, ejecuta el ".bat" que se encuentra en el escritorio para iniciar el proceso de respaldo.*