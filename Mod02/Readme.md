# Lab 02: Implement task processing logic by using Azure Functions

## Architecture:
![architecture_01](ZZ-lab/architecture_02.png)


### Crear una aplicación de Azure Functions en Azure Portal. 
![Lab0200](ZZ-lab/Lab0200.png)

### Connection String Key 1:

```
DefaultEndpointsProtocol=https;AccountName=funcstorgeoconda;AccountKey=2Y+fcKbyCujCLFrR4hjgXIk9pQbEmS0yEiaMdOYNxxaiFNwxamJfvKPgDI55yne/JbJson00nar1PrqoEvG3aA==;EndpointSuffix=core.windows.net
```
## Creacion un proyecto de Azure Functions local con las herramientas principales de Azure Functions.
![Lab0203](ZZ-lab/Lab0203.png)
### Configuracion de la API Web
![Lab0201](ZZ-lab/Lab0201.png)

### Configuración de la Web App
![Lab0103](ZZ-lab/Lab0103.png)

### Código Az-CLI para desplegar el api rest

```
az webapp deployment source config-zip --resource-group ManagedPlatform --src api.zip --name imgapigeoconda
```

### Código Az-CLI para desplegar el web app

``` 
az webapp deployment source config-zip --resource-group ManagedPlatform --src web.zip --name imgwebgeoconda
```


## Comprobación que las web api funcione correctamente.
![Lab0104](ZZ-lab/Lab0104.png)

## Comprobación que la web app funcione correctamente.
![Lab0105](ZZ-lab/Lab0105.png)

### URL WEB APP:

```
https://imgwebgeoconda.azurewebsites.net/
