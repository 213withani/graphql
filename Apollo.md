
https://www.robinwieruch.de/react-apollo-client-example/

https://blog.apollographql.com/tutorial-graphql-input-types-and-client-caching-f11fa0421cfd
Reading the Channel Name from Cache

# cache data updates
https://blog.vulcanjs.org/understanding-post-mutation-data-updates-in-apollo-43e90c37023b

# Apollo cache and server updates
https://s3.amazonaws.com/apollo-docs-1.x/receiving-updates.html
How do we make sure to update the cache if information changes on the server? How will our UI update to reflect this new information?

These are: manual refetches, polling queries and GraphQL subscriptions.


https://s3.amazonaws.com/apollo-docs-1.x/cache-updates.html

```js
// This result
{
  __typename: 'Person',
  id: '1234',
  name: 'Jonas',
}
// Will get the following ID
'Person:1234'
```

