# alch\_delete\_value

Function `alch_delete_value` sets `''` \(empty string\) as the value for a given `$optionID`. Technically it's not deletion, it's an update, but still :\)

## Parameters

The function takes `$optionID` as a parameter. `$optionID` should match the `id` of some field in the main [configuration object](https://github.com/alchemyoptions/alchemy-options-docs/tree/8b2bf3bd7ce84655c638f5207b00fe1902d575b8/functions/Configuration.md).

## Return values

Returns a `boolean`: `True` if option value has changed, `false` if not or if update failed.

## Example

```php
    $optionUpdated = alch_delete_value( 'field-id' );
```

If `field-id` had a value other than an empty string before calling `alch_delete_value`, `$optionUpdated` will be `true`.

