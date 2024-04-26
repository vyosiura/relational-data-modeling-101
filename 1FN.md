# 1ª Forma Normal

- 🥸`Como está nos livros:` Uma entidade estará na 1ª forma normal se e somente se todos os atributos contiverem apenas dados atômicos. Ou seja, atributos multivalorados devem ser movimentados para sua respectiva entidade, ou deve-se criar uma nova entidade.
- 🤓`Como eu entendo:` Um atributo não deve ter mais de um valor e valores que se repetem são grandes canidadatos a serem isolados em sua respectiva entidade. Identificar a chave primária da entidade uma vez que os atributos devem ser atômicos.
- 😍`Na prática:` Identificar colunas com valores que se repetem e ou colunas que tem o "potencial de receber vários valores". Além de dentificar atributos únicos e criar a chave primária para que cada tupla/registro seja única. 

Então, como mostrado anteriormente, dado o modelo abaixo sem aplicar a normalização:

| Nome       	| Documento 	| Data de Nascumento 	| Placa    	| Modelo                 	| Ano  	| Cidade              	| Renavam    	| Data de registro 	| Data Inicio Posse 	| Data Fim Posse	|
|------------	|-----------	|--------------------	|----------	|------------------------	|------	|---------------------	|------------	|------------------	|----------------------	|----------------------	|
| Jane Done  	| 83012310  	| 07/05/1966         	| iju-8172 	| Toyota - Corolla XLI   	| 2023 	| MG - Belo Horizonte 	| 4783912211 	| 23/04/2024      	|         27/04/2024             	|                      	|
| John Doe   	| 45768123  	| 10/01/1970         	| fpw-97f4 	| GM - Tracker 1.0 Turbo 	| 2021 	| SP - Guarulhos      	| 2378465920 	| 10/03/2022       	|  13/03/2022                     	|                      	|
| Foo Bar    	| 6472819   	| 10/09.1991         	| gec-4841 	| Nissan - Versa 1.6 GL  	| 2015 	| SP - Suzano         	| 1209384741 	| 10/03/2013       	| 10/03/2013           	|                 	|
| Foo Bar    	| 6472819   	| 10/09/1991         	| jzu-9876 	| FIAT - Pulse Audace    	| 2022 	| SP - Poa            	| 123890398  	| 10/04/2020       	|          13/04/2020            	|                      	|
| John Jones 	| 09876823  	| 09/10/1987         	| liu-1092 	| VW - Nivus Highline    	| 2023 	| RJ - Rio de Janeiro 	| 901287310  	| 10/04/2021       	| 20/05/2021           	|                 	|

A importância de identificar as entidades já começa na 1FN, pois dessa forma, geralmente fica mais fácil de saber quais atributos devemos mover para cada entidade. Há quem comece pela separação dos atributos porém, independente da forma que se inicia a normalização, o produto final é o que importa. 

## Chave Primária

Aqui temos o primeiro contato com um dos conceitos mais imporantes da normalização e, consequetemente, do modelo relacional: `chave primária` é um conceito utilizado para definir a atomicidade das tuplas em uma entidade e garantir que ela seja única e exclusiva. Essa chave primária pode ser um atributo ou um conjunto de atributos que identifica a tupla da entidade única e que não altera-se seu valor. Dessa forma, ela serve como referência para relacionamentos e identificação única da tupla na entidade. Características:x

- Seu valor não se repete
- Não altera-se  o valor
- Identificador único

Um dos motivos de aplicarmos a chave primária é que já nos ajuda na normalização da 1FN.

## Aplicação da 1FN

### Entidade - Proprietário

| Id PK	| Nome       	| Documento 	| Data de Nascumento 	|
|----	  |------------	|-----------	|--------------------	|
| 1  	  | Jane Done  	| 83012310  	| 07/05/1966         	|
| 2  	  | John Doe   	| 45768123  	| 10/01/1970         	|
| 3  	  | Foo Bar    	| 6472819   	| 10/09/1991         	|
| 4  	  | John Jones 	| 09876823  	| 09/10/1987         	|

### Entidade - Veiculo

| Id PK 	| Modelo                 	| Ano  	|
|----	    |------------------------	|------	|
| 1  	    | Toyota - Corolla XLI   	| 2023 	|
| 2  	    | GM - Tracker 1.0 Turbo 	| 2021 	|
| 3  	    | Nissan - Versa 1.6 GL  	| 2015 	|
| 4  	    | FIAT - Pulse Audace    	| 2022 	|
| 5 	    | VW - Nivus Highline    	| 2021 	|

### Entidade - Registro Veiculo

