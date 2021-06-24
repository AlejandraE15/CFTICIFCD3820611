# Lab 06: Authenticating to and querying Microsoft Graph by using MSAL and .NET SDKs
![architecture_09](ZZ-lab/Architecture_06.png)

## Exercise 1: Create an Azure Active Directory (Azure AD) application registration
* Creo un registro de aplicación
* ![Lab0600](ZZ-lab/Lab0600.png)

* Estos son los valores que necesitaré para mi código.
Application (client) ID :
```
aae6149f-b87b-46d7-a65a-5487d0030313
```
Directory (tenant) ID :
```
46432455-ac40-4b4d-9765-c95cbca056bd
```
* Habilito el  de cliente predeterminado.
![Lab0601](ZZ-lab/Lab0601.png)


## Exercise 2: Obtain a token by using the MSAL.NET library
* Creo un .NET project con los siguientes comandos.
![Lab0602](ZZ-lab/Lab0602.png)
![Lab0603](ZZ-lab/Lab0603.png)

* Dentro de mi proyecto creado, modifico el código de mi Program.cs (En esta actividad utilizaré los valores guardados.)
![Lab0604](ZZ-lab/Lab0604.png)

* Lo ejecuto.
![Lab0605](ZZ-lab/Lab0605.png)

* Me redirige a mi navegador para queinicie sesión mi cuenta.
![Lab0606](ZZ-lab/Lab0606.png)

## Exercise 3: Query Microsoft Graph by using the .NET SDK
* Importo el SDK de Microsoft Graph desde NuGet
![Lab0607](ZZ-lab/Lab0607.png)
![Lab0608](ZZ-lab/Lab0608.png)
 
 * Modifico el Program class para usar el SDK de Microsoft Graph para consultar información de perfil del usuario.
 ![Lab0609](ZZ-lab/Lab0609.png)
 
 * Pruebo la actualización de la aplicación.
![Lab0610](ZZ-lab/Lab0610.png)
