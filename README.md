# Ejercicio 2:
## Primeros pasos:  
Los primeros comandos que hemos aprendido son los básicos para movernos por el terminal de Linux. Una vez ya teníamos claro los conceptos básicos pasamos a configurar nuestro usuario de Git.
### Nombre usuario
Primero se configura el nombre por medio de:
>$ git config --global user.name "Name"  

Para comprobar que ha sido configurado correctamente se puede usar el siguiente comando que devolverá el nombre:
>$ git config user.name  
### Correo usuario
Para el correo electrónico se usan comandos similares:
>$ git config --global user.email "email@email.com"  
>$ git config user.email  

---
## Generar repositorio local

El primer paso es generar un directorio que poder convertir en repositorio por medio de (siendo "repository" el nombre del directorio):
>$ git init repository 

Al usar este comando se creará una carpeta con el nombre ".git" en su interior, lo cuál nos indica que ha sido creado correctamente el repositorio.

Otra manera de generarlo es clonando un repositorio ya creado de github que puede contener archivos. Para ello se necesita la URL del directorio:  
  
![La imagen no se puede cargar](https://lornajane.net/wp-content/uploads/2012/09/repo-address.png "Tremenda imagen, verdad?")

Con este url tenemos que correr el siguiente comando en la consola:
>$ git clone URL 

---
## Asociación de los repositorios locales y remotos
Una vez tenemos ambos directorios hay que relacionarlos por medio de una serie de comandos:
>$ git remote add origin URL  
>$ git branch -M main  

Con el primero lo que hacemos es relacionarlos usando el URL del repositorio remoto. La segunda línea de comando es para cambiar el nombre de la rama a "main" en lugar de "master" por temas éticos.

Para comprobar que repositorios están asociados o si hay alguno asociado usamos el siguiente comando. En el caso de que esté asociado nos devuelve el URL y en el caso de que no lo esté no devuelve nada.

>$ git remote -v 
---
## Situación de los ficheros
Cuando creamos un fichero en el repositorio no se carga inmediatamente a la nube. Hay que seguir una serie de pasos para registrar los cambios que hemos hecho en los ficheros en ambos directorios. 

Por medio del comando de "status" podemos ver la situación global del repositorio y ver en que paso se encuentra cada fichero:

>$ git status  

---
## Staging area
Es el primer paso, donde se preparan los ficheros que se van a subir al **repositorio local** desde el area de trabajo.  
### Añadir
Para añadir estos ficheros se usa:

>$ git add file.html 

### Echar para atrás
En el caso de querer quitar uno de los ficheros de esta area y no querer subirlo al repositorio local se usa:
>$ git rm --cached file.html 
--- 
## Git commit
Una vez tenemos claro los archivos que queremos en el repositorio local, esperando en el staging area, podemos enviarlos en este paso. Es conveniente añadir comentarios que indiquen que cambios se han realizado. El siguiente comando mándará los ficheros al repositorio local:
>$ git commit -m "comment"  

Con "log" podemos ver el historial de commit, o envios, que se ha realizado:
>$ git log  
 
 Los datos que se obtienen son:

* Identificador 
* Autor
* Fecha
* Comentario

---
## Del local al remoto (PUSH)
El último paso es subir los ficheros presentes en el repositorio local al remoto a modo de seguridad o para poder compartir los avances con nuestros compañeros. Esto se realiza con un único comando:
>$ git push -u origin main  
---

## Del remoto al local (PULL)
En el caso de que los cambios se hayan realizado en el remoto por nosotros o por algún compañero el comando que hay que ejecutar para actualizar el repositorio local es:
>$ git pull origin main  
