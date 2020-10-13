# alch\_allowed\_editor\_html\_tags

Filter `alch_allowed_editor_html_tags` can be used to change the default HTML tags that are allowed in the [Editor](../fields/editor.md) field, which uses the `global $allowedposttags;` as a default value.

Consider taking a look at `[wordpress directory]/wp-includes/kses.php` to see what `$allowedposttags` really is.

This filter is applied just before saving the value to the database.

## Example

Say we want our Editor fields to allow _only_ `<p>` and `<strong>` tags which in their turn may only have the `class` attribute

```php
function change_alchemy_options_editor_html_tags() {
    return array(
        'p' => array(
            'class' => true,
        ),
        'strong' => array(
             'class' => true,
         ),
    );
}

add_filter( 'alch_allowed_editor_html_tags', 'change_alchemy_options_editor_html_tags' );
```

Or you can take the passed `$tags` argument and correct it to your needs. Say we don't want any attributes on `h1` tags and leave the rest as defaults

```php
function change_alchemy_options_editor_html_tags( $tags ) {
    $tags['h1'] = array(); // no attributes for the `h1` tag will be allowed

    // do not forget to pass them further
    return $tags;
}

add_filter( 'alch_allowed_editor_html_tags', 'change_alchemy_options_editor_html_tags' );
```

