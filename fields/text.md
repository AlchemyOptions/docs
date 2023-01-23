# Text

Text field renders a simple text input.

## Example configuration

```php
...
array(
    'title' => 'My text field title',
    'id' => 'text-option',
    'desc' => 'Short description for the field',
    'type' => 'text',
    'place' => array(
        'page' => 'my-options-page',
        'tab' => 'main',
    ),
),
...
```

This will produce the following

![](../.gitbook/assets/text.png)

## Params

| Name | Type | Description |
| :--- | :--- | :--- |
| `type` | string | `text` **\(required\)** |
| `id` | string | Unique ID that will be used to retrieve the value **\(required\)** |
| `place` | array | Specifies where (page and tab) this option will be rendered |
| `title` | string | Shows a heading to the left of the field |
| `desc` | string | Shows a description text \(can have HTML\) |

