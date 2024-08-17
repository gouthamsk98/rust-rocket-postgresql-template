# Rocket - CRUD example

This app is crud operation with rocket rs with postgress backend

## Dependency

- PostgreSQL database installed and setup
- The latest version of Rust (this porject uses v1.79.0)

## Running locally

- Install libpq for PostgreSQL
  - linux
    `sudo apt-get install libpq-dev`
  - macos
    ```bash
    brew install libpq
    brew link --force libpq`
    echo 'export PATH="/opt/homebrew/opt/libpq/bin:$PATH"' >> ~/.zshrc
    source ~/.zshrc
    ```
  - windows
    `Who uses windows!!!"
- Install Diesel CLI for database setup
  `cargo install diesel_cli --no-default-features --features postgres`
- In the top-level project directory, run the following command with your connections details:<br/>
  `echo DATABASE_URL=postgres://username:password@localhost/blog > .env`<br/>
  change this to your postgress url
- Navigate into the infrastructure folder `cd infrastructure` and run the command `diesel migration run`
- Navigate back to top-level project directory and run `cargo run`<br/>

  **Now You Are Ready to fly with Rocket🚀🚀🚀**

## Project Architecture

This Project follows the Clean Architecture model. Our architecture will follow as such that the:

- API Layer will handle the API requests and act as our route handler.
- Application layer will handle the logic behind the API requests.
- Domain layer will hold our database models and schemas.
- Infrastructure layer will hold our migrations and database connections.
- Shared layer will hold any other models our project will need such as response structures.

```
Folder Structure
.
├── Cargo.lock
├── Cargo.toml
├── api
│   ├── Cargo.toml
│   └── src
│       └── lib.rs
├── application
│   ├── Cargo.toml
│   └── src
│       └── lib.rs
├── domain
│   ├── Cargo.toml
│   └── src
│       └── lib.rs
├── infrastructure
│   ├── Cargo.toml
│   └── src
│       └── lib.rs
└── shared
    ├── Cargo.toml
    └── src
        └── lib.rs
```

## Author

[Goutham S Krishna](https://www.linkedin.com/in/goutham-s-krishna-21ab151a0/)
