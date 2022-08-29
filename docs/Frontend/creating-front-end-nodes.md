# Creating front-end Nodes

## Introduction
Nodes are very flexible in their nature and can be programmed to perform almost any function or to display any content.  However, a typical node will consist of the following items.

* Inputs
* Outputs 
* Properties
* Content

### Example
This example shows the code found in the F_VN_GausianFilter Node which is located in the TcVision Node Pack.
```javascript
class Node_F_VN_GaussianFilter extends VisionNodeBase {

    constructor() {
        super("F_VN_GaussianFilter");
        this.addInput("ipSrcImage", "ITcVnImage");
        this.addProperty("nFilterWidth", 3, "UDINT", { onlyOdd: true });
        this.addProperty("nFilterHeight", 3, "UDINT", { onlyOdd: true });
        this.addOutput("ipDestImage", "ITcVnImage");

        this.addInformationUrl('Infosys', 'https://infosys.beckhoff.com/english.php?content=../content/1033/tf7xxx_tc3_vision/11087207179.html');
    };
};
```

## Getting started

### Create your node .js file

Your node will reside in its own JavaScript file.  This will be inside the NodePack's Nodes folder.  Use existing nodes as an indication of where your file should be placed.  

### Start with your Class

Next create your node class.  

```javascript
class Node_F_VN_GaussianFilter extends VisionNodeBase {

};
```

By convention, start your class with the "Node_" followed by the function, function block, or name of your node.  

In most cases you will be extending from either NodeBase, or VisionNodeBase.  VisionNodeBase was created to add functionality to our TcVision Nodes.  

### Call super()

We need to allow our based class to construct, so you must first call super(name) by passing in your node name. 

```javascript
super("F_VN_GaussianFilter");
```

### Add Inputs

Next we would add our node's inputs.  These are the ports located on the left hand side of a node and allow data to flow in at runtime.  

Use this.addInput(name, type, options) to create an input.  

```javascript
this.addInput("ipSrcImage", "ITcVnImage");
```
* "ipSrcImage" is the name of the input port.  This must match the name of the PLC NodeInput.  
* "ITcVnImage" is the type of the port.  Only outputs of matching type can be linked with this port.

### Add Properties

Use this.addProperty(name, default_value, type, options) to create a property.  

```javascript
this.addProperty("nFilterWidth", 3, "UDINT", { onlyOdd: true });
```

In the above example we have the following arguments.  

* "nFilterWidth" is the name of the property.  This must match the name of the PLC NodeInput.  
* 3 is the default value of the property. 
* "UDINT" is the type of property.  A widget will be automatically created based on this type. 
* { onlyOdd: true } is the options passed in to the property.  In this example, only odd values are allowed.

When adding a property using this method it will automatically add a widget and an input port of the same type.  More information on widgets can be found [here](/Frontend/widgets.md)  

You can disable the creation of an input port by supplying the option {suppressInput : true}

### Add Outputs

Use this.addOutput(name, type, options) to create an output port.  

```javascript
this.addOutput("ipDestImage", "ITcVnImage");
```

In the above example we have the following arguments.  

* "ipDestImage" is the name of the output port.  This must match the name of the PLC NodeOutput.  
* "ITcVnImage" is the type of the port.  Only outputs of matching type can be linked with this port.

### Add Content

Contents are used to report asynchronous information from the backend to the front end.  It is common to display content in a widget.  

Use this.addContent(name, default_value, type, options) to create a content.  

```javascript
this.addContent("display", false, "BOOL");
```

In the above example (taken from Node_Display_BOOL) we have the following arguments.  

* "display" is the name of the content.  This must match the name of the PLC content.  
* false is the default value of the content prior to receiving information from the PLC. 
* "BOOL" is the type of content.  A widget will be automatically created based on this type. 

When adding a content using this method it will automatically add a widget and setup a content handler of the same type.  More information on widgets can be found [here](/Frontend/widgets.md) 

### Add extras

All nodes have the option of adding extra information.  This is displayed when the user double clicks your node.  Some examples of what can be added are shown below. 

#### Information URL

You can add a link to a webpage using the following;

```javascript
this.addInformationUrl('Infosys', 'https://infosys.beckhoff.com/english.php?content=../content/1033/tf7xxx_tc3_vision/11087207179.html');
```

### Next add your node to the relevant Node Pack

Once your node is created you must register it with a node pack.  In our example of the F_VN_GaussianFilter we would locate the TcVisionNodePack.js file and add the following line.

```javascript
Graph.registerNodeByType("Vision/Image Filtering/F_VN_GaussianFilter", Node_F_VN_GaussianFilter);
```

This instructs Graph to learn your node.  You must supply the type and your class.  

The type argument can include forward slashes to indicate submenus.  This type must match the type in the PLC.  If you have any mistakes then the node will not be created when asked.  