
# Dependency Injection

## O que é?

- A Injeção de Dependência no .NET é um design pattern que consiste na implementação do design principle Inversion of Control.
- No framework .NET, a injeção de dependência faz parte da estrutura interna da plataforma, sem necessidade bibliotecas externas.

## Objetivos

1. Reduzir acoplamento entre uma classe e suas dependências, tornando-a mais independente
2. Aumentar a coesão da classe, seguindo o Princípio da Responsabilidade Única (SRP)

## Aplicação 

- Resumidamente, a injeção de dependência é aplicada nos seguintes pontos:
    - Utilizar abstrações como interface (mais utilizado) e classe base ao invés da implementação da dependência e tipos concretos.
    - Criação da classe injetora, que vai criar a instância da dependência.
    - Injetar a dependência na classe dependente por meio do construtor, passando a abstração como parâmetro.

- Envolve três classes:
	- Classe injetora -> a que instancia e injeta.
	- Classe de serviço (ou de dependência) -> a que é instanciada pela injetora.
	- Classe de cliente (ou dependente)-> a que depende da de serviço.

### Tipos de aplicações

#### Injeção por Construtor

- A mais usada, composta pelo campo private readonly e a injeção pelo construtor.

#### Injeção por Método

- Nesse tipo de injeção, a injeção das instancias será via métodos do objeto, e não pelo construtor.
- As instâncias serão propriedades privadas/públicas da classe, e não um campo.

#### Injeção por Propriedade

- Aqui, são criadas propriedades publicas para as dependências, que são declaradas por via de seus setters.


## Pontos Importantes

- É possível utilizar a injeção de dependência de maneira encadeada. Cada dependência requisitará suas próprias dependências e o container/injetor vai resolvê-las, devolvendo o serviço completo (dependency tree).
- Em um tipo com mais de um construtor, o provedor de serviços escolherá aquele com o maior nível de ser injetado por dependência.


### Serviço

- Um objeto que fornece serviços para outro objeto.
- Não necessariamente precisa ser um serviço web.

### Tempo de vida de serviço 

Quando um serviço é registrado, ele pode possuir um dos seguintes tempos de vida:

#### Transient

- São criados toda vez que seus serviços são requisitados.
- Ideal para serviços leves e sem estado
- AddTransient

#### Scoped

- São criados a cada requisição do cliente
- É a mesma instância dentro do mesmo escopo
- Ao final da requisição, o serviço é encerrado
- AddScoped


#### Singleton

- São criados na primeira execução da aplicação e usados até o fim da aplicação.
- AddSingleton





