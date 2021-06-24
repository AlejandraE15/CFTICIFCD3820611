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

* Así mismo, en el código del archivo FilePArser.cs que he creado antes, lo modifico:
 ```
 using Microsoft.AspNetCore.Mvc;
 using Microsoft.Azure.WebJobs;
 using Microsoft.AspNetCore.Http;
 using System;
 using System.Threading.Tasks;

 public static class FileParser
 {
     [FunctionName("FileParser")]
     public static async Task<IActionResult> Run(
         [HttpTrigger("GET")] HttpRequest request)
     {
         string connectionString = Environment.GetEnvironmentVariable("StorageConnectionString");
         return new OkObjectResult(connectionString);
     }
 }

 ```
 * Validar la función local
![Lab0706](ZZ-lab/Lab0706.png)
![Lab0707](ZZ-lab/Lab0707.png)
* Implementar usando las herramientas principales de Azure Functions.
![Lab0708](ZZ-lab/Lab0708.png)
* Test the Key Vault-derived application setting
![Lab0709](ZZ-lab/Lab0709.png)
## Exercise 4: Access Azure Blob Storage data
* Cargar un blob de almacenamiento de muestra y lo pongo público.
![Lab0710](ZZ-lab/Lab0710.png)
URL blob:
 ```
https://securestorgeoconda.blob.core.windows.net/drop/records.json
 ```
* Test. 
![Lab0711](ZZ-lab/Lab0711.png)
* Cambio el access level a privado y este será el resultado.
![Lab0712](ZZ-lab/Lab0712.png)
* Pull and configure the Azure SDK for .NET
![Lab0713](ZZ-lab/Lab0713.png)
* Vuelvo a escribir código de Azure Blob Storage con el SDK de Azure para .NET
 ```
 using Azure.Storage.Blobs;
 using Microsoft.AspNetCore.Mvc;
 using Microsoft.Azure.WebJobs;
 using Microsoft.AspNetCore.Http;
 using System;
 using System.Threading.Tasks;

public static class FileParser
{
    
    [FunctionName("FileParser")]
    public static async Task<IActionResult> Run(
        [HttpTrigger("GET")] HttpRequest request)
        {
            string connectionString = Environment.GetEnvironmentVariable("StorageConnectionString");
            BlobClient blob = new BlobClient(connectionString, "drop", "records.json");
            var response = await blob.DownloadAsync();
            return new FileStreamResult(response?.Value?.Content, response?.Value?.ContentType);
        }
 }
 ```
 * Deploy and validate the Azure Functions app
![Lab0714](ZZ-lab/Lab0714.png)
* Observo los resultados de mi test run.
![Lab0715](ZZ-lab/Lab0715.png)







