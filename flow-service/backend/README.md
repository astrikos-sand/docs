## Setup

1. Install Docker, Git, and Make
2. Clone the repository
3. Run `cp .env.sample .env`
4. Run `make` to install the project dependencies and start the development server at `http://localhost:8000`
5. Run `make migrate` to apply the migrations
6. Run `make createsuperuser` to create a superuser
7. Go to `http://localhost:8086` to setup the influxdb

## Commands

Explore the `Makefile` to see all the available commands.

## API Documentation

- Type of nodes
    - BaseNode - A node that is used as base for all other nodes. It represents a block that can have input and output slots
    - Data Node
    - Function Node
    - Conditional Node
    - ForEach Node
    - Block Node
    - Input Node
    - Output Node
    - Flow Node