## Worker

A flask server that executes the flow. 

### Commands

- Run `python app.py` to start the server

#### Makefile

Run `make <command>` to execute the commands below:

- `build`: Build and start the Docker container in detached mode
- `up`: Start the Docker container without rebuilding
- `shell`: Access the shell of the container
- `logs`: View the logs of the container

### Execution

- Whenever a environment is created, a docker image is built locally
- Whenever a flow is executed, a container is created from the environment associated with the flow, and the flow runs within this container
- This allow us to use third party libraries in the flow without installing them in the worker. It also help to avoid conflicts between different flows
- **Flow Manager** is a class that manages the flow execution. It finds all the nodes with no input and send them parallely to the **Node Manager**. The **Node Manager** check the type of the node and send it to the respective **Node Executor**. Flow Manager waits for the node manager to finish and then it sends the children nodes of the executed node to the node manager parallely again. This process continues until all the nodes are executed
- Different nodes can have different executor class. This allows us to have different execution logic for different nodes. It also ease in adding new nodes. We just need to create a new executor class and add it to the node executor map
- Since the flow is executed in a parallel manner, we are using the `lock` to avoid updating the same variable from multiple threads
