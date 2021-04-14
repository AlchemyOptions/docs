# alch\_{ $optionsPageID }\_capabilities

Dynamic filter `alch_{ $optionsPageID }_capabilities` should be used to change the capabilities parameter for the page with a specific ID. The default value is returned with the [alch_default_page_capabilities](../filters/alch_default_page_capabilities.md) hook.

## Example

We have an AO options page with the `id` of `my-options-page`, the code should look as follows:

```php
function change_my_options_page_capabilities() {
    return 'edit_alchemy_options';
}

add_filter( 'alch_my-options-page_capabilities', 'change_my_options_page_capabilities' );
```