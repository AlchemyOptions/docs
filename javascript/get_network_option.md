# getNetworkOption

Function `getNetworkOption` is similar to [`getOption`](get_option.md). It allows you to get the saved value of a network option. Uses [kew](https://github.com/Medium/kew) as a promises polyfill.
 
Enqueue a script and [add `alchemy-options-client-scripts` as its dependency](README.md). This will give you the global `alchemyOptions` variable.
 
## Example usage

```javascript
alchemyOptions
    .getNetworkOption('my-network-option-id')
    .then(value => {
        //value is a JSON string like {"success":true,"data":42}
    });
```

`getNetworkOption` returns the kew defer, so you can deal with the promise later.

```javascript
const myOption = alchemyOptions.getNetworkOption('my-network-option-id');

//later in the code
myOption.promise.then(value => {
    // do something with the value
});
```

If for some reason `getNetworkOption` fails, you can deal with it in the `fail` method. It can happen if the AJAX request errored or was aborted.

```javascript
alchemyOptions
    .getNetworkOption('my-network-option')
    .then(value => {
        // value is a JSON string like {"success":true,"data":42}
    })
    .fail(response => {
        // failed to get the value
    });
```

More info on how to use promises can be found in the [kew documentation](https://github.com/Medium/kew#how-do-i-use-kew).

## Note on passing non-existent ID

Most of the time `getNetworkOption` will be successful, even if you pass non-existent ID to it. Consider the following example:

```javascript
alchemyOptions
    .getNetworkOption('some-non-existent-option')
    .then(value => {
        // value is a JSON string like {"success":true,"data":""}
    })
```

If you pass the option ID that doesn't exist, the call will still be successful, the `data` property will be an empty string.

## Params

| Name | Type | Description |
| --- | --- | --- |
| `id` | string | Unique ID that will be used to retrieve the value **(required)**