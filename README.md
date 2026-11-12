# Inventario API - Examen VB.NET

API RESTful desarrollada en VB.NET (ASP.NET Core) bajo Clean Architecture, con Entity Framework Core, SQL Server y documentación en Swagger.

## 🚀 Cómo ejecutar el proyecto
1. Abre el proyecto en **Visual Studio 2022**.
2. Verifica la cadena de conexión en `appsettings.json`.
3. Abre la **Consola del Administrador de paquetes NuGet** y ejecuta:
   - `Add-Migration Inicial`
   - `Update-Database`
4. Presiona **F5** para ejecutar. El navegador abrirá automáticamente en:
   `https://localhost:<puerto>/swagger`

## 🛡️ Reglas de Negocio Implementadas
* **Control de duplicados:** No permite registrar categorías o productos con nombres repetidos (`HTTP 409`).
* **Integridad relacional:** Valida que la categoría exista antes de registrar un producto (`HTTP 409`).
* **Restricción de eliminación:** Bloquea la eliminación de categorías si tienen productos asociados (`HTTP 409`).
* **Validaciones de datos:** El precio debe ser mayor a 0 y el stock no puede ser negativo.
