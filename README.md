# Sistema de Delivery

Sistema de gerenciamento de pedidos de delivery em Java, feito para a disciplina de
Programação Orientada a Objetos da faculdade. Tem duas formas de uso: uma interface de
linha de comando e uma interface gráfica, as duas conversando com o mesmo banco de
dados SQLite.

## O que dá para fazer

- cadastrar clientes, restaurantes (com itens de cardápio) e entregadores;
- criar pedidos com múltiplos itens a partir do cardápio de um restaurante;
- atribuir um entregador disponível automaticamente;
- acompanhar e atualizar o status de um pedido (`REALIZADO`, `EM_PREPARO`, `EM_ENTREGA`, `ENTREGUE`);
- listar pedidos com todos os detalhes;
- usar tudo isso tanto pelo terminal quanto pela interface gráfica.

O projeto começou como uma aplicação CLI e depois ganhou a interface gráfica, mantendo
a mesma lógica de negócio por trás.

## Tecnologias

- Java
- Programação Orientada a Objetos (herança, encapsulamento, classes abstratas, enums)
- SQLite via JDBC, para persistência
- Interface via terminal (CLI) e interface gráfica (GUI)

## Como executar

Este projeto usa SQLite via JDBC. Antes de rodar, baixe o driver JDBC do SQLite
(`sqlite-jdbc-3.45.3.0.jar`) e coloque dentro da pasta `lib/`.

**Windows**
```powershell
javac -cp "lib/sqlite-jdbc-3.45.3.0.jar;src" -d bin src\Main.java src\client\*.java src\database\*.java src\deliveryman\*.java src\orders\*.java src\restaurant\*.java src\system\*.java src\users\*.java
java -cp "bin;lib/sqlite-jdbc-3.45.3.0.jar" Main
```

**Linux/Mac**
```bash
javac -cp "lib/sqlite-jdbc-3.45.3.0.jar:src" -d bin $(find src -name "*.java")
java -cp "bin:lib/sqlite-jdbc-3.45.3.0.jar" Main
```

O arquivo `delivery.db` é criado automaticamente na primeira execução.

## Estrutura do projeto
```text
food-delivery-system/
|-- lib/
|   `-- sqlite-jdbc-3.45.3.0.jar
|-- src/
|   |-- Main.java
|   |-- client/
|   |   `-- Client.java
|   |-- database/
|   |   `-- Database.java
|   |-- deliveryman/
|   |   `-- Deliveryman.java
|   |-- orders/
|   |   |-- Order.java
|   |   `-- Status.java
|   |-- restaurant/
|   |   |-- Menu.java
|   |   `-- Restaurant.java
|   |-- system/
|   |   `-- AppSystem.java
|   `-- users/
|       `-- User.java
|-- bin/               # arquivos compilados
|-- delivery.db
|-- COMO_RODAR.txt
`-- README.md
```

## Contexto acadêmico

Feito para a disciplina de Programação Orientada a Objetos da faculdade, como
exercício de modelagem com herança, encapsulamento e persistência de dados fora de
memória.

## Autor

Desenvolvido por Daniel Augusto Silva.
