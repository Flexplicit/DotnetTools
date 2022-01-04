## **`.NET CLI TOOLS`**

**Updating Dotnet EF Commands**
 - Installs and updates dotnet ef tools
~~~
- dotnet tool install --global dotnet-ef
- dotnet tool update --global dotnet-ef
 ~~~
 
  - Migrates and updates db
 ~~~
- dotnet ef migrations add InitialMigration --project DAL --startup-project ConsoleApp
- dotnet ef database update --project DAL --startup-project ConsoleApp
- dotnet ef migrations remove (Removes last migration if it isn't in the db already)
- dotnet ef migrations script
~~~  

- Updates aspnet CRUD codegenerator
~~~
- dotnet tool install --global dotnet aspnet-codegenerator
- dotnet tool update --global dotnet aspnet-codegenerator
~~~
  
 - Scaffold the webpages: 
~~~
cd WebApp
- dotnet aspnet-codegenerator razorpage -m Game -dc ApplicationDbContext -udl -outDir Pages/Games --referenceScriptLibraries -f 
- dotnet aspnet-codegenerator razorpage -m GameState -dc ApplicationDbContext -udl -outDir Pages/GameStates --referenceScriptLibraries -f 
~~~

 - Scaffolds DB and generates models according to it. 
~~~
dotnet ef dbcontext scaffold "Data Source=(localdb)\MSSQLLocalDB;Initial Catalog=ContactDb” Microsoft.EntityFrameworkCore.SqlServer --table Persons --table Contacts --table ContactTypes --data-annotations --context AppDbContext --context-dir Data --output-dir Models
~~~
 - Scaffold Identity : 
~~~
cd WebApp
dotnet aspnet-codegenerator identity -dc DAL.App.EF.AppDbContext -f
~~~
 - More tools: 
~~~
- dotnet tool list -g
~~~







