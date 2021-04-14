# alch\_{ $optionsPageID }\_position

Dynamic filter `alch_{ $optionsPageID }_position` should be used to change the position parameter for the page with a specific ID. The default value is returned with the [alch_default_page_position](../filters/alch_default_page_position.md) hook.

## Example

We have an AO options page with the `id` of `my-options-page`, the code should look as follows:

```php
function change_my_options_page_position() {
    return 20;
}

add_filter( 'alch_my-options-page_position', 'change_my_options_page_position' );
```