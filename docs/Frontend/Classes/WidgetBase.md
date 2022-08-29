# WidgetBase

## Introduction
Widgets are visual components which can be used on a node.  WidgetBase is the base class for widgets.

## Methods

### constructor(node, property, options)

| Argument | Type  | Required | Description |
|----------|-------|----------|-------------|
| node | Object | yes | Widgets hold a reference to their parent node |
| property | String | optional | Allows you to link a property to a widget.  Any time the widget changes then the property will be updated too. |
| options | Object | optional | Available options listed below |

### Property

Any time a property is linked then the widget will attempt to automatically use its name and default value.  

### Options

Widgets support an option object, which may contain a number of variables used to control it's styling and function.  The following options are supported by the WidgetBase class.

| Option Name | Type | Description |
|-------------|------|-------------|
| callback(value, node) | Function | Called when the widget's value is written to.  Returning false will prevent the write. |
| disabled | Boolean | Disables the widget when set to true |
| label | String | Allows you to supply a label for the widget. |
| property | String | Allows you to link a property to a widget.  Any time the widget changes then the property will be updated too. |
| readOnly | Boolean | When widgets are added with addContent then the readOnly flag is automatically set true. |
| toPropertyConversion(value) | Function | Called prior to the widget value being written to it's linked property. Return value will be used to write to the property.|  
| fromPropertyConversion(value) | Function | Called prior to the widget value being written to from it's linked property. Return value will be used to write to the widget.| 