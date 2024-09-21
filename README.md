# HBnB - AirBnB Clone Project (v1)

## Description

The AirBnB Clone Project is a simplified version of the real [AirBnB Website](https://www.airbnb.com/), aimed at learning full-stack web development. The project includes a web static interface, a dynamic website with a RESTful API, a MySQL database for persistence, and a command-line interpreter (CLI) to manage the backend data and objects.

This project is organized in multiple steps, focusing on building a modular, flexible, and scalable application. It emphasizes understanding how data is handled from backend to frontend, object-relational mapping, RESTful APIs, and web templating.

This first step (version) consists of a custom command-line interface for data management, and the base classes for the storage of this data.

## Features

- **Command Interpreter (CLI)** to create and manage different objects (Users, Places, etc.).
- **Object serialization and deserialization** to JSON for file storage and MySQL for persistent storage.
- **Dynamic web content** using Python and HTML/CSS.
- **RESTful APIs** for interaction with frontend clients.
- **Unit tests** for verifying correctness of models and storage engine.

## Command Interpreter

### How to Start the Command Interpreter

To start the command interpreter, you need to run the console.py file. Ensure that you are in the root directory of the project.

```bash
$ ./console.py
```

### Command Syntax

| Command | Description                                         | Syntax                                                                                                                                            |
| ------- | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| help    | Provides information about a specific command       | `(hbnb) help <command>`                                                                                                                           |
| create  | Creates a new instance of a class and prints the ID | `(hbnb) create <ClassName>`                                                                                                                       |
| show    | Prints the string representation of an instance     | `(hbnb) show <ClassName> <id>` or `(hbnb) <ClassName>.show(<id>)`                                                                                 |
| destroy | Deletes an instance based on the class name and ID  | `(hbnb) destroy <ClassName> <id>` or `(hbnb) <ClassName>.destroy(<id>)`                                                                           |
| all     | Prints all string representations of all instances  | `(hbnb) all` or `(hbnb) all <ClassName>`                                                                                                          |
| update  | Updates an instance based on the class name and ID  | `(hbnb) update <ClassName> <id> <attribute name> "<attribute value>"` or `(hbnb) <ClassName>.update(<id>, <attribute name>, "<attribute value>")` |
| quit    | Exits the command interpreter                       | `(hbnb) quit`                                                                                                                                     |
| EOF     | Exits the command interpreter                       | `(hbnb) EOF`                                                                                                                                      |

### The Console - Usage

The console works both in interactive mode and non-interactive mode (much like a Unix shell). It prints a prompt (hbnb) and waits for the user input.

### Interactive Mode - Examples

Your shell should work like this in interactive mode:

Create a New User

```bash
$ ./console.py
(hbnb) create User
d55bc64d-e555-45db-bf1f-648a8fbd43df
(hbnb)
```

Show an Object

```bash
$ ./console.py
(hbnb) show User d55bc64d-e555-45db-bf1f-648a8fbd43df
[User] (d55bc64d-e555-45db-bf1f-648a8fbd43df) {'id': 'd55bc64d-e555-45db-bf1f-648a8fbd43df', 'created_at': '2024-09-09T12:00:00', 'updated_at': '2024-09-09T12:00:00'}
(hbnb)
```

Update an Object

```bash
$ ./console.py
(hbnb) update User d55bc64d-e555-45db-bf1f-648a8fbd43df email "user@example.com"
(hbnb) show User d55bc64d-e555-45db-bf1f-648a8fbd43df
[User] (d55bc64d-e555-45db-bf1f-648a8fbd43df) {'id': 'd55bc64d-e555-45db-bf1f-648a8fbd43df', 'email': 'user@example.com', 'created_at': '2024-09-09T12:00:00', 'updated_at': '2024-09-09T12:10:00'}
(hbnb)
```

List All Objects

```bash
$ ./console.py
(hbnb) all
[User] (d55bc64d-e555-45db-bf1f-648a8fbd43df) {'id': 'd55bc64d-e555-45db-bf1f-648a8fbd43df', 'created_at': '2024-09-09T12:00:00', 'updated_at': '2024-09-09T12:00:00'}
(hbnb)
```

### Non-interactive Mode - Examples

But also in non-interactive mode: (like the Shell project in C)

```bash
$ echo "help" | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb)
$
$ cat test_help
help
$
$ cat test_help | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb)
$
```

### Project Structure

```bash
├── console.py       # Entry point of the command interpreter
├── models           # Contains all the models
│ ├── base_model.py  # Base class for all models
│ └── engine         # Storage engines (file_storage.py)
├── tests            # Unit tests for the project
|── README.md        # Project documentation
└── AUTHORS          # Contributors
```
