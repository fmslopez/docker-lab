# docker-lab
# Ejercicio 1

Ejecuta un contenedor basado en la imagen:
ubuntu
 
Accede a la terminal del contenedor.

<img width="1196" height="675" alt="captura 2" src="https://github.com/user-attachments/assets/877e1bdf-099a-4b94-8751-c0fc505c416f" />
<img width="997" height="187" alt="captura 1" src="https://github.com/user-attachments/assets/1d1f9f77-3d7d-40c4-bda0-3cf703f14ef8" />


Levanto el contenedor llamado contenedor e incluyo –it para acceder de forma interactiva a su interior, sistema operativo
Instala curl:
apt-get update

<img width="1462" height="535" alt="captura 3" src="https://github.com/user-attachments/assets/ab80d5fc-1fda-43d8-95a9-7ed33c7f4c9f" />

Comprueba que funciona:
curl –version

<img width="1478" height="221" alt="captura 4" src="https://github.com/user-attachments/assets/627d709c-0abb-47e7-bfba-276c04d4d083" />

Pregunta
¿Con qué comando podrías guardar los cambios del contenedor como una nueva imagen?
Con docker commit

Paso 2 --- Dockerfile
Crea un Dockerfile que haga lo mismo automáticamente.
Ejemplo:
FROM ubuntu

RUN apt-get update && apt-get install -y curl

<img width="968" height="377" alt="captura 5" src="https://github.com/user-attachments/assets/17e64574-dd39-48de-abac-4dfcf82c4300" />


Construye la imagen y ejecuta un contenedor.

<img width="1504" height="285" alt="captura 6" src="https://github.com/user-attachments/assets/77f501bb-df38-4e32-89f5-
dbda6467ce8e" />

Construyo la imagen con el comando anterior y le indico donde se encuentra el fichero Dockerfile en este caso se indica . para indicarle que está en este directorio. Mucho ojo con lo siguiente, el fichero tiene que llamarse Dockerfile “la D en mayúsculas y se crea el fichero sin extensión en visual studio”

<img width="1899" height="429" alt="captura 7" src="https://github.com/user-attachments/assets/19c218ac-955c-4111-91af-a39309a85843" />

<img width="1904" height="335" alt="captura 8" src="https://github.com/user-attachments/assets/17c71174-6ef6-40e5-8233-64e993de0acc" />

<img width="1763" height="712" alt="captura 9" src="https://github.com/user-attachments/assets/3c6eec01-03e8-4f4d-a988-69b3473f0ccf" />


Pregunta
¿Qué comando permite ver las capas de una imagen Docker?
Docker history nombre_imagen

#Ejercicio 2






