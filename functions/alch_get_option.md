# alch_get_option

Function `alch_get_option` returns the value of a saved option.

## Parameters

The function takes `$optionID` and `$default` as parameters. `$optionID` should match the `id` of some field in the main [configuration object](Configuration.md).

## Return values

Return value can be of several types, depending on the [type of the field](/fields/README.md).

## Example

```php
    $myVal = alch_get_option( 'field-id', 'Some default value' );
```

If `field-id` has a value in the database, it will be assigned to the `$myVal` variable, otherwise, `$myVal` will be `Some default value`.