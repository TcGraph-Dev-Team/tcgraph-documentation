# Literal, Display, Bundle and Un-bundle Nodes

## Introduction
Nodes come in all shapes and sizes, but in some instances we have common functionality across node packs. This page will talk about 4 of these common node types. 

These are,
* Literal
* Display
* Bundle
* Un-bundle

## Rules
Before we dive in to the definition of each, we can first start by defining some rules.  This will help us to identify what type of node we are looking to make. 

|          |Literal|Display|Bundle|Un-bundle|
|----------|-------|-------|------|---------|
|Properties|Only 1 |No     |Yes   |No       |
|Inputs    |No     |Only 1 |Yes   |Only 1   |
|Output    |Only 1 |No     |Only 1|Yes      |
|Content   |No     |Yes    |No    |No       |

## Literal (Node_Literal_DataType)
A literal node allows users to setup a value for the target datatype. 

A literal node must only contain a single property and a single output.  The property will be passed to the output in the PLC backend. 

The node may contain any number of widgets or code to drive the property, but in most cases the single property will be linked to a single widget.  

Literals should use the following option when adding the property as no inputs are permitted.
```javascript
{suppressInput: true}
```

### Example
The Node_Literal_TcVnVector4_LREAL literal provides the user with a single color picker.  From this example you can see that a literal node gives the user a method of working with the datatype as a whole entity.  

This differs from a bundle node of the same type.

## Display (Node_Display_DataType)
A display node 

## Bundle (Node_Bundle_DataType)
TBA

## Un-bundle (Node_Unbundle_DataType)
TBA