| Veiculo Id PK	| Proprietario PK/FK |Cidade|Estado| Renavam     	| Placa                	  | Data de Registro  	| Data Inicio Posse | Data Fim Posse |
|-------   |------ |----- |----- |-------------	|----------------------- |-------------------	|--------------------- | ---------------- |
| 1  	     |    1               |   1  |1    | 4783912211  	| iju-8172   	            |  23/04/2024         |      27/04/2024      |
| 2  	          |    2               |   2  |1    | 2378465920  	| fpw-97f4                |  10/03/2022         |      13/03/2022      | 
| 3  	          |    3               |   3  |1    | 1209384741  	| gec-4841                |  10/03/2013         |      11/02/2013      | 
| 4  	          |    4               |   4  |2     | 123890398   	| jzu-9876                |  10/04/2020         |        13/04/2020    | 
| 5             |    5               |   5  |3     | 901287310    | liu-1092                |  10/04/2021         |      20/05/2021      | 

### Entidade - Estado

|Id  PK | Nome           |
|----   |----------------|
|1      | São Paulo      |
|2      | Minas Gerais   |
|3      | Rio de Janeiro |

### Entidade - Cidade

|Id PK | Estado | Nome           |
|----  |------- |----------------|
|1     |   1    | Suzano         |
|2     |   1    | Guarulhos      |
|3     |   1    | Poa            | 
|4     |   2    | Belo Horizone  |
|5     |   3    | Rio de Janeiro |

As tabelas estão na 1 Forma normal pois:

- Removemos atributos multivalorados
- Removemos duplicidades
- Identificamos as chaves únicas (primárias e candidatas)


Para visualizar melhor como ficaria o modelo até o momento: [Modelo Entidade Relacionamento](https://viewer.diagrams.net/?tags=%7B%7D&highlight=0000ff&edit=_blank&layers=1&nav=1&title=emd.drawio#R7VhdU%2BIwFP01nXEfnOmHoDwuIC4jOqzsus%2BxCW3GtGHSIOCv3xua9BstjquMyxPNufckae65l9tY3iBaXwm0CG84Jsxybby2vKHluo5j9%2BBHIZsUOb%2FopkAgKNZOOTCjz0SDtkaXFJOk5Cg5Z5IuyqDP45j4soQhIfiq7DbnrLzqAgWkBsx8xOroH4plmKIXHTvHfxAahDJ7YW2JkHHWQBIizFcFyLu0vIHgXKZP0XpAmDo8cy4pb7TDmm1MkFi2Idxcz65jHgzJ%2BvTXvTOZPZ7%2FHJ3qWZ4QW%2BoXngq%2BEJRIJCjXG5cbcxrJikYMxTDq%2ByFleII2fKlWTyTyH82oH3JBn3ksEQOTAwCYhdTBhaMreswUE2CFCr6MMcGaNAe75jhnZqz3Ym8nFfwxi4qr%2BCQB%2F6k5EjuDJiiRZismDMqKURJu11MDxGgQw7MPbCIUIHy9vlp%2BFVJJZgvkK2AFalevISPzivVwmLMlQpJ1AdLhuSI8IlJswEVbjVJ0qrg9PV7lwnO6GguLojNEpMUeZFPneoAHLYk95OHW5GG5fWC49sn0%2BpvldpkK94OAp0BuD6F%2FC0s3GobcX0ZwOFyxf%2BdsTJ%2BKXkgiVS5gDvsWJT7VlNQXXqLkXpGniSAjc5kJZMAZh2gOY77V7ZwyVoESCCqNg8mWNTyrSE8JS8WQQlH4rheQfGG0hR4yQQouYff5GMRgVPeiUF7MzNfVo%2BXSaamW838lFq8mlntC%2FSU7lpGPLSOdXrmOePan15GzpjoyxjuLyLaP4I2m73FdT18p773W4T6UvO%2FUgntHAqqCAOixBHxGCfCcN7YSWd%2F97irpNpUArY7xMO0oYOLRjopQbEtbuA8oRpikjqNdvcYliAnzmlO1yWii3pEYPaGo0sq0YU4Z8tEbeLoxylNrb%2Bo4pr7q6e0pTxLyhglGNHqN%2FYULc6d1Eu5ZmDPw3XOuV8u5VPLHavyh1dipfNh1Pv%2FDzpT5%2Fb%2FsvnCG91oH9lBaL6d%2Bf5P%2B8x0z%2FGM%2FubzDy%2FDGu5txNcObO6KTXX1V8XbnP%2Frvdw7pNgaG%2Ba3x1la4e%2Fcu%2FwI%3D)

Podemos iniciar a [segunda forma normal](./2FN.md) agora. 
