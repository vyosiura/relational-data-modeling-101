# 3ª Forma Normal

- 🥸`Como está nos livros:` Uma entidade estará na 3ª forma normal se e somente se ela estiver na 1FN e 2FN e seus atributos não compoem nenhuma dependência contínua (transitiva).
- 🤓`Como eu entendo:` Não podemos ter situações onde: **Se A é B e B é C então, A é C (A -> B -> C)** 
- 😍`Na prática:` Um caso comum disso acontecer é quando temos 3 entidades que se relacionam entre si criando uma relacionamento fechando um formato de triangulo onde as entidades são os angulos e os relacionamentos compoem seus vértices.

No nosso modelo, olhando para a entidade `Registro Veiculo` deixamos escapar um atributo que acaba criando essa dependência transitiva: o `EstadoID`. Ele acaba sendo uma dependência contínua pois como a cidade faz parte de um estado sabendo a cidade que o registro aconteceu, automaticamente conseguimos resolver em qual estado o carro está registrado.

Dessa forma, apenas removendo o relacionamento entre `Estado` e `Registro Veiculo` conseguimos deixar nosso modelo na 3FN. Obtendo o seguinte resultado: [3FN](https://viewer.diagrams.net/?tags=%7B%7D&highlight=0000ff&edit=_blank&layers=1&nav=1&title=emd.drawio#R7ZpZc6M4EMc%2FjatmH2aKw8b2o6%2FsppJMuZK9Zt80oIAqgLxCju18%2BmmBBAjwlfW1Ez8FtaSW1Pr1HyGnZY%2Bi5a8MzYIH6uGwZRnesmWPW5ZlmkYf%2FgjLKrN0e05m8BnxZKPC8ETesDQa0jonHk60hpzSkJOZbnRpHGOXazbEGF3ozZ5pqI86Qz6uGZ5cFNatfxGPB5m11zEK%2B2%2BY%2BAHPFyxrIqQaS0MSII8uSiZ70rJHjFKePUXLEQ5F8FRcsn43a2rziTEc8106uJ3%2BP7EzGj9EL8vB4M0I7vrRZ%2BnlFYVzueApozNGMEeMUDlxvlLRSBYkClEMpaEbkNC7Rys6F6MnHLkvqjQMKCNvNOYohCoTDFDNuNxcCF25xZPoCWZhZXQee9iTnZ6hXvYx26os52KkThl9yXfFEv1xAu2nKiRGbrpHCVdTUdsgaj2UBOl4ooBC4sfw7EJvzISBuXJ8MfwiIBw%2FzZArDAugXSyDR2qJMpCYcbxcu0Nmvu%2BQMJhGmLMVNJEdFFQyVSxblhcFeKYjbUEZOoUYkrD7ueuCB3iQSOyBh1XDo2UNoYdlfJq9%2FNKynFBs93cGTz5PgzD8CkM3VoypO48gElT0%2FuMu7%2B2R13IrxJGQC%2FBhfEWJS2SXrC0sQmtewVPtYIifeQ7IiIYUdnMc05TbZxKGFVMCm0pi%2Fz7tNW5X0BNgiW0lIAoDOQCnM8UW%2Bp4DySiH2Rdl2HlF3b6grE%2FWOj0rnZ5ttHSPBYtdg%2BVPTNx5eJWRE8tIW9cR8%2Bwy0m6SkVuvUSbSIwRtrBrEdZR%2B8pS3LzvlO7WNfcQ%2BEZsA1mv2X0L255u%2FDZJcJw5OidOQ%2Fk3vfsXO7Xjd%2B34omRItjE%2FTO6i%2FWXOSyEyQ57FGn%2FPvnKbCAsD4KSqf3UwaBmIZMeFEADcsWpZGn4bIRaW5Zd71EfX5joiHPJxNd91MYd0xekVR5VxUXfuG01KRdJu67mb9WPraOYi%2B5saDp063ljoTkEHvKqqnFdWerqmdncE42pGq994vs4%2BV393LPj%2F1a7uYvTCu6X3S9La7F5ff6jBW%2F2bSElw%2FDmTvhttx%2Baix9nLmY7%2F4%2B5ctDOa2i9nSme8qFSeUCqtfuVzpnf3zymy8pW36EG%2FSDB2rvT89bmPipjxOaZKs1ZYNDm5ItK33x1Im8zDXvMf7JjHrF721PcKej5UOUMYD6tMYhZPCWgt%2BKXY49gbipzsoTh7fMKO%2F0wcUr7KaGxKqdoUUiX3AS8L%2FFs9f2h1Z%2FKYcwvN4WWo3XpUKU8wIREbISWaLIUqZp44qfivXFa7SkvLlztlrLoxZREQYNgsNRI3OmYs3xFvenkKG%2Bvgd37JlUIwmUJSR4RBx8qpPuIkeOcaUElhKrozOOmVULrKFyl4FgzVH3Yqjqp8sEDU%2FKcv5uv8D3k231Rvwhv0kfPWYBo%2FGR0VcI0zxbpZgN75Ync2852xrZBegr2H7gDhbO%2BKcvdbOx7NZwbBdPeztynP1yGBXHR0b6Pot%2FWUCrdg092MzF34tETbnwQF5dv4nPHeMLRjuyrNTcVT7Cjo2z02%2FJ1wiz4cUaOuECt3blWijdVaiLUcHMSd8X6LtiqN21dGxia5f8%2F%2BMROvHafN0QKtP761EO2eWaLsCdP%2B9El3NjKqjdwMNxeJfFrPmxT9%2B2pMf)


Finalizado a normalização podemos transformar nosso modelo lógico em físico, gerando comandos SQL de tabelas, constraints, etc...

Algumas ferramentas online já realizam a conversão de forma automática para maior praticidade. Como MySQL Workbench, SQL Server Management Studio, DBeaver, entre outras.

## Considerações finais

A 3FN pode ser considerada como a cereja do bolo. 
Na minha opinião, a 1FN e a 2FN devem ser tratadas com mais atenção pois nessas 2FN que definimos muitas das entidades e seus relacionamentos.

