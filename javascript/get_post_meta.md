# getPostMeta

Function `getPostMeta` allows you to get the saved post meta value by passing `postID` and `metaID` parameters. Uses [kew](https://github.com/Medium/kew) as a promises polyfill.
 
Enqueue a script and [add `alchemy-options-client-scripts` as its dependency](README.md). This will give you the global `alchemyOptions` variable.
 
## Example usage

```javascript
alchemyOptions
    .getPostMeta(42, 'my-meta-id')
    .then(value => {
        //value is a JSON string like {"success":true,"data":42}
    });
```

`getPostMeta` returns the kew defer, so you can deal with the promise later.

```javascript
const myMeta = alchemyOptions.getPostMeta(42, 'my-meta-id');

//later in the code
myMeta.promise.then(value => {
    // do something with the value
});
```

If for some reason `getPostMeta` fails, you can deal with it in the `fail` method. It can happen if the AJAX request errored or was aborted.

```javascript
alchemyOptions
    .getPostMeta(42, 'my-meta-id')
    .then(value => {
        // value is a JSON string like {"success":true,"data":42}
    })
    .fail(response => {
        // failed to get the value
    });
```

More info can be found in the [kew documentation](https://github.com/Medium/kew#how-do-i-use-kew).

## Note on passing non-existent IDs 

Most of the time `getPostMeta` will be successful, even if you pass non-existent IDs to it. Consider the following example:

```javascript
alchemyOptions
    .getPostMeta(121465413561, 'some-meta-id') // ID of a post that doesn't exist
    .then(value => {
        // value is a JSON string like {"success":true,"data":""}
    })
```

If you pass the ID of a post that doesn't exist, the call will still be successful, the `data` property will be an empty string.

The same thing will happen if you ask non-existent `metaID`.

## Params

| Name | Type | Description |
| --- | --- | --- |
| `postID` | number | Post ID to query for the meta **(required)**
| `metaID` | string | Post meta ID **(required)**