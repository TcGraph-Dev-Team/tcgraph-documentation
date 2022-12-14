# Widgets

## Introduction
Widgets are visual components which can be used on a node.  A node can have any number of widgets and are commonly in conjunction with properties to give end users the ability to change values.  

As widgets and properties typically go hand in hand, the default operation of node.addProperty() will automatically make a corresponding widget of the type if it is available and will link this to the property. 

The same is also true for content.  The default operation of node.addContent will automatically make a corresponding widget of the type provided, will set the option "readOnly" to true and will create a content handler to keep it updated.  

## Example
The following code adds BOOL widget when a BOOL property called "enable" is added. 
```javascript
class MyExampleNode extends NodeBase {

    constructor() {
        super("MyExampleNode");
        this.addProperty("enable", true, "BOOL"); // creates a BOOL widget with linked property
    };
};
```

The following code adds BOOL widget when a BOOL content called "display" is added. 
```javascript
class MyExampleNode extends NodeBase {

    constructor() {
        super("MyExampleNode");
        this.addContent("display", null, "BOOL"); // creates a readOnly BOOL widget with linked content
    };
};
```

## Options

Widgets support an option object, which may contain a number of variables used to control the styling and operation of a widget. Widgets have a few base options derived in [WidgetBase](/Frontend/Classes/WidgetBase.md), but typically this will be dependent of the actual widget implementation.  

### Options Example

Options can be added as the forth argument of addProperty

```javascript
class MyExampleNode extends NodeBase {

    constructor() {
        super("MyExampleNode");
        this.addProperty("enable", true, "BOOL", {callback : function(value,node) {console.log(value,node}});
    };
};
```