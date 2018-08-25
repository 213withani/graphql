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
