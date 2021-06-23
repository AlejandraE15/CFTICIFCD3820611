# Lab 08: Creating a multi-tier solution by using services in Azure
![architecture_08](ZZ-lab/Architecture.png)

### Exercise 1: Creating an Azure App Service resource by using a Docker container image
* Creo un grupo de recurso junto con una Api Service y una API Management. 
![Lab0800](ZZ-lab/Lab0800.png)
* Test the httpbin web application
![Lab0801](ZZ-lab/Lab0801.png)


## Exercise 2: Build an API proxy tier by using Azure API Management
* Dentro de mi API Management creo una Blank API llamada httpbin-ap
![Lab0802](ZZ-lab/Lab0802.png)
Properties URL: 
```
http://httpapigeoconda.azurewebsites.net/
 ```
 * En mi Blank API creada, añadiré una operación una política.
![Lab0803](ZZ-lab/Lab0803.png)

* Seleciono Echo Headers y busco Backend, lo edito pàra agregar un nuevo valor.
![Lab0804](ZZ-lab/Lab0904.png)

* Estos son los resultados de mi API creada.
![Lab0805](ZZ-lab/Lab0805.png)

 * Asi mismo creo una mnueva operación llamada Get Legacy Data y veo sus resultados también.
![Lab0806](ZZ-lab/Lab0806.png)

*  En esta ultima operación creada  agrego una  nueva politica donde tendré que editar el código, quedando de esta manera:
![Lab0807](ZZ-lab/Lab0807.png)
* Compruebo que al cambiar el código se cree un formato .JSON
![Lab0808](ZZ-lab/Lab08080png)
* Por último, observo el contenido del Backend y del Outbound.
![Lab0809](ZZ-lab/Lab0810.png)
![Lab0809](ZZ-lab/Lab0811.png)

