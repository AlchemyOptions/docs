# alch\_default\_page\_capabilities

Filter `alch_default_page_capabilities` should be used to change the default AO options pages capabilities parameter. The default value is `manage_options`.

## Example

```php
function change_default_page_capabilities() {
    return 'edit_alchemy_options';
}

add_filter( 'alch_default_page_capabilities', 'change_default_page_capabilities' );
```

To modify the page capabilities parameter on a per-page basis use the [alch_{ $optionsPageID }_capabilities](../filters/alch_options_page_id_capabilities.md) hook.