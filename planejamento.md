#  Modelagem 101 - Estudo de caso

Para manter o controle dos carros de uma cidade a secretária municipal de trânsito decidiu criar um banco de dados dos proprietários dos veículos e suas respectivas características. O proprietário pode possuir mais de um carro, e o mesmo carro pode possuir outros proprietários em diferentes momentos. Um carro não deve ter mais de um dono por vez.
Utilizaremos as técnicas de normalização para criar um modelo relacional que será implementado em um banco de dados. 

> **🥲 Vinicês:** Este caso está faltando muitas informações e só foi criado para ser uma ideia que possamos nos basear para estudar a Normalização. Adiante, conforme realizamos a normalização essas informações virão à tona.
> Perdoe a preguiça da voz da pessoa que vos fala em sua cabeça 🥸.

Dessa forma, podemos dizer que o esboço inicial dos dados que precisamos para o controle será dessa forma:

| Nome       	| Documento 	| Data de Nascumento 	| Placa    	| Modelo                 	| Ano  	| Cidade              	| Renavam    	| Data de registro 	| Data Inicio Posse 	| Data Fim Posse	|
|------------	|-----------	|--------------------	|----------	|------------------------	|------	|---------------------	|------------	|------------------	|----------------------	|----------------------	|
| Jane Done  	| 83012310  	| 07/05/1966         	| iju-8172 	| Toyota - Corolla XLI   	| 2023 	| MG - Belo Horizonte 	| 4783912211 	| 23/04/2024      	|         27/04/2024             	|                      	|
| John Doe   	| 45768123  	| 10/01/1970         	| fpw-97f4 	| GM - Tracker 1.0 Turbo 	| 2021 	| SP - Guarulhos      	| 2378465920 	| 10/03/2022       	|  13/03/2022                     	|                      	|
| Foo Bar    	| 6472819   	| 10/09.1991         	| gec-4841 	| Nissan - Versa 1.6 GL  	| 2015 	| SP - Suzano         	| 1209384741 	| 10/03/2013       	| 10/03/2013           	|                 	|
| Foo Bar    	| 6472819   	| 10/09/1991         	| jzu-9876 	| FIAT - Pulse Audace    	| 2022 	| SP - Poa            	| 123890398  	| 10/04/2020       	|          13/04/2020            	|                      	|
| John Jones 	| 09876823  	| 09/10/1987         	| liu-1092 	| VW - Nivus Highline    	| 2023 	| RJ - Rio de Janeiro 	| 901287310  	| 10/04/2021       	| 20/05/2021           	|                 	|

## Idenitificando as entidades

![Entidade](./img/entidade.png)

Para iniciarmos a normalização um processo importante é identificar as entidades que são abordadas no cenário que estamos entidades. 
Algumas formas de identificá-las:

- Substantivos geralmente são forte índicios de entidades.
- Alguns entidades deverão ser especificadas o que poderá gerar novas entidades dentro do cenário.
- Algumas entidades representam algo mais abstrato como eventos mas que também possuem atributos para que possamos registrá-los. Ex.: Um vôo de avião, Uma viagem de ônibus, Uma festa, etc...

Dado o caso de estudo podemos identificar algumas entidades: 

- **Estado**
- **Cidade**
- **Veiculo**
- **Registro Veiculo**
- **Proprietário**
 
Estas foram a identidade que foram identificadas inicialmente. 

> Nem sempre todas as entidades entrarão dentro do contexto que será modelado. Afim de simplificar o caso de estudo deixaremos de fora as entidades `Secretária`, `Motandora` e `Modelo` que poderiam ser usadas em outros cenários caso a complexidade do sistema seja maior.
> Em documentos contendo o caso de negócio, geralmente as informações serão mais claras que esse caso (ou as vezes não mesmo). Sempre questione em dúvidas pois entender o conceito faz total diferença no produto final.

Com todas essas informações podemos explorar a as formas normais para nos auxiliar no desenho da solução.

Acesse aqui para continuar: [1 Forma Normal](./1FN.md)