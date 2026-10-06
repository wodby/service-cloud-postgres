# Cloud PostgreSQL on Wodby

This service stands for a managed PostgreSQL server that runs at a cloud provider, outside the cluster. It has no containers, volumes or configuration of its own in the environment.

## What Wodby sets up

- The server is a managed database created on Wodby through a cloud provider integration and selected for this service when the application is created.
- One database and one user are declared for the environment, both named after the application and the environment. The user's password is generated once per environment (token `password`). The application does not create them.

## How a linked service reaches it

- Host and port are those of the managed database server, not a service name inside the environment.
- A service linked to this one receives the host, port, database name, user name and password as environment variables defined by its own link (for example `DB_HOST`, `DB_PORT`, `DB_NAME`, `DB_USERNAME`, `DB_PASSWORD` on the PHP service). Read those in the application; do not hardcode the provider's address.

## What is not here

- There is no database container to open a shell in, and no server settings on this service. Server parameters, storage and versions are managed on the managed database itself.
- The manifest declares no backups, imports or actions for this service.
