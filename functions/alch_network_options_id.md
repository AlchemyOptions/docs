# alch\_network\_options\_id

Function `alch_network_options_id` is similar to [`alch_options_id`](alch_options_id.md). It returns the filtered configuration option name for the network.

By default, the configuration options are stored in the `alchemy_network_options` option. A [filter](../filters/alch_network_options_id.md) is available to change it.

## Parameters

The function doesn't have any parameters.

## Example

```php
    $myNetworkOptionsID = alch_network_options_id();
```

If no functions were executed for the `alch_network_options_id` filter the `$myNetworkOptionsID` variable will be `alchemy_network_options`.

