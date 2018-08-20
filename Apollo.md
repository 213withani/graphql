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
