
# EXEMPLO DE APLICAÇÃO COM ASP CORE E REACT:

##TECNOLOGIAS UTILIZADAS/DEMONSTRADAS:
Abordagem DDD
API REST
ASP Net Core com Entity Framework
React com Axios
Node JS
Yarn
Typescript (TSX)
JavaScript com Ajax (JSX)
Estilização CSS
Estilização com SASS
Componentização
Visual Studio 2019
Visual Studio Code

**INSTRUÇÕES:**

1) Este projeto utiliza banco de dados local (LocalDB) na pasta /prj_teste/LocalDB por favor atulizar o endereço do banco, ou ainda para setar outra base de dados, atualizar o endereço do DB no campo "DevConection", na propriedade 'AttachDbFilename' no arquivo appsettings.json (/prj_teste/ASP_Core/RESTAPIDDD/RestDDD.API/appsettings.json)

 --> Para nova base de dados, executar as migrations (no project: Infraestructure\RestDDD.Infraestructure), para evitar erros, remova a propriedade 'AttachDbFilename', do campo "DevConection" no arquivo appsettings.json (/prj_teste/ASP_Core/RESTAPIDDD/RestDDD.API/appsettings.json)

COMANDOS PARA EXECUÇÃO DAS MIGRATIONS:
com o console do gerenciador de pacotes:
>update-database

com outros consoles (git-bash, Power Shell, Shell, CMD entre outros):
>dotnet ef database update

2) Caso a API seja executada em porta diferente, deve-se, alterar o arquivo api.ts (\prj_teste\frontend\src\services\api.ts) com o endereço correto

##FRONTEND:
**INFORMAÇÕES:**
* Criação de Páginas:
Deve-se criar um diretório em /src/pages/ refente ao elemento a ser trabalhando na página, e dentro deste diretório as referidas páginas, exemplo, o diretório User contém as páginas CreateUser.tsx e Login.tsx.<br/><br/>

* Estilização:
A estilização com CSS deve ser inserida no diretório /src/styles/components/ para componentes ou /src/styles/pages para páginas, ou para o caso de se utilizar SCSS, a estilização é feita no diretório do próprio componente exemplo /src/componentes/input. *OBS: usei CSS e SCSS no desenvolvimento do exemplo para utilizar ambas as abordagem, na palicação real, usaria o que já foi definido*.<br/><br/>

* Interfaces:
Iserir as interfaces no diretório src/interfaces (poderá ser criado diretórios internos para melhorar a ornganização).<br/><br/>

* src/logs:
Diretório para armezar logs da aplicação (a ser implementado).<br/><br/>

##BACKEND:
**INFORMAÇÕES:**

* API desenvolvido com a arquitetura DDD, onde:
***DOMAIN***
=> Domain \ project.Domain \ Entities : (class) entidade
=> Domain \ project.Domain.Core \ Interfaces \ Repositories : (Interface) IRepository
=> Domain \ project.Domain.Core \ Interfaces \ Services : (Interface) IService
=> Domain \ project.Domain.Services : (class) Service

***INFRAESTRUCTURE***
=> Infraestructure \ project.Infraestructure \ Data \ SqlContext -> Deve-se Adicionar o Contexto do OBJ
=> Infraestructure \ project.Infraestructure \ Data \ Repositories : (Class) Repository 
=> Infraestructure \ project.Infraestructure \ CrossCutting \ IOC \ ConfigurationIOC -> Deve-se registrar os Builders

***APLICATION***
=> Application \ projetc.Application \ DTOS : (class) DTO 
=> Application \ projetc.Application \ Interfaces \ Mappers : (Interface) IMapper
=> Application \ projetc.Application \ Interfaces : (Interface) IApplicationService
=> Application \ projetc.Application \ Mappers : (class) Mapper
=> Application \ projetc.Application : (class) ApplicationService

##BANCO DE DADOS:
**INFORMAÇÕES:**

* Para a construção desta aplicação foi utilizado o ORM do Entity Code First, com seu Scafold e migrations.<br/><br/>

* A tabela do Usuário é a do EF.<br/><br/>

* A tabela Contatos possui o seguintes atributos:
Id int Identity AutoIncrement primary key not null,
Nome nvarchar(50) not null,
Nascimento DateTime not null,
Email varchar(80) nullable,
DataCadastro DateTime not null,
DataAlteracao DateTime not null,
IsActive bit" not null