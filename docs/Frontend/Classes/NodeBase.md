# NodeBase

## Introduction
NodeBase is the super of all nodes.  Extend from this base when creating nodes.

## Methods

### constructor(name)

| Argument | Type  | Required | Description |
|----------|-------|----------|-------------|
| name | String | yes | Pass the name of the node |

### subscribe(name, handler)
| Argument | Type  | Required | Description |
|----------|-------|----------|-------------|
| name | String | yes | Name of the event (listed below) |
| handler | Function | yes | Call back function which will be called when the event is raised.  The function will be passed an even object containing data as shown below.|

#### Possible events
| Name | data |
|------|------|
| onAdded | graph, node |
| onRemoved | node |
| onConfigure | info |
| onSelected | node |
| onDeselected | node |
| onConnectionsChange | input_type, slot, flag, link, x |
| onPropertyChanged | name, value, prev_value |

### unsubscribe(name, handler)
| Argument | Type  | Required | Description |
|----------|-------|----------|-------------|
| name | String | yes | Name of the event (listed below) |
 handler | Function | yes | The function originally passed during the subscribe |