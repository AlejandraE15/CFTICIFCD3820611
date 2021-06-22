# Lab 12: Enhancing a web application by using the Azure Content Delivery Network
![architecture_12](ZZ-lab/architecture_12.png)

### Exercise 1: Create Azure resources
![Lab1200](ZZ-lab/Lab1200.png)

* Properties URL de mi web app.

```
http://landingpagegeoconda.azurewebsites.net/
```
### Exercise 2: Configure Content Delivery Network and endpoints 
* Compruebo que el provedor Microsoft.CDN no este creado.
![Lab01201](ZZ-lab/Lab1201.png)

* Registro mi nuevo proveedor.
![Lab1202](ZZ-lab/Lab1202.png)

* Creo un CDN profile.
![Lab1203](ZZ-lab/Lab1203.png)

* En mi grupo de recursos creo dos contenedores llamados media y video.
![Lab1204](ZZ-lab/Lab1204.png)

* Dentro de mi CDN profile agrego 3 Endpoint, basados en mis 2 contenedores y mi web app.
![Lab1205](ZZ-lab/Lab1205.png)

### Exercise 3: Upload and configure static web content

* Observo mi pagina web, la cual aun no tiene contenido. 
![Lab1206](ZZ-lab/Lab1206.png)

* En mi contenedor llamado media, subo unas imágenes jpd de mi práctica.
![Lab1207](ZZ-lab/Lab1207.png)

* Por otra lado en mi contenedor llamado video, también subo un archivo mp4 .
![Lab1208](ZZ-lab/Lab1208.png)

* Configuro en los ajustes de mi Web app, añadiendo 2 aplicaciones con los valores de los contenedores creados anteriormente.
![Lab1209](ZZ-lab/Lab1209.png)

* Compruebo que mis archivos se hayan subido a mi página web.
![Lab1210](ZZ-lab/Lab1210.png)

### Exercise 4: Use Content Delivery Network endpoints

*
