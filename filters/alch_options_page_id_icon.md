# alch\_{ $optionsPageID }\_icon

Dynamic filter `alch_{ $optionsPageID }_icon` should be used to change the icon for the page with a specific ID. The default value is returned with the [alch_default_page_icon](../filters/alch_default_page_icon.md) hook. The passed value should be compatible with the `$icon_url` parameter of the [`add_menu_page`](https://developer.wordpress.org/reference/functions/add_menu_page/) function.

## Example

We have an AO options page with the `id` of `my-options-page`, the code should look as follows:

```php
function change_my_options_page_icon() {
    return 'dashicons-chart-pie';
}

add_filter( 'alch_my-options-page_icon', 'change_my_options_page_icon' );
```