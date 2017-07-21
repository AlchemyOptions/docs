# alch_options_id

Function `alch_options_id` returns the filtered configuration option name.

By default, the configuration options are stored in the `alchemy_options` option. A [filter](/filters/alch_options_id.md) is available to change it.

## Parameters

The function doesn't have any parameters.

## Example

```php
    $myOptionsID = alch_options_id();
```

If no functions were executed for the `alch_options_id` filter the `$myOptionsID` variable will be `alchemy_options`.