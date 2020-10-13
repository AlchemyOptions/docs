# alch\_get\_network\_option

Function `alch_get_network_option` is similar to [`alch_get_option`](alch_get_option.md). It returns the value of a saved network option.

For client-side use [getNetworkOption](../javascript/get_network_option.md).

## Parameters

The function takes `$optionID` and `$default` as parameters. `$optionID` should match the `id` of some field in the main network [configuration object](../configuration.md).

## Return values

Return value can be of several types, depending on the [type of the field](../fields/).

## Example

```php
    $myNetworkVal = alch_get_network_option( 'field-id', 'Some default value' );
```

If `field-id` has a value in the database, it will be assigned to the `$myNetworkVal` variable, otherwise, `$myNetworkVal` will be `Some default value`.

