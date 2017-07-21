# alch_get_network_option

Function `alch_get_network_option` is similar to [`alch_get_option`](alch_get_option.md). It returns the value of a saved network option.

## Parameters

The function takes `$optionID` and `$default` as parameters. `$optionID` should match the `id` of some field in the main network [configuration object](Configuration.md).

## Return values

Return value can be of several types, depending on the [type of the field](/fields/README.md).

## Example

```php
    $myNetworkVal = alch_get_network_option( 'field-id', 'Some default value' );
```

If `field-id` has a value in the database, it will be assigned to the `$myNetworkVal` variable, otherwise, `$myNetworkVal` will be `Some default value`.