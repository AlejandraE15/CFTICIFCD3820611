# Lab 06: Authenticating to and querying Microsoft Graph by using MSAL and .NET SDKs
![architecture_09](ZZ-lab/Architecture_07.png)

## Exercise 1: Create an Azure Active Directory (Azure AD) application registration
* Creo un grupo de recurso en el cual tenga, una cuenta de almacenamiento, una Key Vault y una function app, dentro de la cual tendré una Application Insights.
![Lab0701](ZZ-lab/Lab0701.png)


## Exercise 2: Configure secrets and identities

* Observo en mi web app, que el Event Grid ya se visualiza. 
![Lab0702](ZZ-lab/Lab0702.png)

* Creo una nueva suscripción, la cual saldrá en mi "Topic Endpoint"
![Lab0703](ZZ-lab/Lab0703.png)

* Observo el evento de validación de mi suscripción.
![Lab0704](ZZ-lab/Lab0704.png)

### Exercise 3: Publish Event Grid events from .NET
* Creo un .NET project
![Lab0705](ZZ-lab/Lab0705.png)


 
* Dentro de mi .NET project, modifico el código de mi  Program.cs

 
 * Estos son los valores que he agregado a mi código.
 ```
Topic Endpoint:
https://hrtopicgeoconda.eastus-1.eventgrid.azure.net/api/events

Access Key 1 :
KgHrASIfUpVvRMDcqzXYNW4/MZY8JpLMhpyxBswUZeM=
```
![Lab0706](ZZ-lab/Lab0706.png)
* Finalmente observo como aparecen mis nuevas publicaciones.
![Lab0707](ZZ-lab/Lab0707.png)
