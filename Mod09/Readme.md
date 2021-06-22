# Lab 09: Publishing and subscribing to Event Grid events
![architecture_09](ZZ-lab/Architecture_09.png)

### Exercise 1: Create and configure Azure resources

* Creo una Application Insights resource y  una App Service.
![Lab1100](ZZ-lab/Lab1100.png)
![Lab1101](ZZ-lab/Lab1101.png)

* Configuración de las opciones de escalado automático de mi Web app.
![Lab1102](ZZ-lab/Lab1102.png)

### Exercise 2: Monitor a local web application by using Application Insights
* Build a .NET Web API project
![Lab01103](ZZ-lab/Lab1103.png)

* Dentro de mi carpeta Startup.cs del proyecto que cree, le agrego este codigo a mi Startup class, asi como tambíen modifico el CopnfigureServices, agregandole otra linea de codigo.
```
private const string INSTRUMENTATION_KEY = "a5cdd414-c892-45d5-a0da-ac57c7dacf48";
```
```
 public void ConfigureServices(IServiceCollection services)
        {

            services.AddControllers();

            services.AddApplicationInsightsTelemetry(INSTRUMENTATION_KEY);
            
            services.AddSwaggerGen(c =>
            {
                c.SwaggerDoc("v1", new OpenApiInfo { Title = "SimpleApi", Version = "v1" });
            });
        }
```
* Hechas las modificaciones, uso el comando dotnet build y dotnet run-.

![Lab1104](ZZ-lab/Lab1104.png)

* Abro una nueva ventana y compruebo que funciona.
![Lab1105](ZZ-lab/Lab1105.png)

### Exercise 3: Monitor a web app using Application Insights
 
 * Implementación de una aplicación en la web app
![Lab1106](ZZ-lab/Lab1106.png)
![Lab1207](ZZ-lab/Lab1107.png)
![Lab1108](ZZ-lab/Lab1108.png)
![Lab119](ZZ-lab/Lab119.png)
* Compruebo que los datos se han subido a mi API service.
![Lab1109](ZZ-lab/Lab1109.png)
