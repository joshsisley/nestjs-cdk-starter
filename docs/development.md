# Setup and development

- [Setup and development](#setup-and-development)
  - [First-time setup](#first-time-setup)
  - [Installation](#installation)
    - [Database](#database)
    - [Configuration](#configuration)
    - [Dev server](#dev-server)
  - [Generators](#generators)
  - [Docker](#docker)
    - [Docker installation](#docker-installation)
    - [Docker-compose installation](#docker-compose-installation)
    - [Run](#run)

## First-time setup

Make sure you have the following installed:

- [Node](https://nodejs.org/en/) (at least the latest LTS)
- [Yarn](https://yarnpkg.com/lang/en/docs/install/) (at least 1.0)

## Installation

```bash
# Install dependencies from package.json
npm install
```

> Note: don't delete yarn.lock before installation, See more [in yarn docs](https://classic.yarnpkg.com/en/docs/yarn-lock/)

### Database

> Note: Awesome NestJS Boilerplate uses [TypeORM](https://github.com/typeorm/typeorm) with Data Mapper pattern.

### Configuration

Before start install PostgreSQL and fill correct configurations in `.env` file.

> Note: You can find the tutorial for installing PostgreSQL by going to the [PostgreSQL Tutorials](https://www.postgresqltutorial.com/install-postgresql/) web page.

```env
DB_HOST=localhost
DB_PORT=5432
DB_USERNAME=postgres
DB_PASSWORD=postgres
DB_DATABASE=nest_boilerplate
```

Some helper script to work with database

```bash
# To create new migration file
npm run migration:create migration_name

# Truncate full database (note: it isn't deleting the database)
npm run schema:drop

# Generate migration from update of entities
npm run migration:generate migration_name
```

### Dev server

```bash
# Launch the dev server
npm run start:dev

# Launch the dev server with file watcher
npm run watch:dev

# Launch the dev server and enable remote debugger with file watcher
npm run debug:dev
```

## Generators

This project includes generators to speed up common development tasks. Commands include:

> Note: Make sure you already have the nest-cli globally installed

```bash
# Install nest-cli globally
npm install -g @nestjs/cli

# Generate a new service
nest generate service users

# Generate a new class
nest g class users

```

> Note: You can find the full list of commands in the official [Nest-cli Docs](https://docs.nestjs.com/cli/usages#generate-alias-g).

## Docker

if you are familiar with [docker](https://www.docker.com/) and [docker-compose](https://docs.docker.com/compose) then you can run built in docker-compose file, which will install and configure application and database for you.

### Docker installation

Download docker from Official website

- Mac <https://docs.docker.com/docker-for-mac/install/>
- Windows <https://docs.docker.com/docker-for-windows/install/>
- Ubuntu <https://docs.docker.com/install/linux/docker-ce/ubuntu/>

### Docker-compose installation

Download docker from [Official website](https://docs.docker.com/compose/install)

### Run

Open terminal and navigate to project directory and run the following command.

```bash
PORT=3000 docker-compose up
```

> Note: application will run on port 3000 (<http://localhost:3000>)

Navigate to <http://localhost:8080> and connect to you database with the following configurations

```text
host: postgres
user: postgres
pass: postgres
```

create database `nest_boilerplate` and your application fully is ready to use.
