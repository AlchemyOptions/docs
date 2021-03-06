# getOption

Function `getOption` allows you to get the saved value of an option. Uses [kew](https://github.com/Medium/kew) as a promises polyfill.

For server-side use [alch\_get\_option](../functions/alch_get_option.md).

Enqueue a script and [add `alchemy-options-client-scripts` as its dependency](./). This will give you the global `alchemyOptions` variable.

## Example usage

```javascript
alchemyOptions
    .getOption('my-option-id')
    .then(value => {
        //value is a JSON string like {"success":true,"data":42}
    });
```

`getOption` returns the kew defer, so you can deal with the promise later.

```javascript
const myOption = alchemyOptions.getOption('my-option-id');

//later in the code
myOption.promise.then(value => {
    // do something with the value
});
```

If for some reason `getOption` fails, you can deal with it in the `fail` method. It can happen if the AJAX request errored or was aborted.

```javascript
alchemyOptions
    .getOption('my-option')
    .then(value => {
        // value is a JSON string like {"success":true,"data":42}
    })
    .fail(response => {
        // failed to get the value
    });
```

More info can be found in the [kew documentation](https://github.com/Medium/kew#how-do-i-use-kew).

## Note on passing non-existent IDs

Most of the time `getOption` will be successful, even if you pass non-existent ID to it. Consider the following example:

```javascript
alchemyOptions
    .getOption('some-non-existent-option')
    .then(value => {
        // value is a JSON string like {"success":true,"data":""}
    })
```

If you pass the option ID that doesn't exist, the call will still be successful, the `data` property will be an empty string.

## Params

| Name | Type | Description |
| :--- | :--- | :--- |
| `id` | string | Unique ID that will be used to retrieve the value **\(required\)** |

