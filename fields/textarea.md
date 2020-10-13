# Textarea

Textarea field renders a textarea.

## Example configuration

```php
...
array(
    'title' => 'My textarea field title',
    'id' => 'textarea-option',
    'desc' => 'Short description for the field',
    'tab' => 'main',
    'type' => 'textarea',
),
...
```

This will produce the following

![](../.gitbook/assets/textarea.png)

## Params

| Name | Type | Description |
| :--- | :--- | :--- |
| `type` | string | `textarea` **\(required\)** |
| `id` | string | Unique ID that will be used to retrieve the value **\(required\)** |
| `tab` | string | Specifies in which tab this option will be rendered. |
| `title` | string | Shows a heading to the left of the field |
| `desc` | string | Shows a description text \(can have HTML\) |

