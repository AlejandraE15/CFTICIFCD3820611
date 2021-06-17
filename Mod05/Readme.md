# Lab: Implementación de procesos de cargas de trabajo mediante el uso de imágenes y contenedores
Arquitectura: 
![Architecture_05](ZZ-lab/Architecture_05.png)

# Exercise 1: Create a VM by using the Azure Command-Line Interface (CLI)
* Creamos un grupo de recursos.
![Lab05](ZZ-lab/Lab05.png)

* Usando los comandos de Azure CLI para crear una maquina virtual. 
![Lab0500](ZZ-lab/Lab0500.png)

## Exercise 2: Create a Docker container image and deploy it to Azure Container Registry

* Dentro de ~/clouddrive directory creamos un nuevo directorio llamado ipcheck, en el cual crearemos una nueva consola llamada ipcheck.
![Lab0501](ZZ-lab/Lab0501.png)

* Creo un nuevo archivo llamado  Dockerfile y abro el Visual Code de  Cloud Shell.
![Lab0502](ZZ-lab/Lab0502.png)

* Elijo  el archivo de Program.cs borro todo y le agrego nuevos códigos, lo guardo y finalizo con un dotnet run.
![Lab0503](ZZ-lab/Lab0503.png)

* En el archivo creado Dockerfile. le agregamos el siguiente código y guardo.
![Lab0504](ZZ-lab/Lab0504.png)

* Crear un Container Registry resource
![Lab0512](ZZ-lab/Lab0512.png)

* Abrir Azure Cloud Shell and store Container Registry metadata
![Lab0505](ZZ-lab/Lab0505.png)
![Lab0506](ZZ-lab/Lab0506.png)
![Lab0507](ZZ-lab/Lab0507.png)

* Validar mi contenedor de imagen en Container Registry
![Lab0508](ZZ-lab/Lab0508.png)

## Exercise 3: Deploy an Azure container instance

* Enable the admin user in Container Registry
![Lab0509](ZZ-lab/Lab0509.png)

* Creo un Container instance
![Lab0510](ZZ-lab/Lab0510.png)

* Dentro de la seccion "Containers" buscamos Events y luyego Logs, confirmamos que dentro esta nuestra IP Adresses.
![Lab0511](ZZ-lab/Lab0511.png)



