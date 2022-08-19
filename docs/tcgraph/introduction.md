# Introduction

## Terminology
TcGraph uses a set number of moving pieces to function.  By knowing the name and reason behind each of the pieces will allow you to read, adapt and create more of the same.  The Goal of TcGraph is to be a highly expandable framework which can be used to solve any PLC coding project. 

### Graph
A graph is a program written in a graphical way.  It both describes the layout and connection of nodes and is responsible to execute them in a given order. 

### Node
Nodes are the graphical language building blocks of a graph.  Nodes represent program functionality, state and program flow.  They fully encapsulate processes and will do their job when told to execute by their parent graph.  Nodes can be created, cloned, moved and deleted as needed.  Nodes can transfer information to other nodes by the use of ports.  Nodes can have user settings in the form of properties and nodes can return data to the user in the form of content. 

### Ports (Input and Output)
Nodes may require data in order to perform a function.  An input port allows a node to retrieve data from another Node's output port.  Likewise, the output data from a node may be made available to other nodes by the use of an output port.  Ports are read and written in realtime and should not be confused with properties and content which is an asynchronous process. 

### Properties
TBA

### Content
TBA

### Links
TBA