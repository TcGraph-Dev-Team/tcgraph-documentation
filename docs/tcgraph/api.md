# API

## getStatus(level, callback(reply))


### Method
```
GET
```

### Response
```javascript
{ 
   "uuid" : "xxx-xxx-xxx-xxx",
   "debug" : [],
   "info" : [
        {
            "name" : "router-memory",
            "dataType" : "RouterMemory",
            "value" : { 
                "startMemory" : 0,
                "currentMemory" : 0,
                "memoryDifference" : 0,
                "tcStartMemory" : 0,
                "tcStartMemoryDifference" : 0  
             } 
        }
   ],
   "warnings" : [],
   "errors" : [
        {
            "message" : "error-message",
            "reason" : "error-reason"
            // can also include custom key values
        }
    ],
    "nodes" : [
        {
            "id" : 1,
            "debug" : [],
            "info" : [
                    {
                        "name" : "profiler",
                        "dataType" : "PROFILERSTRUCT",
                        "value" : { 
                            "lastExecTime" : 0,
                            "minExecTime" : 0,
                            "maxExecTime" : 0,
                            "averageExecTime" : 0,
                            "measureCycle" : 0  
                        } 
                    }
                ],
            "warnings" : [],
            "errors" : []
        }   
    ],
}
```

## getContent(nodeId, contentName, callback(reply)


### Method
```
GET
```

### Response
Primitive
```javascript
{
   "name" : "example-bool",
   "dataType" : "BOOL",
   "value" : true
}
```
Structure
```javascript
{
   "name" : "example-struct",
   "dataType" : "myStruct",
   "value" : {
      "myBool" : true,
      "myInt" : 123
   }
}
```