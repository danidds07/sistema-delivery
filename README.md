**English** | [Português](README.pt-BR.md)

# Food Delivery System

A food delivery order management system in Java, built for my university Object-Oriented Programming course. It can be used in two ways: a command-line interface and a graphical interface, both talking to the same SQLite database.

## What it does

- registers customers, restaurants (with menu items) and delivery drivers;
- creates orders with multiple items from a restaurant's menu;
- automatically assigns an available delivery driver;
- tracks and updates order status (`REALIZADO`, `EM_PREPARO`, `EM_ENTREGA`, `ENTREGUE`, meaning placed, preparing, out for delivery and delivered);
- lists orders with all their details;
- works the same from the terminal or the graphical interface.

The project started as a CLI application and later gained the graphical interface, keeping the same business logic behind it.

## Tech stack

- Java
- Object-Oriented Programming (inheritance, encapsulation, abstract classes, enums)
- SQLite via JDBC for persistence
- Command-line interface (CLI) and graphical interface (GUI)

## How to run

This project uses SQLite via JDBC. Before running it, download the SQLite JDBC driver (`sqlite-jdbc-3.45.3.0.jar`) and place it in the `lib/` folder.

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

The `delivery.db` file is created automatically on the first run.

## Project structure
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
|-- bin/               # compiled files
|-- delivery.db
|-- COMO_RODAR.txt
`-- README.md
```

## Academic context

Built for my university Object-Oriented Programming course, as an exercise in modeling with inheritance, encapsulation and persistent (non in-memory) data.

## Author

Developed by Daniel Augusto Silva.
