# alch_options_id

Filter `alch_options_id` can be used to change the default configuration option name, which is `alchemy_options`.

## Example

```php
//somewhere in functions.php

function change_default_alchemy_options_option() {
    return 'my-new-options-id';
}

add_filter( 'alch_options_id', 'change_default_alchemy_options_option' );
```

Thus, the Alchemy Options will get the new ID when it calls the [`alch_options_id` function](/functions/alch_options_id.md).