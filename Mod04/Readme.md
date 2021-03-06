# Lab 04: Constructing a polyglot data solution
### Arquitectura
![Architecture_4.png](ZZ-lab/Architecture_4.png)

## Exercise 1: Creating database resources in Azure
![Lab0401](ZZ-lab/Lab0401.png)
![Lab0402](ZZ-lab/Lab0402.png)


* PRIMARY CONNECTION STRING 
```
AccountEndpoint=https://polycosmosgeoconda.documents.azure.com:443/;AccountKey=TMmDFaG7IUNzbK2UJ4W7jNDv3cPZVtPOQGpRw3hPalVlkic8QWI7tH0VBbqT58UOaUYXNBT5uhFyHkJU4V40Yw==;


```

## Exercise 2: Import and validate data
* Entro a mi polystorgeoconda a traves de de mi resource groups llamado PolygotData 
![Lab0403](ZZ-lab/La0403.png)
* Ceo 2 contenedores llamados "images" y "databases"
![Lab0404](ZZ-lab/Lab0404.png)
* En mi contenedor llamado images copio el Blob Servive que esta en Endpoints 
```
https://polystorgeoconda.blob.core.windows.net/images
```
* Subo todas la imagenes que tengo en mi carpeta  C:Allfiles\Labs\04\Starter\Images 
![Lab0405](ZZ-lab/Lab0405.png)
* En el contenedor llamado databases subo el arrchivo AdventureWorks.bacpac que esta en mi C: Allfiles\Labs\04\Starter 
![Lab0406](ZZ-lab/LAb0406.png)
* En este paso he importado la database que teniamos en el contenedor "databases"  
![Lab0407](ZZ-lab/Lab0407.png)
* Dentro de mi  polysqlsrvrgeoconda. selecciono la casilla de "Firewalls and virtual networks" y elijo "Add client IP"
![Lab0408](ZZ-lab/Lab0408.png)
* Connection strings
 
``` 
Server=tcp:polysqlsrvrgeoconda.database.windows.net,1433;Initial Catalog=AdventureWorks;Persist Security Info=False;User ID=testuser;Password=TestPa55w.rd;MultipleActiveResultSets=False;Encrypt=True;TrustServerCertificate=False;Connection Timeout=30;
```
* Compruebo que en database haya lops archivos
![Lab0409](ZZ-lab/Lab0409.png)
![Lab0410](ZZ-lab/Lab0410.png)

## Exercise 3: Open and configure a .NET web application
* En este punto abrimos Powershell e introducimos "dotnet build"
![Lab0411](ZZ-lab/Lab0411.png)
* Abrimos en Visual Studio Code la carpeta que en mi caso es (C):\Allfiles\Labs\04\Starter\AdventureWorks y modificamos el codigo usando el Connection Strings y el Blob Container Url que antes guardamos.
![Lab0414](ZZ-lab/Lab0414.png)
* Validar la aplicaci??n web.
![Lab0413](ZZ-lab/Lab0413.png)
![Lab0415](ZZ-lab/Lab0415.png)

## Pasamos la p??gina de local a una App Service.
![Lab0416](ZZ-lab/Lab0416.png)
![Lab0417](ZZ-lab/Lab0417.png)
![Lab0418](ZZ-lab/Lab0418.png)

* P??gina web
```
https://polywebgeoconda.azurewebsites.net/
```

## Exercise 4: Migrating SQL data to Azure Cosmos DB

* Crear un migration project
![Lab0419](ZZ-lab/Lab0419.png)
