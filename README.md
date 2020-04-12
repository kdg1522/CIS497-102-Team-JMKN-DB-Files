# CIS497-102-Team-JMKN-DB-Files
Setup instructions (Windows) and additional files needed for database connection

### Downloads
* SQL Server Express: <https://go.microsoft.com/fwlink/?linkid=866658>
* Microsoft SQL Server Management Studio: <https://aka.ms/ssmsfullsetup>


In Visual Studio solution explorer, right click AppName -> Manage NuGet Packages and go to Browse tab.
* Install System.Data.SqlClient
* Install Microsoft.EntityFrameworkCore
* Install Microsoft.EntityFrameworkCore.Design
* Install Microsoft.EntityFrameworkCore.SqlServer
* Install Microsoft.EntityFrameworkCore.Tools


From this repository:
* Download InfoDatabase.bak
* Download appsettings.local.json


### Database Setup
Open Microsoft SQL Server Management Studio (SSMS) and Connect.
* Server Type: Database Engine
* Authentication: Windows Authentication


From the start menu, open Services. 
* Right-click SQL Server (SQLExpress), select Properties, and make sure Startup Type is set to Automatic
* Do the same for SQL Server Agent (SQLExpress) and SQL Server Browser


Move InfoDatabase.bak into Microsoft SSMS backup directory.
(For me, it was C: -> Program Files -> Microsoft SQL Server -> MSSQL15.SQLEXPRESS -> MSSQL -> Backup)


In SSMS, right-click on databases and select "Restore Database". 
Select InfoDatabase and hit OK.


Copy your server name in Object Explorer.
(For me it was LAPTOP-86KULK7K\SQLEXPRESS)


### Connecting to Database
* Open the project in Visual Studio and go to View -> Server Explorer
* Select Add Connection
* In the Change Data Source window, select Microsoft SQL Server as Data Source and .NET Framework Data Provider for SQL Server as Data Provider 
* Hit OK
* In the Add Connection window, paste the server name into the Server Name field
* Make sure Authentication is set to Windows Authentication
* Under "Select or enter a database name", choose InfoDatabase
* Hit OK


The server should appear under Data Connections in the Server Explorer now.
* Right-click the server and select Properties
* In the Properties window, find Connection String and copy it
* Open the appsettings.local.json file you downloaded and paste the string where it says "Your connection string here"
* Save and close the file
* In Visual Studio's Solution Explorer, drag appsettings.local.json onto the AppName folder


The program should run without errors now. Test it and let me know if you have any problems.