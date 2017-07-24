# alch_allowed_editor_protocols

Filter `alch_allowed_editor_protocols` can be used to change the default protocols that are allowed in the [Editor](/fields/editor.md) field, which uses those returned by [`wp_allowed_protocols()`](https://developer.wordpress.org/reference/functions/wp_allowed_protocols/) as a default value.

This filter is applied just before saving the value to the database.

## Example

Say we want our Editor fields to allow _only_ `https` protocol

```php
function change_alch_allowed_editor_protocols() {
    return array( 'https' );
}

add_filter( 'alch_allowed_editor_protocols', 'change_alch_allowed_editor_protocols' );
```

In a way it is similar to the [`alch_allowed_editor_html_tags`](alch_allowed_editor_html_tags.md) filter, since both of them control what is going to be stored from the Editor field. The results of both filters are used in the [`wp_kses`](https://developer.wordpress.org/reference/functions/wp_kses/) before storing the value.
