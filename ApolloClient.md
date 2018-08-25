
# Docs that started it all
https://www.apollographql.com/docs/react/basics/setup

```
// To create queries with need backticks ` and this package provides it
import gql from 'graphql-tag';

// snippet: you can query using apollo client but recommended way is using hoc or new Query component
const client = new ApolloClient(
client.query({ query: gql`{ hello }` }).then(console.log);
```

 
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
