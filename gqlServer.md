# Minimal GraphQL Server
## by Mirko Nasato

#fetch #query # errors #noRedux

## Goal:

* 00:00 Minimal GraphQL Server
* 00:12:12 Minimal GraphQL Client
* 00:20:34 The "Job Board" Project
* 00:27:26 GraphQL Server Endpoint

Query:
* 00:34:37 Returning an Array of Jobs
* 00:41:34 Nested Objects in GraphQL Queries
* 00:45:01 Object Associations: Job/Company
* 00:52:05 Fetching Jobs in the Client
* 00:57:37 Arguments: Returning a Job by ID
* 01:02:52 Query Variables: Fetching a Job

Errors:
* 01:10:57 Handling GraphQL Error Responses
* 01:20:26 Fetching a Company by ID
* 01:25:53 Returning Jobs for a Company

https://www.youtube.com/watch?v=56uJzGsaLoI

* Create folder
* create express server.js

* npm i graphql graphql-tools apollo-server-express
* graphql : core
* graphql-tools : utilities ex makeExecutableSchema
* apollo-server-express: wrapper with utils; 
  - ex. grahpqlExpress for app route and exposing http

Describe data to be exposed by our API
* typeDefs: 
  - top level type
  - API interface
  - which queries can be sent by the client

ex. All a client can do is ask fo the greeting that returns a string value
```js
type Query {
 greeting: String
}
```

* Resolvers: process a request
  - it resolves the value of a field in this case greeting
  - Logic of how server will respond to user/client
  - How server responds, how each req is handled

```js
 Query: {
  greeting: () => 'Hello'
 }
```

Process Flow: typeDefs => resolvers => API 

* Any call to /grahpql will be taken care by graphqlExpress
  - graphqlExpress tells express to server gql schema 
  - app route, expose to http
  
  
