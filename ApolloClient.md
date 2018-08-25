# API bottom of doc page
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
cache-first:       This is the default value where we always try reading data from your cache first.
cache-and-network: Regardless of whether or not the full data is in your cache this fetchPolicy will always execute query with the network interface. This fetch policy optimizes for users getting a quick response while also trying to keep cached data consistent with your server data at the cost of extra network requests.
network-only:       This fetch policy will never return you *initial* data from the cache. This fetch policy optimizes for data consistency with the server
cache-only:         This fetch policy will never execute a query using your network interface. 
no-cache:           This fetch policy will never return your initial data from the cache. Instead it will always make a request using your network interface to the server. 
```

# other gql books
https://github.com/GraphQLCollege/fullstack-graphql/blob/master/manuscript/chapter-0.md

# Intro
https://www.apollographql.com/docs/react/
quickly build a UI that fetches data with GraphQL

https://codesandbox.io/s/nn9y2wzyw4
// Fetch GraphQL data with plain JS
// Fetch GraphQL data with a Query component

# get-started with a small app
https://www.apollographql.com/docs/react/essentials/get-started.html

```
// react-apollo: View layer integration for React
import { ApolloProvider } from "react-apollo";
// Uses the render prop pattern to share GraphQL data with your UI.
import { Query } from "react-apollo";


```

# Pull Request with examples
https://github.com/apollographql/GitHunt-React 
https://github.com/apollographql/GitHunt-React/pull/275

# Docs that started it all
https://www.apollographql.com/docs/react/basics/setup

```
// To create queries with need backticks ` and this package provides it
import gql from 'graphql-tag';

// snippet: you can query using apollo client but recommended way is using hoc or new Query component
const client = new ApolloClient(
client.query({ query: gql`{ hello }` }).then(console.log);

// Seems like props below are appended to the component props:
// use the graphql container to pass the query results returned by MY_QUERY
// to a component as a prop (and update them as the results change)
const MyComponentWithData = graphql(MY_QUERY)(props => <div>...</div>);
```
graphql + (operation) + (component) => get your data + describe which data + present your data

 
# react-apollo-migration to ```<Query/>```
https://www.apollographql.com/docs/react/react-apollo-migration.html
graphql(query,{}) to <Query/> hoc to component

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