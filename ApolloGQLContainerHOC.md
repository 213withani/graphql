# introduction-to-apollo gql hoc 2018

https://flaviocopes.com/apollo/#introduction-to-apollo

```
const App = graphql(POPULAR_REPOSITORIES_LIST)(props =>
  <ul>
    {props.data.loading ? '' : props.data.search.edges.map((row, i) =>
      <li key={row.node.owner.login + '-' + row.node.name}>
        {row.node.owner.login} / {row.node.name}: {' '}
        <strong>
          {row.node.stargazers.totalCount}
        </strong>
      </li>
    )}
  </ul>
)

export default App
```
