OPC UA Server Simulation
====

## About repository
In this repository you will find an example of OPC UA Server simulation where **Node-RED act as OPC UA Server**. 

> This respository is part of **OPC UA Course** published at ✅
> https://codeandcompile.com/course/learn-opc-ua-with-node-red

## What you can do with this repository?
 -  Simulating OPC UA Server using flow variables Testing 3rd party OPC
 -    UA client for read and write operations  Creating a layer of OPC UA
 -    over non OPC UA devices like Arduino, relay based PLC etc.

## How to use this repository with PLC or Arudino?

 - Read the controller (PLC or Arduino) using Serial or MODBUS TCP/IP communication.
 -  Store the information in the flow variables by replacing the timestamp (test values).
 - That's it, your device is ready to be accessed via OPC UA client

## Understanding flow:

### OPC UA variable declaration
OPC UA variables are defined in the following node. Open this node and check the `Address space` to see the variable declaration

![image](https://user-images.githubusercontent.com/48238929/210648385-aee5cb65-05f7-4977-92cd-7d30e1faaa84.png)

### Write to OPC UA Input variables
In this example, inject nodes with regular interval are used to inject random values to the flow variables which are used in the OPC UA input variable declaration. 

![image](https://user-images.githubusercontent.com/48238929/210648871-60a1d7be-bec4-4a16-a53c-b0ecbc20642c.png)


### Write to OPC UA Output variables
In this example, random math function is used to write random values to the flow variables which are used in the OPC UA output variable declaration. 

![image](https://user-images.githubusercontent.com/48238929/210649503-2b91e735-df00-4917-ac37-4d3d117215d2.png)

## Data flow Case 1: Using random values
```mermaid
graph LR
A[Random values] --Write--> B[Node-RED flow variables] --Write Input variables--> C[OPC UA Server] 
B --Write Output variables--> C
```

## Data flow Case 2: Using Arduino values
### Read data
```mermaid
graph LR
A[Arduino I/Os] --Reads via Serial--> B[Node-RED flow variables] --Write to variables--> C[OPC UA Server] 
```


## Data flow Case 3: Using PLC values
### Read data
```mermaid
graph LR
A[PLC I/Os] --Reads via MODBUS--> B[Node-RED flow variables] --Write to variables--> C[OPC UA Server] 
```

### Reading OPC UA variables using UaExpert
![image](https://user-images.githubusercontent.com/48238929/210653141-4a3c6353-b4f4-4767-9188-c592ec87f44d.png)



