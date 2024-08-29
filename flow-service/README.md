# Flow Service

It is a service that handles the flow related part of the application. It consists of the following components:
- [React Flow](/flow-service/react-flow/) - A react component that renders the flow in angular based thingsboard frontend `ui-ngx`
- [Backend](/flow-service/backend/) - A django server that handles the provide the flow related APIs
- [Worker](/flow-service/worker/) - A flask server that handle the execution of the flow.

## Execution

- Whenever a flow is executed, the frontend sends a request (containing the flow id) to the backend to execute the flow. The backend fetches all the nodes of the flow from the database and sends it to the worker. The worker then executes the flow asynchronously and save the logs to the archives.
- This architecture allows for better scalability as the worker can be scaled independently of the backend server.

![Integration](../_media/flow-service/integration.png ':size=350x250')
