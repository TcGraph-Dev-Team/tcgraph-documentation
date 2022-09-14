# How to deal with methods

## Introduction
In most situations you will be writing nodes which wrap over both Functions and Function blocks, but you may come across a function block which exposes both methods and properties.  So the question is, how do you create a node for this?

## Solution
You will create a node specifically for calling the method.  If your function block has multiple methods or properties, then you will need a node for each.  

For example, 

If we had a Function Block of Motor and this had the .Start(Speed) and .Stop() methods then we would make the following nodes.

Node_Motor_Start
Node_Motor_Stop

Both would take a reference to a Motor as an input, and the _Start node would also take a speed as an input/property. 
