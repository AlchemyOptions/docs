# alch_delete_value

Function `alch_delete_value` sets `''` (empty string) as the value for a given `$optionID`. Technically it's not deletion, it's an update, but still :)

## Parameters

The function takes `$optionID` as a parameter. `$optionID` should match the `id` of some field in the main [configuration object](Configuration.md).

## Return values

Returns a `boolean`: `True` if option value has changed, `false` if not or if update failed.

## Example

```php
    $optionUpdated = alch_delete_value( 'field-id' );
```

If `field-id` had a value other than an empty string before calling `alch_delete_value`, `$optionUpdated` will be `true`.