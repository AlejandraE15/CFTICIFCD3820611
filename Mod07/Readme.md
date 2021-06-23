# Lab 07: Access resource secrets more securely across services
![architecture_09](ZZ-lab/Architecture_07.png)

## Exercise 1: Create Azure resources
* Creo un grupo de recurso en el cual tenga, una cuenta de almacenamiento, una Key Vault y una function app, dentro de la cual tendré una Application Insights.
![Lab0700](ZZ-lab/Lab0700.png)


### Exercise 2: Create an Event Grid subscription
![Lab0901](ZZ-lab/Lab0901.png)
* Observo en mi web app, que el Event Grid ya se visualiza. 
![Lab0902](ZZ-lab/Lab0902.png)

* Creo una nueva suscripción, la cual saldrá en mi "Topic Endpoint"
![Lab0903](ZZ-lab/Lab0903.png)

* Observo el evento de validación de mi suscripción.
![Lab0904](ZZ-lab/Lab0904.png)

### Exercise 3: Publish Event Grid events from .NET
* Creo un .NET project
![Lab0905](ZZ-lab/Lab0905.png)


 
* Dentro de mi .NET project, modifico el código de mi  Program.cs

 
 * Estos son los valores que he agregado a mi código.
 ```
Topic Endpoint:
https://hrtopicgeoconda.eastus-1.eventgrid.azure.net/api/events

Access Key 1 :
KgHrASIfUpVvRMDcqzXYNW4/MZY8JpLMhpyxBswUZeM=
```
![Lab0906](ZZ-lab/Lab0906.png)
* Finalmente observo como aparecen mis nuevas publicaciones.
![Lab0907](ZZ-lab/Lab0907.png)
