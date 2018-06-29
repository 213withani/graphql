# graphql
Credit to this great simple and amazing article on graphql with node:
https://blog.bitsrc.io/write-graphql-apis-on-node-with-mongodb-f3d0084cbbb8

# graphql.org
a runtime [translator] for fulfilling those queries with your existing data. 

GraphQL queries always return predictable results. 

While typical REST APIs require loading from multiple URLs, GraphQL APIs get all the data your app needs in a single request.

GraphQL APIs are organized in terms of types and fields, not endpoints. Access the full capabilities of your data from a single endpoint.


Graphiql: Know exactly what data you can request from your API

Add new fields and types to your GraphQL API without impacting existing queries.

## Bring your own data and code
You provide functions for each field in the type system, and GraphQL calls them with optimal concurrency.

# Introduction to GraphQL
https://graphql.org/learn/

a server-side runtime for executing queries by using a type system you define for your data

functions for each field on each type

[Send] GraphQL queries to validate and execute

A received query is first checked to ensure it only refers to the types and fields defined, then runs the provided functions to produce a result.

# Queries and Mutations
GraphQL is about asking for specific fields on objects

fields can also refer to Objects

fetch lots of related data in one request, instead of making several roundtrips as one would need in a classic REST architecture.

GraphQL queries look the same for both single items or lists of items, however we know which one to expect based on what is indicated in the schema.

## Arguments
In a system like REST, you can only pass a single set of arguments - the query parameters and URL segments in your request.
## Aliases
you can't directly query for the same field with different arguments. That's why you need aliases - they let you rename the result of a field to anything you want.

## Fragments
reusable units called fragments. Fragments let you construct sets of fields

frequently used to split complicated application data requirements into smaller chunks

## Operation name
in JavaScript we can easily work only with anonymous functions, but when we give a function a name, it's easier to track it down, debug our code, and log when it's called. In the same way, GraphQL query and mutation names, along with fragment names, can be a useful debugging tool on the server side to identify different GraphQL requests.

## Variables
GraphQL has a first-class way to factor dynamic values out of the query, and pass them as a separate dictionary. 

## Variables definition
So if you want to pass a complex object into a field, you need to know what input type that matches on the server

## Mutations
In REST, any request might end up causing some side-effects on the server, but by convention it's suggested that one doesn't use GET requests to modify data. 

GraphQL is similar - technically any query could be implemented to cause a data write. However, it's useful to establish a convention that any operations that cause writes should be sent explicitly via a mutation.

### Multiple fields in mutations 
While query fields are executed in parallel, mutation fields run in series, one after the other.

ensuring that we don't end up with a race condition
