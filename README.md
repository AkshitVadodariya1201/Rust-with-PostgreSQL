# DB-Data Project

## Overview

This project is a Rust application that interacts with a PostgreSQL database to manage authors and books. It demonstrates basic CRUD operations using the `postgres` crate.

## Prerequisites

- Rust and Cargo (See [Rust Installation](https://www.rust-lang.org/tools/install))
- Docker and Docker Compose (See [Docker Installation](https://docs.docker.com/get-docker/))
- PostgreSQL client (Optional, for direct database interaction)

## Setup

1. Clone the repository:

```sh
git clone <repository-url>
cd <repository-directory>
```

2. Start the PostgreSQL database using Docker Compose:

```sh
docker-compose up -d
```

This command starts a PostgreSQL instance and an Adminer instance for database management accessible at `http://localhost:8080`.

3. Run the application:

```sh
cd db-data
cargo run
```

This command compiles the Rust application and executes it, performing the defined database operations.

## Structure 

- `src/main.rs`: Contains the main application logic for interacting with the PostgreSQL database.
- `Cargo.toml`: Contains the project metadata and dependencies.
- `docker-compose.yml`: Contains the configuration for the PostgreSQL and Adminer services.

## Database Schema

The database schema consists of two tables: 
- `authors`: Contains the author information with the following columns:
  - `id`: Unique identifier for the author.
  - `name`: Name of the author.
  - `country`: Country of the author.
- `books`: Contains the book information with the following columns:
  - `id`: Unique identifier for the book.
  - `title`: Title of the book.
  - `author_id`: Foreign key referencing the `authors` table.
  

## Usage

The application provides a command-line interface (CLI) to interact with the database. The available commands are:

- `list-authors`: List all authors in the database.
- `create-author <name>`: Create a new author with the given name.
- `delete-author <id>`: Delete the author with the given ID.
- `list-books`: List all books in the database.
- `create-book <title> <author_id>`: Create a new book with the given title and author ID.
- `delete-book <id>`: Delete the book with the given ID.
- `help`: Display the list of available commands.
- `exit`: Exit the application.
  
## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
