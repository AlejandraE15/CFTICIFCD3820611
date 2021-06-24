# Lab 07: Access resource secrets more securely across services
![architecture_07](ZZ-lab/Architecture_07.png)

## Exercise 1: Create Azure resources
* Creo un grupo de recurso en el cual tenga, una cuenta de almacenamiento, una Key Vault y una function app, dentro de la cual tendré una Application Insights.
![Lab0700](ZZ-lab/Lab0700.png)

## Exercise 2: Configure secrets and identities

* Configurar una identidad de servicio administrado asignada por el sistema
![Lab0701](ZZ-lab/Lab0701.png)
* Creo una Key Vault secreta.
*Aqui utilizaré mi Connection String*
 ``` DefaultEndpointsProtocol=https;AccountName=securestorgeoconda;AccountKey=WuhcTUtwBwSAmSDNO2Rup4D3rZtxMtLB+yWur1L685KYFKLQ65R1ugvAuAbOOa40CxQ22jYSq+5jSB3zuCkwTQ==;EndpointSuffix=core.windows.net 
 ```
![Lab0702](ZZ-lab/Lab0702.png)

* Configuración de una directiva de acceso de Key Vault
![Lab0703](ZZ-lab/Lab0703.png)

* Creación de una configuración de aplicación derivada de Key Vault
![Lab0704](ZZ-lab/Lab0704.png)

*Valor utilizado*
 ``` 
@Microsoft.KeyVault(SecretUri=https://securevaultgeocondae.vault.azure.net/secrets/storagecredentials/27c8051c3f534134830b2cca7b6368b7)

 ``` 
## Exercise 3: Build an Azure Functions app
*  Inicio un proyecto de función.
![Lab0705](ZZ-lab/Lab0705.png)


 
* Dentro de mi proyecto, modifico el código de mi local.settings.json quedando así:
 ```
 {
     "IsEncrypted": false,
     "Values": {
         "AzureWebJobsStorage": "UseDevelopmentStorage=true",
         "FUNCTIONS_WORKER_RUNTIME": "dotnet",
         "StorageConnectionString": "[TEST VALUE]"
     }
 }

 ```

https://hrtopicgeoconda.eastus-1.eventgrid.azure.net/api/events

Access Key 1 :
KgHrASIfUpVvRMDcqzXYNW4/MZY8JpLMhpyxBswUZeM=
```
![Lab0706](ZZ-lab/Lab0706.png)
* Finalmente observo como aparecen mis nuevas publicaciones.
![Lab0707](ZZ-lab/Lab0707.png)
