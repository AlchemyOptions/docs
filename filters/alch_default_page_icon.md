# alch\_default\_page\_icon

Filter `alch_default_page_icon` should be used to change the default AO options pages icon. The default value is the AO logo. The passed value should be compatible with the `$icon_url` parameter of the [`add_menu_page`](https://developer.wordpress.org/reference/functions/add_menu_page/) function.

## Example

```php
function change_default_page_icon() {
    return 'dashicons-chart-pie';
}

add_filter( 'alch_default_page_icon', 'change_default_page_icon' );
```

To modify the page icon on a per-page basis use the [alch_{ $optionsPageID }_icon](../filters/alch_%7B$optionsPageID%7D_icon.md) hook.