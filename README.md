# loopback-example-remote
**NOTE: This example is not yet finished!  Please check back later.**

This is an example of using the LoopBack [remote connector](http://docs.strongloop.com/display/LB/Remote+connector).

## Overview

The example has the following structure:
- `server`: contains a LoopBack application that connects to a backend data source (just the in-memory data source here) and provides a CRUD API (both Node and REST) to interact with the data source.  
- `client`: A Node application that connects to the LoopBack server application using the [remote connector](https://github.com/strongloop/loopback-connector-remote).  This acts as a very simple Node client SDK for LoopBack.
- `common/models`: Model definitions shared between client and server applications.  Using a shared model definition ensures that client and server expect the same model structures.

## How to run the example

```
$ cd client
$ npm install
$ cd ../server
$ npm install
$ slc run server
```
