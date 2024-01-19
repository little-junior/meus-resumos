# SOLID - Resumo

## Definição

- Acrônimo que reúne 5 dos principais design principles da programação orientada a objetos.
- Comprime boas práticas para garantir códigos mais legíveis, manuteníveis e que não ferem padrões de desenvolvimento de software.
<br/>
<br/>
<br/>



[S - Single Responsibility Principle (SRP)](#srp) <br>
[O - Open-Closed Principle (ORP)](#orp) <br>
[L - Liskov Substitution Principle (LSP)](#lsp) <br>
[I - Interface Segregation Principle (ISP)](#isp) <br>
[D - Dependency Inversion Principle (DIP)](#dip)

<br/>
<br/>

### S - Single Responsibility Principle (SRP) <a name="srp"></a>

***Uma classe só deve ter uma razão para mudar***

- Apenas um propósito e nada mais.
	- Só deve ter uma responsabilidade, evitando criar classes que fazem de tudo, e no fim fazem tudo ruim.
	- Não significa que deve haver só um método ou propriedade, mas que tudo que contenha seja relacionado a uma responsabilidade.
- Não se aplica somente a classes, mas também a métodos, funções e tudo aquilo que tem a tarefa de realizar algo.

#### Como aplicar o SRP

- Buscar dividir as múltiplas responsabilidades de um bloco em outros blocos, impedindo que façam mais de uma coisa dentro do contexto apresentado.

#### Benefícios do SRP

1. Aumento da coesão
	- A classe terá sua responsabilidade e apenas ela, sem necessidade de quebrar a cabeça para saber o que ela faz.

2. Baixo acoplamento
	- Com apenas uma responsabilidade, serão poucas as dependências, melhorando a qualidade do código.

3. Reuso do código
	- Quando for necessário reutilizar a classe, será mais fácil manuseá-la.

4. Fácil manutenção do código posteriormente

<br/>

### O - Open-Closed Principle (OCP) <a name="orp"></a>

***Objetos e entidades devem estar abertos para extensão, mas não para modificação***

- Quando surgirem novas funcionalidades e requisitos para uma entidade, ela deve ser estendida por uma interface, uma classe abstrata ou qualquer implementação que possibilite sua extensão sem causar bugs ou quebrar o código.
- A partir do momento que são feitos os testes unitários, a classe está fechada e seu código original só deve ser aberto quando forem achados erros e problemas (só uma razão para mudar).

#### Como aplicar o OCP

- Ao invés de utilizar implementações, utilizar abstrações (interfaces na maioria dos casos).
	- Dessa forma, pensando no futuro, qualquer adição será feita como extensão, sem alterar a classe original.
	- ***Separe o comportamento extensível por trás de uma interface e inverta as dependências.***

#### Benefícios do OCP

1. Facilidade na adição de novos requisitos
2. Diminuilção da chance de quebra de código e aparição de bugs
3. Isolamento da classe, tornando-a independente

<br/>

### L - Liskov Substitution Principle (LSP) <a name="lsp"></a>

***Uma classe base deve ser substituível por qualquer uma de suas classes derivadas sem modificar o comportamento***

- O código deve funcionar da forma esperada, sendo a classe derivada ou a base, sem se preocupar com resultados inesperados.


#### Como aplicar o LSP

- Utilizar do polimorfismo da maneira correta 
- Aplicar outros princípios, como injeção de dependência, OCP e ISP
- Evitar em uma classe derivada:
	- Sobrescrever/implementar um método que não faz nada
	- Lançar uma exceção inesperada
	- Retornar valores de tipos diferentes da classe base

#### Benefícios do LSP

1. Utilização do polimorfismo e herança da maneira correta
2. Não aparição de resultados inesperados
3. Abstração das entidades

<br/>

### I - Interface Segregation Principle (ISP)<a name="isp"></a>

***Uma entidade não deve ser forçada a implementar interfaces e métodos das quais não faz uso

- Ao invés de criar interfaces genéricas, é ideal criar interfaces específicas que cumprem seu papel (SRP) e não ferem as implementações (IRP).
- Se uma classe possui um método implementado que não está sendo usado, é necessário quebrar a interface em "sub interfaces".
	- Interfaces muito grandes nunca são ideais.

#### Como aplicar o ISP

- Quebrar interfaces generais em múltiplas interfaces específicas.
- Entender o propósito e responsabilidade de cada entidade para não implementar atores desnecessários.

#### Benefícios do ISP

1. Boa abstração no código
2. Aplicação de responsabilidades certas
3. Distribuição de abstrações

<br/>

### D - Dependency Inversion Principle (DIP)<a name="dip"></a>

***1. Módulos de alto nível não devem depender de módulos de baixo nível. Ambos devem depender da abstração.*** <br/>
***2. Abstrações não devem depender de detalhes. Detalhes devem depender de abstrações.***

- Uma classe deve depender de abstrações, não de implementações.
	- Implementações apenas acoplam o código, o que pode levar a erros e problemas futuros.
	- Uma classe de alto nível não deve saber como funciona a de baixo nível, apenas deve utilizar sua abstração.
- Não é a mesma coisa que injeção de dependência, mas trabalham juntas para atingir o objetivo do desacoplamento.
- É necessário pensar no futuro do código e sua expansão.
	- O que fazer para deixar as funcionalidades flexíveis e fáceis de se manter, ao mesmo tempo fechadas e com apenas uma responsabilidade?


#### Como aplicar o DIP

- Utilizar da injeção de dependência para diminuir o acoplamento
- Criar dependências de abstrações, não implementações.


#### Benefícios do DIP

- Módulos desacoplados
- Código com boa manutenção e abstração
- Expansão segura e com menor probabilidade de problemas
