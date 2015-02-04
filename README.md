# loopback-example-remote

This is a very simple example of using the LoopBack [remote connector](http://docs.strongloop.com/display/LB/Remote+connector), [loopback-connector-remote](https://github.com/strongloop/loopback-connector-remote).

## Overview

The example has the following structure:
- `server`: A LoopBack application that connects to a backend data source (just the in-memory data source here) and provides a CRUD API (both Node and REST) to interact with the data source.  
- `client`: A Node application that connects to the LoopBack server application using the [remote connector](https://github.com/strongloop/loopback-connector-remote).  This acts as a very simple Node client SDK for LoopBack.
- `common/models`: Model definitions shared between client and server applications.  Using a shared model definition ensures that client and server expect the same model structures.  This simple example defines only
one model: `Person`, with a single property, `name`.
- `examples`: Contains examples of using the Node SDK in `client` to connect to the server API.
 - `create.js`: A simple example script that creates a new Person record (instance).

## How to run the example

Initially, you need to run `npm install` to install all the dependencies for both client and server.   
Then, start the server application.

```
$ cd client
$ npm install
$ cd ../server
$ npm install
$ slc run 
```

Now in another shell, run the example that uses the client "SDK."

```
$ node examples/create.js
Created Person...
{ name: 'Fred', id: 1 }
```

Now open LoopBack Explorer at http://0.0.0.0:3001/explorer/.  
This provides a view into the server application REST API. 

Go to http://0.0.0.0:3001/explorer/#!/People/find to expand the `GET /People` operation.
Then click **Try it!**.

In **Response Body**, you will see the record that `create.js` created via the Node client SDK:

```
[
  {
    "name": "Fred",
    "id": 1
  }
]
```
