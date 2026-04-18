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

<img width="1504" height="285" alt="captura 6" src="https://github.com/user-attachments/assets/2c4e7fa8-ed5a-4d0a-aad9-912d6b5bf451" />


Construyo la imagen con el comando anterior y le indico donde se encuentra el fichero Dockerfile en este caso se indica . para indicarle que está en este directorio. Mucho ojo con lo siguiente, el fichero tiene que llamarse Dockerfile “la D en mayúsculas y se crea el fichero sin extensión en visual studio”

<img width="1899" height="429" alt="captura 7" src="https://github.com/user-attachments/assets/19c218ac-955c-4111-91af-a39309a85843" />

<img width="1904" height="335" alt="captura 8" src="https://github.com/user-attachments/assets/17c71174-6ef6-40e5-8233-64e993de0acc" />

<img width="1763" height="712" alt="captura 9" src="https://github.com/user-attachments/assets/3c6eec01-03e8-4f4d-a988-69b3473f0ccf" />


Pregunta
¿Qué comando permite ver las capas de una imagen Docker?
Docker history nombre_imagen

# Ejercicio 2
Limpiando imágenes (opcional)
Crea un Dockerfile basado en: ubuntu
Construye la imagen.<img width="1429" height="367" alt="captura 4" src="https://github.com/user-attachments/assets/e6cfe7bc-2db3-4d81-a198-2e44defdbe05" />


<img width="1478" height="356" alt="captura 1" src="https://github.com/user-attachments/assets/269b120c-60bc-41ae-8870-c24183bad0e3" />

<img width="1279" height="608" alt="captura 2" src="https://github.com/user-attachments/assets/59c2f323-812f-4eec-b193-0b1493999c61" />

<img width="1724" height="77" alt="captura 3" src="https://github.com/user-attachments/assets/22ad1177-1df6-4c3a-9f0d-564c4fb396fb" />


Después modifica el Dockerfile para instalar:
•	curl


<img width="1429" height="367" alt="captura 4" src="https://github.com/user-attachments/assets/24e30705-2f9d-4cf2-9c31-3de7ff4fe81b" />

<img width="1247" height="630" alt="captura 5" src="https://github.com/user-attachments/assets/f29875a4-4035-46f4-a1c2-3b9c901b69fb" />


<img width="1367" height="68" alt="captura 6" src="https://github.com/user-attachments/assets/5c3513ff-f50e-4e7e-a5cb-2e1994e23fb3" />

•	después wget

imagenes 7 a 8

<img width="1572" height="393" alt="captura 7" src="https://github.com/user-attachments/assets/0a956ac3-86d9-4e62-8ca2-88710b940a24" />


<img width="1739" height="110" alt="captura 8" src="https://github.com/user-attachments/assets/12a8b3e6-40d3-4788-a2cc-a09a1e7a4de4" />


Construye la imagen en cada cambio.
Me he creado otra nueva imagen
Lista las imágenes:
docker images
 <img width="1478" height="356" alt="captura 1" src="https://github.com/user-attachments/assets/6fb0f776-a2a1-49ed-83a6-ea62c52fedde" />
<img width="1478" height="356" alt="captura 1" src="https://github.com/user-attachments/assets/40b89d99-13f2-497c-b5ab-db30630e348f" />

Pregunta:
¿Qué ocurre con las imágenes anteriores?
Las imágenes anteriores se mantienen para volver a usarlas posteriormente cuando sea necesario.

# Ejercicio 3
3. Volúmenes persistentes
Ejecuta un contenedor de:
postgres
 
Usa un volumen Docker montado en:
/var/lib/postgresql/data
 Captura 1
<img width="1875" height="100" alt="captura 1" src="https://github.com/user-attachments/assets/8a845136-8358-4b28-9240-2cd89edbf604" />


Revisando la documentación parece que el /data ya no se utiliza y hay que descartarlo, por lo tanto, en las nuevas versiones indico el comando anterior.
Creo un contenedor con nombre postgres, tengo que incluir una variable de entorno que en mi caso la he puesto como actividad3, me creo un volumen de datos llamado, para ser muy original, “datos” y lo enlazo con el directorio /data del contenedor y finalmente levanto todo esto en el puerto 5433 para mi entorno y 5432 dentro del contenedor (esto es porque he realizado una prueba antes y he utilizado el puerto 5432, pero tú puedes usar 5432:5432), tomo la imagen última de postgres. Por cierto, el –d es para “desatachar” la ejecución del contenedor al terminal y que no me lo deje bloqueado.

