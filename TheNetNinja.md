# GraphQL Tutorial
https://www.youtube.com/watch?v=Y0lDGjwRYKw&list=PL4cUxeGkcC9iK6Qhn-QLcXCXPQUov1U7f

## Intro
* Will build gql server using Node.js
* will be querying that gql server from FE
* query and retrieve info from gql server

simplistic app UI desgin: less work, less css
iamshaunjp/grahpql-playlist

https://youtu.be/bUD6ERbcXrQ
##  GraphQL Tutorial #2: A Birdseye View of GraphQL

* REST API endpoints use urls to control different types of data
* FE makes AJAX/fetch requests to endpoints to retrieve information
* So you retrieve your information based on resources, one bye one based on endpoints

Graphql you retrieve information based on a graphql so you can go to a node and retrieve information but since they are connected then you an retrieve other types of information available on the same call.


## GraphQL Tutorial #3 - Project (stack) Overview
https://youtu.be/g3IBx2RFl38

Server/Node.js: Express App, GraphQL server
* Describe how our data graph looks. Design our data relationship, how gql can walk from one to another. Our entry points into the graph

crapp + apollo -> server -> mLab MongoDB

## GraphQL Tutorial #4 - Making Queries (front-end preview)
https://youtu.be/bX2e4FILf78

Graphiql: dummy FE app to form and retrieve querie data

dev tools Network tab shows Headers info. The Request Paylod shows an object with 
* operationName: null
* query: "..."
* variables: null

query property is just what looks like a string. Nothing special. The special thing happens when gql server receives that string and it can parse it (pull it apart) so that it understands that string and knows what data to return. How to walk/traverse the graph, how to grab info we requested and how to return it back to us, the client, the browser.

# GraphQL Tutorial #5 Express App Setup
```js
const express = require('express')
const app = express();

app.listen(4000, () => {
 console.log('listening');
 });
```

# GraphQL Tutorial #6 - Setting up GraphQL
npm install graphql express-graphql 
* graphql: JS implementation
* allows express to understand gql

Use as middleware in a single route, like an endpoint to interact with gql data
* app.use('/graphql', when someone goes to this route, express knows you want to interact with gql
* since express in its own doesn't understand gql, it will hand it off to graphqlHTTP
* gqlHTTP knows how to handle gql requests

gql error obj format:
{"errors": ["message":"you got err"}]}

Ultimate goal for creating gql server is to allow to queries to drop into our grahp at diff points to retrieve data.

Schema to describe how our graph will look. So gql-express knows exactly how to deal with our data and queries.

GraphQL Tutorial #7 - GraphQL Schema

