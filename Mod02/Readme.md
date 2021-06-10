# Lab 02: Implement task processing logic by using Azure Functions

## Architecture:
![architecture_01](ZZ-lab/architecture_02.png)


### Crear una Store Account dentro de un Resource Group llamado Serverless. 
![Lab0200](ZZ-lab/Lab0200.png)

### Crear una Function App. 
![Lab0201](ZZ-lab/Lab0201.png)
### Connection String Key 1:

```
DefaultEndpointsProtocol=https;AccountName=funcstorgeoconda;AccountKey=2Y+fcKbyCujCLFrR4hjgXIk9pQbEmS0yEiaMdOYNxxaiFNwxamJfvKPgDI55yne/JbJson00nar1PrqoEvG3aA==;EndpointSuffix=core.windows.net
```


### Configure local Azure Functions project.
![Lab0203](ZZ-lab/Lab0203.png)


```
{
    "IsEncrypted": false,
    "Values": {
        "AzureWebJobsStorage": "DefaultEndpointsProtocol=https;AccountName=funcstorgeoconda;AccountKey=2Y+fcKbyCujCLFrR4hjgXIk9pQbEmS0yEiaMdOYNxxaiFNwxamJfvKPgDI55yne/JbJson00nar1PrqoEvG3aA==;EndpointSuffix=core.windows.net",
        "FUNCTIONS_WORKER_RUNTIME": "dotnet"
    }
}
```

### Crear una HTTP-triggered function
![Lab0204](ZZ-lab/Lab0204.png)
### Escribir un HTTP-triggered function code
![Lab0205](ZZ-lab/Lab0205.png)

### Test the HTTP-triggered function by using httprepl
![Lab0206](ZZ-lab/Lab0206.png)
![Lab0207](ZZ-lab/Lab0207.png)
### Create a function that triggers on a schedule
![Lab0208](ZZ-lab/Lab0208.png)

*Codigo usado para la task 4: Update the function integration configuration*
```
using System;
using Microsoft.Azure.WebJobs;
using Microsoft.Azure.WebJobs.Host;
using Microsoft.Extensions.Logging;

namespace func
{
    public static class Recurring
    {
         [FunctionName("Recurring")]
         public static void Run([TimerTrigger("*/30 * * * * *")]TimerInfo myTimer, ILogger log)
        {
            log.LogInformation($"C# Timer trigger function executed at: {DateTime.Now}");
        }
    }
}
```

![Lab0209](ZZ-lab/Lab0209.png)

### Crear una función que se integre con otros servicios.

*Subir un archivo en un contenedor nuevo llamado content, dentro de mi funcstorgeoconda*
![Lab0210](ZZ-lab/Lab0210.png)
*Crear una HTTP-triggered function.
![Lab0211](ZZ-lab/Lab0211.png)
