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
* typeDefs: top level type
* * which queries can be sent by the client

ex. All a client can do is ask fo the greeting that returns a string value
```js
type Query {
 greeting: String
}
```

* Resolvers: process a request
* * it resolves the value of a field in this case greeting
* 
* 

* 
* 
