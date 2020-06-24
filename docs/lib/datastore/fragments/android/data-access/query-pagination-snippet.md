```swift
// TODO convert this page from iOS to Android
Amplify.DataStore.query(Post.self, paginate: .page(0, limit: 100)) {
    // handle result
}
```

The `paginate` arguments takes an object of type [`QueryPaginationInput`](https://aws-amplify.github.io/amplify-ios/docs/Structs/QueryPaginationInput.html). That object can be created with the following factory functions:

- [`.page(_ page: UInt, limit: UInt)`](https://aws-amplify.github.io/amplify-ios/docs/Structs/QueryPaginationInput.html#/s:7Amplify20QueryPaginationInputV4page_5limitACSu_SutFZ): the page number (starting at `0`) and the page size, defined by `limit` (defaults to `100`)
- [`.firstPage`](https://aws-amplify.github.io/amplify-ios/docs/Structs/QueryPaginationInput.html#/s:7Amplify20QueryPaginationInputV9firstPageACvpZ): an idiomatic shortcut to `.page(0, limit: 100)`
- [`.firstResult`](https://aws-amplify.github.io/amplify-ios/docs/Structs/QueryPaginationInput.html#/s:7Amplify20QueryPaginationInputV11firstResultACvpZ): an idiomatic shortcut to `.page(0, limit: 1)`