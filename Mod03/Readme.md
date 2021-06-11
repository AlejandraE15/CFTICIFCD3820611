# Lab 03: Retrieving Azure Storage resources and metadata by using the Azure Storage SDK for .NET

## Objectives

*Create containers and upload blobs by using the Azure portal.

*Enumerate blobs and containers by using the Microsoft Azure Storage SDK for .NET.

*Pull blob metadata by using the Storage SDK.

### Crear una Storage Account 
![Lab0300](ZZ-lab/Lab0300.png)

### Crear 2 contenedores en mi Storage Account
![Lab0301](ZZ-lab/Lab0301.png)
### Subir una imagen a uno de mis contenedores
![Lab0302](ZZ-lab/Lab0302.png)
### Crear un .Net project
![Lab0303](ZZ-lab/Lab0303.png)
## Modificar  Program.cs para acceder a mi Storage usando los siguientes codigos.


```
using Azure.Storage;
using Azure.Storage.Blobs;
using Azure.Storage.Blobs.Models;
using System;
using System.Threading.Tasks;

public class Program
{
    private const string blobServiceEndpoint = "https://mediastorgeoconda.blob.core.windows.net/";
    private const string storageAccountName = "mediastorgeoconda";
    private const string storageAccountKey = "H2JRz7NJVQbNR8+Xvdh3KUDKmJdgGPwsZm8jEKwMv1uPKjsdC1tzzffpuri2f6NnucgoH5QNPTC0Gsc42FZlpQ==";
        
    public static async Task Main(string[] args)
    {
        StorageSharedKeyCredential accountCredentials = new StorageSharedKeyCredential(storageAccountName, storageAccountKey);

        BlobServiceClient serviceClient = new BlobServiceClient(new Uri(blobServiceEndpoint), accountCredentials);

        AccountInfo info = await serviceClient.GetAccountInfoAsync();

        await Console.Out.WriteLineAsync($"Connected to Azure Storage Account");
        await Console.Out.WriteLineAsync($"Account name:\t{storageAccountName}");
        await Console.Out.WriteLineAsync($"Account kind:\t{info?.AccountKind}");
        await Console.Out.WriteLineAsync($"Account sku:\t{info?.SkuName}");

        await EnumerateContainersAsync(serviceClient);

        string existingContainerName = "raster-graphics";
        await EnumerateBlobsAsync(serviceClient, existingContainerName);

        string newContainerName = "vector-graphics";
        BlobContainerClient containerClient = await GetContainerAsync(serviceClient, newContainerName);

        string uploadedBlobName = "graph.svg";
        BlobClient blobClient = await GetBlobAsync(containerClient, uploadedBlobName);

        await Console.Out.WriteLineAsync($"Blob Url:\t{blobClient.Uri}");


    }

    private static async Task EnumerateContainersAsync(BlobServiceClient client)
        {  
           await foreach (BlobContainerItem container in client.GetBlobContainersAsync())
            {
                 await Console.Out.WriteLineAsync($"Container:\t{container.Name}");
            }       
      
        }
    private static async Task EnumerateBlobsAsync(BlobServiceClient client, string containerName)
        {      
            BlobContainerClient container = client.GetBlobContainerClient(containerName);

            await Console.Out.WriteLineAsync($"Searching:\t{container.Name}");
            await foreach (BlobItem blob in container.GetBlobsAsync())
            {
            await Console.Out.WriteLineAsync($"Existing Blob:\t{blob.Name}");
            }
        }
    private static async Task<BlobContainerClient> GetContainerAsync(BlobServiceClient client, string containerName)
        {
            BlobContainerClient container = client.GetBlobContainerClient(containerName);
            await container.CreateIfNotExistsAsync(PublicAccessType.Blob); 
            await Console.Out.WriteLineAsync($"New Container:\t{container.Name}");

            return container;
        }
    private static async Task<BlobClient> GetBlobAsync(BlobContainerClient client, string blobName)
        {
            BlobClient blob = client.GetBlobClient(blobName);
            await Console.Out.WriteLineAsync($"Blob Found:\t{blob.Name}");
            
            return blob;
        }

}
```


* Conectar con Azure Storage bob service endpoint
![Lab0304](ZZ-lab/Lab0304.png)


*Conectar con los contenedores existentes
![Lab0305](ZZ-lab/Lab0305.png)
### Retrieve blob Uniform Resource Identifiers (URIs) by using the .NET SDK

*Enumerar los blobs de un contenedor existente mediante el SDK
![Lab0306](ZZ-lab/Lab0306.png)

*Crear un nuevo contenedor usando SDK
![Lab00307](ZZ-lab/Lab0307.png)
## Subir un nuevo blob usando el portal de Azure.
![Lab00308](ZZ-lab/Lab0308.png)
### Access blob URI by using the SDK
![Lab0309](ZZ-lab/Lab0309.png)
## Test the URI by using a browser
![Lab0310](ZZ-lab/Lab0310.png)

*Blob URL:
```
https://mediastorgeoconda.blob.core.windows.net/vector-graphics/graph.svg
```
