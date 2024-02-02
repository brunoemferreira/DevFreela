# DevFreela

## Arquitetura Limpa
  * _**Arquitetura**_ : é a organização fundamental de um sistema , incluindo seus componentes , o relacionamento entre eles , o ambiente, e os principios em que se baseia sua construção. 
  
  * _**Arquitetura Limpa**_ : conhecida como _Onion Architecture_, ou Arquitetura Cebola, é uma arquitetura amplamente utilizada no mercado, tem como foco o _domínio_ do sistema, tendo em sua essência o _**DDD - Domain Driven Design**_. Ela possuio diversas variaçõies porém sempre tem a mesma estrutura base.
    * Sua estrutura é dividida em **4** camadas principais : 
      1. Camada Core (Também chamada de Domain )
         * **Entidades** : classes do dominio, que representam as entidaddes.
         * **Enums** : tipos de enumeração do C#, sendo definido um conjunto de constantes nomeadas (geralmente números inteiros).
         * **Data Access Objects(DTO)**: objetos de transporte dce dados, geralmente utilizados em retorno de serviços de infra-estrutura(integração  com outro sistema), consultas com projeção de dados diferenciadas(.ex. dapper ).  
         * **Serviços de camada de domínio** : quando uma operação do dominio envolve múltiplas classes ou estados, extrapolando responsabilidades, um serviço de cada domínio é indicado.
         * **Interfaces(de serviços de infra-estrutura, domínio, repositórios)** : utilizadas em diferentes camadas, como API, Aplicação e InfraEstrutura.
         * **Exceçoes de Domínio** : excecóes específicas a cenários de problema no fluxo de negócioElas são tratadas via filtro de ASP.NET Core, que tratará as exceções de maneira automática. Um exemplo seria o de _ProjectAlreadyStartedException_, que indicaria uma ação de início de projeto que já foi iniciado.
      2. Infrastructure
      3. Application
      4. API/Interface

### DDD - Domain-Driven Design

* Conceitos :
  * **Agregados** : padrão que representa um conjunto de objetos do dominio que podem ser tratados como um só.
  * **Repositórios** : abstrações que representam acesso a objetos de domínio.
  * **Linguagém Ubíqua** : modelo de linguagem universal para comunicação entre desenvolvedores e analisatas de negócios.    


## SOLID
### _**S - SRP Single Responsability Principle**_ 
### _**O - OCP Open-Closed Principle**_ 
### _**L - LSP Liskov Substituition Principle**_ 
### _**I - ISP Interface Segregation Principle**_ 
### _**D - DIP Dependency Inversion Principle**_ 
 
  1. Módulos de alto nível não devem depender de módulos de baixo nível. Ambos devem depender de abstrações.
  2. Abstrações não devem depender de detalhes. Detalhes devem depender de abstrações.
  
  Dependa de abstraçoes e não de implementações. 
 
 > _**Importante**_ : **Inversão de Dependência** não é igual a Injeção de Dependência, fique ciente disso! A **Inversão de Dependência é um princípio (Conceito)** e a **Injeção de Dependência é um padrão de projeto (Design Pattern)**.

___


## Structures

> *Controllers* : 

> *Actions* : 

> *Models* : 

> *Repository* : 

> *Controllers* : 

## Design Patterns

### _**Injeção de Dependência**_
  
 * Possui **3 ciclos de vida** :
   * _**Singleton**_ : Os serviços são criados uma vez durante a vida útil do aplicativo que usa a memsma instância para todo o aplicativo. São registrados usando o método _**AddSingleton**_.
   
   * _**Scoped**_ : Os serviços são criados em cada solicitação(uma vez por solicitação do cliente). É indicado para aplicações WEB. Se durante uma request você usar a mesma injeção de dependência em muitos lugares, você vai usar a mesma instância dos objetos, e ele fará referência a mesma alocação de memória. São registrados usando o método _**AddScopped**_. Nesse tempo de vida útil os serviços criados são descartados no final do request, ou seja depois do response.   
   
   * _**Transient**_ : Os serviços são criados cada vez que são solicitados. Cada vez que for injetado em uma classe , será criada uma nova instância do serviço. É indicado para serviços leves e sem estado. São registrados usando o método _**AddTransient**_.

_**Vantagens**_ : 
* Baixo acoplamento entre as classes 
* A responsabilidade de criar as classes agora passa ser do container de injeção de dependência.

___



## Comandos utilizados no curso
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

# Setar a variável de ambiente para desenvolvimentoß
$ set ASPNETCORE_ENVIRONMENT="Development"

```