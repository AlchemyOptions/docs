# alch\_network\_value\_{ $optionID }

Dynamic filter `alch_network_value_{ $optionID }` is similar to [`alch_value_{ $optionID }`](alch_value_%7B$optionID%7D.md). It is used to filter the value for a given [field](../fields/) before returning it from [`alch_get_network_option`](../functions/alch_get_network_option.md). It isn't applied to the `$default` parameter if the field has no value stored.

The `$optionID` should match one of the IDs in the [configuration object](https://github.com/alchemyoptions/alchemy-options-docs/tree/8b2bf3bd7ce84655c638f5207b00fe1902d575b8/filters/Configuration.md).

## Example

Say you want to tweak the [URL field](../fields/url.md) with the ID of `my-url-field` to convert the `http` protocol to `https`.

```php
//somewhere in functions.php

function tweak_network_url_field( $value ) {
    // do not forget to pass it further
    return str_replace( "http://", "https://", $value );
}

add_filter( 'alch_network_value_my-url-field', 'tweak_network_url_field' );
```

