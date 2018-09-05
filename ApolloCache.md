# cache

https://www.apollographql.com/docs/react/advanced/caching.html

```
const cache = new InMemoryCache({
  dataIdFromObject: object => object.key || null
});
```

# cachePolicy - API bottom of doc page

https://www.apollographql.com/docs/react/api/apollo-client.html#ApolloCache
```
const defaultOptions = {
  watchQuery: {
    fetchPolicy: 'cache-and-network',
    errorPolicy: 'ignore',
  },
  query: {
    fetchPolicy: 'network-only',
    errorPolicy: 'all',
  },
};
```

Note: The React Apollo <Query /> component uses Apollo Client’s watchQuery functionality, so if you would like to set defaultOptions when using <Query />, be sure to set them under the defaultOptions.watchQuery property.

https://www.apollographql.com/docs/react/api/apollo-client.html#ApolloClient.watchQuery

```
watchQuery(options)

fetchPolicy "cache-first" | "cache-and-network" | "network-only" | "cache-only" | "no-cache" | "standby"
Specifies the FetchPolicy to be used for this query

query(options)
fetchPolicy "cache-first" | "cache-and-network" | "network-only" | "cache-only" | "no-cache" | "standby"
Specifies the FetchPolicy to be used for this query
```

# fetchPolicy
https://www.apollographql.com/docs/react/api/react-apollo.html#graphql-config-options-fetchPolicy

```
cache-first:       This is the *default* value where we always try reading data from your cache first.
cache-and-network: Regardless of whether or not the full data is in your cache this fetchPolicy will always execute query with the network interface. This fetch policy optimizes for users getting a quick response while also trying to keep cached data consistent with your server data at the cost of extra network requests.
network-only:       This fetch policy will never return you *initial* data from the cache. This fetch policy optimizes for data consistency with the server
cache-only:         This fetch policy will never execute a query using your network interface. 
no-cache:           This fetch policy will never return your initial data from the cache. Instead it will always make a request using your network interface to the server. 
```

# Pull Request with examples
https://github.com/apollographql/GitHunt-React 
https://github.com/apollographql/GitHunt-React/pull/275

# graphql + (operation) + (component) => get your data + describe which data + present your data

 
# caching w/ ```<Query/>```
https://www.apollographql.com/docs/react/advanced/caching.html#fetchMore
```
const FeedWithData = ({ match }) => (
  <Query
    query={FEED_QUERY}
    variables={{
      type: match.params.type.toUpperCase() || "TOP",
      offset: 0,
      limit: 10
    }}
    fetchPolicy="cache-and-network"
  >
    {({ data, fetchMore }) => (
      <Feed
        entries={data.feed || []}
        onLoadMore={() =>
          fetchMore({
            variables: {
              offset: data.feed.length
            },
            updateQuery: (prev, { fetchMoreResult }) => {
              if (!fetchMoreResult) return prev;
              return Object.assign({}, prev, {
                feed: [...prev.feed, ...fetchMoreResult.feed]
              });
            }
          })
        }
      />
    )}
  </Query>
);
```


# Updating React Apollo Cache
## mutate and update:
https://www.youtube.com/watch?v=uDfFkuvhnxs

# How to get updated data from apollo cache
https://stackoverflow.com/questions/50342116/how-to-get-updated-data-from-apollo-cache


# Why do we cache?
https://hackernoon.com/why-do-we-cache-b24920e1e903


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

# disable cache stack overflow

https://stackoverflow.com/questions/47879016/how-to-disable-cache-in-apollo-link-or-apollo-client
