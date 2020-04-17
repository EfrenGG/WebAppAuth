# Aplicación con ASP.NET Core con Identity
Esta aplicación únicamente contiene el código utilizado por Identity para poder asegurar una aplicación web.

Para ejecutar la aplicación es posible utilizar Visual Studio 2019 o .NET Core CLI, a continuación se muestran los pasos para ambas opciones.

### Visual Studio 2019

1. Descargar la última versión de Visual Studio Community 2019 desde este [link](https://visualstudio.microsoft.com/es/thank-you-downloading-visual-studio/?sku=Community&rel=16).
2. Abrir el archivo WebAppAuth.csproj con Visual Studio. Esta acción carga el proyecto e instala las dependencias.
3. Abrir el archivo _appsettings.json_ y modificar la línea `<connection-string>` por el string de conexión de la BD de SQL Server local:
  ```json
  "ConnectionStrings": {
    "WebAppAuthIdentityDbContextConnection": "<connection-string>"
  }
```
4. Ejecutar el comando `Update-Database` desde la consola de PowerShell como se muestra [aqui](https://docs.microsoft.com/en-us/ef/core/managing-schemas/migrations/?tabs=vs#update-the-database). Al ejecutar este comando, se generan las tablas de Identity en la BD especificada.
5. Iniciar la aplicación con el botón de IIS Express.

### .NET Core CLI

1. Descarga la versión 3.1 del SDK de .NET Core a través de este [enlace](https://dotnet.microsoft.com/download/dotnet-core/thank-you/sdk-3.1.201-windows-x64-installer) e instalarlo.
2. Abrir una línea de comando y posicionarse donde se descargó este directorio.
3. Instalar las herramientas de Entity Framework Core ejecutado el comando `dotnet tool install --global dotnet-ef`.
4. Ejecutar el comando `dotnet restore` para instalar las dependencias del proyecto.
5. Abrir el archivo _appsettings.json_ y modificar la línea `<connection-string>` por el string de conexión de la BD de SQL Server local:
  ```json
  "ConnectionStrings": {
    "WebAppAuthIdentityDbContextConnection": "<connection-string>"
  }
```
6. Ejecutar el comando `dotnet ef database update` para crear las tablas de Identity en la BD especificada.
7. Ejecutar el comando `dotnet run` para ejecutar la aplicación y abrirla en el browser configurado por defecto.
