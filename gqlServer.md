# Minimal GraphQL Server
## by Mirko Nasato

https://www.youtube.com/watch?v=56uJzGsaLoI

* Create folder
* create express server.js

* npm i graphql graphql-tools apollo-server-express
* graphql : core
* graphql-tools : utilities ex makeExecutableSchema
* apollo-server-express: wrapper with utils; 
* * ex. grahpqlExpress for app route and exposing http

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
* 

Process Flow: typeDefs => typeDefs => resolvers => API 

* Any call to /grahpql will be taken care by graphqlExpress
  - graphqlExpress tells express to server gql schema 
  - app route, expose to http
  
  
