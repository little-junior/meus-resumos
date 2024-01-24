# Aggregate

- Padrão utilizado no DDD definido como um conjunto de objetos do domínio que podem ser tratados como uma unidade única.
- Presente na camada Domain Model.
- Um dos componentes de um Aggregate será o Aggregate Root, que garante a integridade do Aggregate sendo o ponto de entrada e único meio que as referências externas possuem com ele.
- É o elemento básico de transferência de armazenamento de dados, inferindo a requisição (carregamento e salvamento) de um Aggregate como um todo, e não suas partes.
- Exemplo:
	- Um pedido terá itens, que serão objetos separados, mas no contexto do DDD, o pedido e seus itens serão tratados como um único aggregate. 


## Aggregate Root

- Ponto de entrada para acessar e modificar os componentes internos de um aggregate.
- Responsável por garantir a consistência e integridade do aggregate como um todo.
- É o único objeto de um aggregate que pode ser acessado diretamente por entidades externas.
	- Todos os componentes do aggregate que não são o root devem ser readonly e não podem possuir métodos que mudem seus estados. Tudo isso deve estar no root.
- Todas as modificações e operações dentro de um aggregate são tratadas como uma unidade única de trabalho, que são persistidas ou descartadas juntas.

![[aggregateexample.png]]
https://medium.com/@edin.sahbaz/exploring-the-power-of-aggregates-in-domain-driven-design-and-clean-architecture-6408d6128d3b

## Benefícios 

1. Entidades mais consistentes e com limites definidos nas regras de negócio.
2. Persistência garantida das unidades, que dão certo ou falham juntas.
3. Melhora a performance e escalabilidade do sistema, otimizando o acesso a dados e os conflitos de consistência.
4. Facilidade teste unitários ao encapsular a lógica do negócio em unidades concisas.