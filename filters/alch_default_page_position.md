# alch\_default\_page\_position

Filter `alch_default_page_position` should be used to change the default AO options pages position parameter. The default value is `60` (after the Appearance section).

## Example

```php
function change_default_page_position() {
    return 20;
}

add_filter( 'alch_default_page_position', 'change_default_page_position' );
```

To modify the page position parameter on a per-page basis use the [alch_{ $optionsPageID }_position](../filters/alch_%7B$optionsPageID%7D_position.md) hook.