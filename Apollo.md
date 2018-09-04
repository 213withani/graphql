#  MLS apollo and less redux
https://blog.apollographql.com/reducing-our-redux-code-with-react-apollo-5091b9de9c2a

# Github PR issues apollo-client
https://github.com/apollographql/apollo-client/issues/3452#issuecomment-389601457

# A COMPLETE INTRODUCTION TO APOLLO, THE GRAPHQL TOOLKIT
https://flaviocopes.com/apollo/

# This follows our app code
https://github.com/apollographql/apollo-client/tree/master/packages/apollo-cache-inmemory#normalization

# Updating React Apollo Cache
## mutate and update:
https://www.youtube.com/watch?v=uDfFkuvhnxs

# How to get updated data from apollo cache
https://stackoverflow.com/questions/50342116/how-to-get-updated-data-from-apollo-cache

# Realtime GraphQL UI Updates in React with Apollo. (long with samples)
https://scotch.io/tutorials/realtime-graphql-ui-updates-in-react-with-apollo

# Why do we cache?
https://hackernoon.com/why-do-we-cache-b24920e1e903

# How to force-refresh a React child component: the easy way
https://medium.freecodecamp.org/force-refreshing-a-react-child-component-the-easy-way-6cdbb9e6d99c

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

# Pagination

https://s3.amazonaws.com/apollo-docs-1.x/pagination.html

# disable cache stack overflow

https://stackoverflow.com/questions/47879016/how-to-disable-cache-in-apollo-link-or-apollo-client
