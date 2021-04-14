# alch\_value\_{ $optionID }

Dynamic filter `alch_value_{ $optionID }` is used to filter the value for a given [field](../fields/) before returning it from [`alch_get_option`](../functions/alch_get_option.md). It isn't applied to the `$default` parameter if the field has no value stored.

The `$optionID` should match one of the IDs in the [configuration object](../configuration.md).

## Example

Say you want to tweak the [URL field](../fields/url.md) with the ID of `my-url-field` to convert the `http` protocol to `https`.

```php
//somewhere in functions.php

function tweak_url_field( $value ) {
    // do not forget to pass it further
    return str_replace( "http://", "https://", $value );
}

add_filter( 'alch_value_my-url-field', 'tweak_url_field' );
```

