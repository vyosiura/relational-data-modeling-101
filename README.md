# Relational Data Modeling 101

Este é um repositório utilizado para demonstrar técnicas de modelagem de dados relacionais de forma simples e intuitiva. 

## Modelo relacional

O modelo relacional é o conceito utilizado por populares banco de dados como Oracle, SQL Server, MySQL e Postgres. Ele se baseia em **Entidades** e **Relacionamentos** onde as Entidades geralmente são uma definição que fazem analogia à algo representando o mundo real com conjuto de atributos para sua definição. E os Relacionamentos representam como as Entidades interagem entre si. 

> **😀 Vinicês:** Tentando ser o mais claro possível, as Entidades representam "coisas" e os relacionamentos são como as entidades se relacionam entre si.

> 🚦 Para mais detalhes de como foi concebido o modelo relacional procure sobre Edgar F. Codd que foi o criador do modelo relacional que serviu de base para os bancos de dados relacionais. 

### Implementação Física

O modelo relacional é utilizado para que possamos criar nossas estruturas de banco de dados de forma eficiente e escalável, **a performance e escalabilidade do banco de dados geralmente é extremamente dependente da sua modelagem**. 
Na sua implementação, podemos identificar as Entidades como **tabelas** e seus relacionamentos são implementados através de **chaves primárias e estrangeiras** que indicam a relação entre as tabelas. **_Schemas_** podem representar módulos dentro de um cenário que um banco de dados representa.

## Normalização

A normalização é utilizada para desenhar modelos de dados relacionais de forma consistente e eficiente afim de evitar dados duplicados e reduzir a complexidade do modelo de dados.

Dentro da normalização existe o que chamamos de `Formas Normais` que são regras para facilitar o processo de normalização. Neste conteúdo iremos cobrir a Primeira, Segunda, Terceira Forma Normal.

## Elementos da normalizaçãos

Para que possamos ter uma noção do que faremos a seguir, comentarei brevemente os componentes do modelo entidade relacionamento para que o entedimento seja mais fluído.

### Entidade

Representam os objetos principais sobre os quais você deseja armazenar informações. No exemplo de uma biblioteca, as entidades podem ser "Livros", "Autores" e "Empréstimos".

### Atributos

São as características que descrevem cada entidade. Por exemplo, os atributos da entidade "Livros" podem ser "Título", "Autor", "ISBN" e "Gênero"

### Tuplas / Registros

Representam uma instância da entidade, entidade são modelos para que as tuplas sejam criadas e manipuladas em um banco de dados. 

### Relacionamentos

Conectam as entidades entre si. Eles indicam como diferentes entidades estão relacionadas umas às outras. Por exemplo, o relacionamento entre "Livros" e "Autores" pode ser "escrito por", indicando que um livro é escrito por um autor. 

#### Tipo de relacionamento - Um para um (1:1)

Uma entidade está relacionada a no máximo uma instância de outra entidade. Por exemplo, um "Autor" só pode escrever um número máximo de "Livros".

#### Tipo de relacionamento - Um para muitos (1:N) 

Uma entidade está relacionada a zero ou mais instâncias de outra entidade. Por exemplo, um "Livro" pode ser escrito por um único "Autor" ou por vários co-autores.

#### Tipo de relacionamento - Muitos para muitos (N:N)

Uma entidade está relacionada a zero ou mais instâncias de outra entidade, e vice-versa. Por exemplo, um "Livro" pode ser emprestado a zero ou mais "Leitores", e um "Leitor" pode emprestar zero ou mais "Livros".

### Chave Primária

Chave primárias são atributos que são utilizados para identificar unicamente uma entidade. Geralmente uma entidade terá uma atributo que representa a chave primária. Porém, a chave primária pode ser composta por mais de um atributo.


### Chave Candidata

Chaves candidatas são chaves que por natureza são atributos únicos, que são **candidatos** à chave primária. Eles também conseguem identificar a entidade de forma única, mas acabam não sendo chaves primárias pois são dados de origem externa e que não temos controle, ocasionando um ponto de atenção em caso que o ambiente em que esse dado rege seja alterado. 

### Chave Estrangeira

A chave estrangeria representa a chave primária de uma entidade em uma outra entidade distinta. A chave estrangeira representa o relacionamento entre as entidades e a forma que se relacionam. Como vimos brevemente, o tipo de relacionamento que ditará qual entidade receberá a chave estrangeria de outra entidade. 
Ex.: Um funcionário pode ter vários beneficiários em seu plano de saúde. Nesse exemplo, espelharemos a chave primária do funcionário para a entidade de beneficiários afim de identificar e atrelar uma relação entre um funcionário e seus respectivos beneficiários.


## Isso é só começo

Apesar de parecer muita coisa, iremos abordar pouco a pouco todos os conceitos para ficar confortável e conseguirmos aplicar normalização no dia a dia. Podemos pular para o [nosso estudo de caso](./planejamento.md)
