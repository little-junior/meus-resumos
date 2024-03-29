# Domain-Driven Design (DDD)


- Abordagem de desenvolvimento de software que enfatiza o entendimento do domínio de negócio em cima da modelagem.
- Foca na melhoria da qualidade do software a partir da aproximação com a necessidade do negócio e seu contexto, refletindo o domínio de negócio.
- Prioriza o uso de uma linguagem universal, que compartilha as ideias do mundo do desenvolvimento de software e dos negócios.


## Conceitos do DDD

### Core Domain

- É a área central de um negócio, que comanda as operações e garante o sucesso do negócio.
- O DDD defende seu reconhecimento, já que possibilita uma ideia compreensiva a respeito dos aspectos fundamentais do negócio, alinhando com a ideia de criar um sistema que se encaixe perfeitamente nos requisitos e objetivos do negócio.

### Model-Driven Design

- Atua como uma representação do domínio de negócio, e contém os elementos, entidades e relações essenciais do contexto.
- Ao basear o desenvolvimento do software ao modelo de dominio, juntamente com a colaboração dos conhecedores do negócio, resulta em um software que realmente reflete ao negócio.

### Ubiquitous Language

- Possibilita a integração entre desenvolvedores, conhecedores do negócio e usuários.
- Indo da etapa de discussões até a implementação, garante uma comunicação clara entre as partes e entendimento do domínio do negócio, além de reduzir a probabilidade de mal entendidos.

## Componentes fundamentais do DDD

### Bounded Contexts

- Define limites lógicos dentro do sistema, no qual um modelo de negócio específico se aplica. 
- Cada contexto possui sua linguagem universal, sendo totalmente isolado e independente das outras partes do sistema.

### Entities

- Objetos com identidades únicas, que não mudam independente de mudanças e estados.
- São definidos pelas suas identidades distintas.
- Exemplo: um cliente sempre será um cliente e uma entity independente da mudança de seus atributos.

### Value Objects

- Objetos imutáveis que, ao contrário dos entities, são caracterizados pelos seus atributos.
- Pode ser substituido por outra instancia desde que tenha os mesmo atributos.
- Exemplos: endereços, datas, valores monetários.

### Aggregates

- Conjunto que agrupa entities e value objects, tratando-os como uma unidade única.
- Possui um aggregate root, que é o intermediário entre as interações e o aggregate.
- Mantem a integridade e consistencia de objetos relacionados.


### Domain Events

- Captura eventos importantes, que possuem grande significancia no sistema, e representam algo que ocorreu no domínio no passado.
- Possibilita que o sistema reaja e responda aos eventos adequadamente, mantendo a integridade do software.


## Implementação do DDD e seus padrões internos no .NET

- Implementar as regras técnicas do DDD pode ser um obstáculo, mas deve focar em:
	- Organizar o código para ficar alinhado com os problemas do negócio.
	- Usar os mesmos termos do negócio (ubiquitous language)

- **Atenção**: Recomenda-se usar a abordagem DDD apenas em microserviços complexos, com regras de negócio profundas.


### Camadas (layers) de uma aplicação com abordagem DDD

- As camadas de uma aplicação que aborda o DDD normalmente se concentra em três:
	- Application Layer
	- Domain model Layer
	- Infrastructure Layer

- Cada uma das camadas é um projeto, fazendo com que a comunicação entre elas fique claro.

![ddd layers](../media/dddlayers.png)
https://learn.microsoft.com/en-us/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/ddd-oriented-microservice
#### Domain Model Layer

- É o coração da aplicação, sendo responsável por representar os conceitos do negócio, como suas informações e regras.
- É onde o negócio é expressado, sendo uma Class Library com as domain entities POCOs, e sem qualquer dependência com as demais camadas ou frameworks.

#### Application Layer

- Define o que a aplicação deve fazer e direciona os objetos do domínio para trabalhar nos problemas.
- Responsável pelos trabalhos do sistema, mas também pela interação com a camada de application de outros sistemas.
- Não contém regras ou conhecimento do sistema.
- Normalmente implementado como um projeto ASP.NET Core Web API, que aborda a interação do microserviço, seu acesso remoto, e conexões com APIs externas.
- É a camada onde são implementadas os casos de usos dependentes da parte front-end do sistema.


#### Infrastructure Layer

- Camada da persistência de dados, que faz a relação com o banco de dados ou qualquer outro armazenamento.
- Não deve influenciar a camada de domain model, mas sim depender dela.


![ddd layers dependencies](../media/dddlayersdependencies.png)
https://learn.microsoft.com/en-us/dotnet/architecture/microservices/microservice-ddd-cqrs-patterns/ddd-oriented-microservice




