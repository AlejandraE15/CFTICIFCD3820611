# Lab 11: Monitoring services that are deployed to Azure
![architecture_11](ZZ-lab/architecture_11.png)

### Exercise 1: Create and configure Azure resources

* Creo una Application Insights resource
![Lab1100](ZZ-lab/Lab1100.png)

* Creo una App Service.
![Lab1101](ZZ-lab/Lab1101.png)

* Configuración de las opciones de escalado automático de aplicaciones web
![Lab1102](ZZ-lab/Lab1102.png)

### Exercise 2: Monitor a local web application by using Application Insights
* Build a .NET Web API project
![Lab01103](ZZ-lab/Lab1203.png)

* Registro mi nuevo proveedor.
![Lab1104](ZZ-lab/Lab1204.png)

* Creo un CDN profile.
![Lab1105](ZZ-lab/Lab1205.png)

### Exercise 3: Upload and configure static web content

* Observo mi pagina web, la cual aun no tiene contenido. 
![Lab1106](ZZ-lab/Lab1106.png)

* En mi contenedor llamado media, subo unas imágenes jpd de mi práctica.
![Lab1207](ZZ-lab/Lab1207.png)

* Por otra lado en mi contenedor llamado video, también subo un archivo mp4 .
![Lab1108](ZZ-lab/Lab1108.png)

* Configuro en los ajustes de mi Web app, añadiendo 2 aplicaciones con los valores de los contenedores creados anteriormente.
![Lab1109](ZZ-lab/Lab1109.png)

* Compruebo que mis archivos se hayan subido a mi página web.
![Lab1210](ZZ-lab/Lab1110.png)

### Exercise 4: Use Content Delivery Network endpoints

* Pruebo mi contenido multimedia con los siguientes enlaces y si funcionan.

![Lab1111](ZZ-lab/Lab1111.png)
```
https://cdnmediageoconda.azureedge.net/campus.jpg
```
![Lab1112](ZZ-lab/Lab1112.png)
```
https://cdnmediageoconda.azureedge.net/conference.jpg
```
![Lab1113](ZZ-lab/Lab1113.png)
```
https://cdnmediageoconda.azureedge.net/poster.jpg
```
![Lab1114](ZZ-lab/Lab111  4.png)
```
https://cdnvideogeoconda.azureedge.net/welcome.mp4
```
* Actualizo las configuraciones de mi aplicación web con los calores sacados de mi CDN profile de media y video.
![Lab1115](ZZ-lab/Lab1115.png)

* Finalmente corroboro que mi pagina fucniona correctamente con el enlace de mi CDNweb.
![Lab1116](ZZ-lab/Lab1116.png)
