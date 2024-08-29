## Backend

A Django server that provides an API for the Flow related operations. It uses Django Rest Framework to create the API endpoints.

### Setup

1. Install Docker, Git, and Make
2. Clone the repository
3. Run `cp .env.sample .env`
4. Run `make` to install the project dependencies and start the development server at `http://localhost:8000`
5. Run `make migrate` to apply the migrations
6. Run `make createsuperuser` to create a superuser

### Commands

- Run `python manage.py migrate` to apply the migrations
- Run `python manage.py createsuperuser` to create a superuser
- Run `python manage.py runserver 0.0.0.0:8000` to start the development server

#### Makefile

Run `make <command>` to execute the commands below:

- `build`: Build and start the Docker containers in detached mode
- `up`: Start the Docker containers without rebuilding
- `migrations`: Create new database migrations for the Django project
- `migrate`: Apply database migrations, including Django Celery Results
- `createsuperuser`: Create a new Django superuser
- `shell`: Access the shell of the backend container
- `db-shell`: Access the PostgreSQL shell inside the database container
- `logs`: View the logs of the backend container
- `db-logs`: View the logs of the database container
- `down`: Stop and remove the Docker containers
- `broker-shell`: Access the shell of the broker container
- `broker-logs`: View the logs of the broker container
- `management`: Enable RabbitMQ management plugins
- `celery-logs`: View the logs of the Celery container
- `celery-shell`: Access the shell of the Celery container
- `celery-beat-logs`: View the logs of the Celery Beat container
- `celery-beat-shell`: Access the shell of the Celery Beat container
- `worker-user`: Create a new Django superuser with the username "worker"

### Good to know

- Supported Types: `int`, `float`, `str`, `bool`, `list`, `dict`, `tuple`, `set`, `None`
- Scope - It is similar to the scope in programming languages. It is flow within flow. It is used to implement nodes like conditional, loop, block.

### Type of nodes

- BaseNode - A node that is used as base for all other nodes. It represents a block that can have input and output slots
- Data Node - A node that stores value and its type. It outputs the type transformed value when executed
- Function Node - A node that represents a function definition. It executes the function when executed. The function is executed using `eval` where the parameters are passed as a `locals`
- Conditional Node - A node that takes condition as input along with its type and different case values. When it is executed, It compares the condition with the case values and the one which matches it execute the scope attached to that case as a new flow
- ForEach Node - A node that takes an iterable as input. It picks each element from the iterable and input the element to the scope attached to node and execute it as a new flow
- Block Node - A node that represents a block of code. It executes the scope attached to it as a new flow
- Input Node - A node that has only output slots. It is used to define the input of the flow
- Output Node - A node that has only input slots. It is used to define the output of the flow
- Flow Node - A node that represents a flow. It is used to reuse the flow in multiple places. The input and output slots of the flow node are created based on the input and output nodes of the flow it represents

### Trigger

It is an event that starts the flow execution

#### Periodic

It is a trigger that periodically executes the flow. `Celery` and `Celery Beat` are used to implement the periodic trigger. `RabbitMQ` is used as the message broker. `Celery` spins up workers to execute the tasks. Workers listen to the message broker for the tasks to execute. `Celery Beat` is used to schedule the periodic tasks and push the tasks to the message broker. The periodic trigger can be of two types:

- Interval - It is a periodic trigger that executes the flow at a fixed interval. The interval is defined in seconds
- Crontab - It is a periodic trigger that executes the flow based on the crontab expression

#### Webhook

It is a trigger that executes the flow when a `POST` request is made to the webhook URL. The webhook URL is generated when the webhook trigger is created
