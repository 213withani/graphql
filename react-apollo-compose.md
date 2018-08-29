# compose.md
https://www.apollographql.com/docs/react/api/react-apollo.html#compose

* several component enhancers at once
* cleans up code
* 
```compose(funcC, funcB, funcA)(component) => funcC(funcB(funcA(component)))```
