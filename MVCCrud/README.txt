Trabajo de Diseño de Sistemas de Internet

Integrantes:
	Elliott Noé Alvarez Parrales
	Jarov Bayardo Davila Larios

Notas de la clase practica:
 - Se uso la base de datos SQL Server Express 2019 LocalDB. 
	Esta edicion de SQL Server se puede descargar en Visual Studio Installer como componente individual.
 - El string de conexion se encuentra guardado en Secrets.json
	Es posible hacer esto sin usar Secrets.json, pero es recomendado hacerlo por esta via por temas de seguridad.)
 - Para la compilacion del modelo Notas (O en este caso "Notum" debido a la compilacion) se uso un comando desde la consola
	de desarrollador, en vez de la consola de administracion de paquetes Nuget. Esto pasa porque se guardó el string de 
	conexion en secret.json 
 - Despues de compilar el modelo y su contexto, se agrego la siguiente linea en Program.cs
	Es necesaria esta linea para que EntityFramework pueda encontrar la base de datos y compilar controladores y vistas.
	builder.Services.AddDbContext<NotasContext>(options => {
		options.UseSqlServer(builder.Configuration.GetConnectionString("ConnectionStrings:LocalDB")); });