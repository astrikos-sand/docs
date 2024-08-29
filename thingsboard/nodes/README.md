### Nodes

#### Function Node

- Definition is the *function definition* to which the function node is attached

    ![Function Node](../../_media/thingsboard/nodes/function.png ':size=350x250')

#### Data Node

- Data node is like a variable in a programming language. It can be used to store data and can be accessed by other nodes in the flow.

    ![Data Node](../../_media/thingsboard/nodes/data.png ':size=350x250')

#### Conditional Node

- First input of the conditional node is the condition
- Value type for the condition and cases should be same
- It is similar to switch case in programming languages
- `Add cases` is used to add case name and value
- `Default` case is automatically created and it is executed when none of the cases are true
- `condition` slot is automatically created
- `_case` slot is automatically created for scope of each case

    ![Conditional Node](../../_media/thingsboard/nodes/conditional.png ':size=350x250')

#### For Each Node

- First input of the for each node is the list
- `list` slot is automatically created
- `_element` slot is automatically created for the scope flow `input` node

    ![For Each Node](../../_media/thingsboard/nodes/for_each.png ':size=350x250')

#### Block Node

- Independent block of nodes for better organization

    ![Block Node](../../_media/thingsboard/nodes/block.png ':size=350x250')

#### Input Node

- It can have only output slots

    ![Input Node](../../_media/thingsboard/nodes/input.png ':size=350x250')

#### Output Node

- It can have only input slots

    ![Output Node](../../_media/thingsboard/nodes/output.png ':size=350x250')

#### Flow Node

- It represents another flow and inputs passed to the flow node are passed to the represented flow

    ![Flow Node](../../_media/thingsboard/nodes/flow.png ':size=350x250')
