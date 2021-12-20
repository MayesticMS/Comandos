# Comandos
## DOTNET
- Ver lista de posibles proyectos a crear
```
    dotnet new --list
```
- Crear tipos de proyectos o solucion, la -o significa output.
```
    dotnet new sln -o NombreSolucion
    dotnet new gitignore
    dotnet new webapi -o NombreProyecto
```
- Agregar proyectos a la solucion o eliminarlos.
```
    dotnet sln NombreSolucion.sln add NombreProyecto.csproj
    dotnet sln NombreSolucion.sln remove NombreProyecto.csproj
```
- Agregar referencias a proyectos o eliminarlas.
```
    dotnet add NombreProyecto.csproj reference NombreProyectoAgregar.csproj
    dotnet remove NombreProyecto.csproj reference NombreProyectoAgregar.csproj
```
- Agregar NuGet
```
    dotnet add package System.Data.SqlClient --version 4.8.3
    dotnet add package Dapper --version 2.0.90
    dotnet add package Moq --version 4.16.1
```
- Compilar, ejecutar estando en la carpeta del proyecto.
```
    dotnet build
    dotnet restore
    dotnet run NombreProyecto.csproj
    dotnet Proyecto.dll --urls "https://192.168.0.4:5000"
    dotnet test NombreProyecto.csproj
```
- Configuraciones de GIT
```
    git config --list
    git config --global user.name "User"
    git config --global user.email "Correo"
```
- Ver status, ver ramas, cambiar de ramas, crear rama y seleccionarla, ver cambios del servidor.
```
    git status
    git branch
    git checkout NombreRama
    git checkout -b NombreRama
    git fetch
```
- Linux abrir puertos.
```
    sudo ufw enable
    sudo ufw allow 1433/tcp
    sudo ufw enable
```
- Linux ver servicios.
```
    systemctl status mssql-server
    sudo systemctl stop mssql-server
    sudo systemctl reload mssql-server
    sudo systemctl disable mssql-server
    sudo systemctl enable mssql-server
    sudo systemctl start mssql-server
```
## Sonar Qube
Token: 474e6fcecba67f9902388c3d92767ab49fc71237
admin	barfuma94+
Instalar nuger msbuild.coverlet y desisntalar el default en el proyecto de pruebas

CMD iniciar sonarqube
"D:\Program Files\SonarQube\bin\windows-x86-64/StartSonar.bat"

Iniciar escaneo
dotnet sonarscanner begin /k:"Isonoe" /d:sonar.host.url="http://localhost:9000"  /d:sonar.login="474e6fcecba67f9902388c3d92767ab49fc71237" /d:sonar.cs.opencover.reportsPaths="coverage.opencover.xml"

Compilar proyecto
dotnet build

Ejecutar pruebas unitarias
dotnet test /p:CollectCoverage=true /p:CoverletOutputFormat=opencover /p:CoverletOutput=../

Detener escaneo
dotnet sonarscanner end /d:sonar.login="474e6fcecba67f9902388c3d92767ab49fc71237"
