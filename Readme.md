# DevFreela


Aula : 

## Structures

> *Controllers* : 

> *Actions* : 

> *Models* : 

> *Repository* : 

> *Controllers* : 













```powershell
# Criar Solution
$ dotnet new sln --name DevFreela

# Cria o Projeto DevFreela.API do tipo webapi e cria a pasta DevFreela.API
$ dotnet new webapi --name DevFreela.API --output DevFreela.API

# Adicionar a referencia do projeto na solution
$ dotnet sln add ./DevFreela.API/DevFreela.API.csproj

# Build no projeto
$ dotnet build

# Executar a aplicação
$ dotnet run

# Criar arquivo .gitignore para projetos .net
$ dotnet new gitignore
```