<img width="1874" height="230" alt="captura 2" src="https://github.com/user-attachments/assets/0825ea1f-de6c-43f9-af03-2fdedc4129e2" />


Accedemos al contenedor
Captura 3

<img width="1302" height="139" alt="captura 3" src="https://github.com/user-attachments/assets/d2b1c1e1-8f99-4c8b-8f43-22df137bc7a8" />

Usuario postgres, porque lo indican ellos, pongo el nombre del contenedor que he creado antes, accedo de forma interactiva al terminal.
Crear tabla
Conéctate a la base de datos.
Crea la tabla:
CREATE TABLE items (
 id SERIAL PRIMARY KEY,
 name TEXT
);
 
Inserta un registro:
INSERT INTO items(name) VALUES ('item1');

<img width="1346" height="397" alt="captura 4" src="https://github.com/user-attachments/assets/27d8e753-016b-4e91-82e6-da9117e848e3" />

Creo tabla e inserto registro

<img width="985" height="398" alt="captura 5" src="https://github.com/user-attachments/assets/b7162685-1979-4b43-95cf-7e0361476565" />

Me salgo del contenedor.
________________________________________
Comprobación
1.	Para el contenedor

<img width="1828" height="387" alt="captura 6" src="https://github.com/user-attachments/assets/cf239aca-0834-45bc-b52c-a86c7033d57f" />

Contenedor parado
2.	Elimina el contenedor

<img width="1867" height="93" alt="captura 7" src="https://github.com/user-attachments/assets/9ce05bb4-7690-44de-af8f-37c1c6ccd408" />


<img width="697" height="182" alt="captura 8 " src="https://github.com/user-attachments/assets/b240b46e-4c13-4540-a4d5-8ef270963abf" />


<img width="1869" height="329" alt="captura 9" src="https://github.com/user-attachments/assets/6a2a0562-0d78-4c5f-af15-dc2acac638d4" />

Contenedor eliminado
Vemos que ya no está el contenedor
3.	Crea un nuevo contenedor usando el mismo volumen


<img width="1720" height="355" alt="captura 10" src="https://github.com/user-attachments/assets/e1f8bd83-97ff-4583-876a-ebe849ad553e" />


Y en la captura anterior vemos como seguimos teniendo la misma información, a pesar de haber eliminado el contenedor anteriormente.


# Ejercicio 4

Crea un archivo en tu máquina:
index.html
 
Ejemplo:
<h1>Hola Docker</h1>

<img width="1752" height="621" alt="captura 1" src="https://github.com/user-attachments/assets/e3b627aa-b524-4266-92fe-0b5c21a16dfa" />

Ejecuta un contenedor nginx:
•	mapea el puerto 80
•	monta el archivo en:
<!-- -->
 
/usr/share/nginx/html/index.html
 
Abre el navegador.

<img width="1631" height="180" alt="captura 2" src="https://github.com/user-attachments/assets/c62e02e0-1cfa-437e-ae91-1c2273324c9c" />


Creamos un contenedor nginx denominado nginx_apartado4, expuesto en el puerto 80 y mediante un volumen tipo bind mount el cual toma el archivo index.html de mi carpeta y lo enlaza al directorio donde se deben de incluir dentro del servidor nginx.

<img width="487" height="262" alt="captura 3" src="https://github.com/user-attachments/assets/2479c55d-acb0-4f57-9eea-14b818192d94" />


Vemos que funciona
Y ahora vamos a modificar el fichero index.html en nuestra carpeta del equipo host.


<img width="1822" height="637" alt="captura 4" src="https://github.com/user-attachments/assets/2d4bb09d-4b74-406d-9a52-df30759261d6" />


Y vemos como se modifica en nuestro navegador una vez recarguemos la página, sin tener que levantar un nuevo contenedor ni otra acción sobre el mismo.

<img width="489" height="375" alt="captura 5" src="https://github.com/user-attachments/assets/102eb118-0876-4eb5-933a-30124bfa0d50" />


Pregunta:
¿Qué ocurre si modificas el archivo index.html en tu máquina?
Tal y como he comentado anteriormente, cuando actualizamos nuestra web vemos que se modifica automáticamente.


