# Astrikos AI (IITR)

> Smart Cities | Smart Data Centers | Smart Campus

### Overview

![integration](/_media/integration.png ':size=800x400')

### Terminologies

- Node - A node is like a block that can take inputs, process them and give outputs.
- Input slots - Input of a node is called input slots
- Output slots - Output of a node is called output slots
- Connection - Connection is a link from output slot of one node to input slot of another node
- How the node processes the input and gives output depends on the type of node
- Flow - A flow is a collection of nodes and connections between them. It can also be visualized as a function where it call other functions (nodes)
- Execution of a flow - All the nodes that have no inputs are executed first. Then the nodes that have all inputs available are executed. This process is repeated until no node with all inputs available is left. The execution of a flow is done parallelly.
- A flow can also have inputs and outputs

![Flow](/_media/flow.png ':size=700x350')

- Function Definition - A function definition is similar to a actual python function. **DO NOT confuse it with a node**.
