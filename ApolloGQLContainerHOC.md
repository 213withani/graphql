# Netninja graphql(query)(component) 4hrs
https://www.youtube.com/watch?v=ed8SzALpx1Q

#26 (2:34:47)- Making Queries from React
#27 (2:42:26)- Rendering Data in a Component
#28 (2:49:23)- Add Book Component
#29 (2:59:41)- External Query File
#30 (3:04:12)- Updating Component State
#31 (3:12:35)- Composing Queries
#32 (3:24:48)- Query variables
#33 (3:31:05)- Re-fetching Queries
#34 (3:35:11)- Book Details Component
#35 (3:42:47)- Making a Single Query
#36 (3:54:13)- Styling the App

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
