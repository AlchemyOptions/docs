# Colorpicker

Colorpicker field renders a simple text input which shows a default [Iris Colorpicker](http://automattic.github.io/Iris/) on input focus, current color sample and a button to clear the color.

## Example configuration

```php
...
array(
    'title' => 'My colorpicker field title',
    'id' => 'colorpicker-option',
    'desc' => 'Short description for the field',
    'place' => array(
        'page' => 'my-options-page',
        'tab' => 'main',
    ),
    'type' => 'colorpicker',
),
...
```

This will produce the following

![](../.gitbook/assets/colorpicker.png)

## Params

| Name | Type | Description |
| :--- | :--- | :--- |
| `type` | string | `colorpicker` **\(required\)** |
| `id` | string | Unique ID that will be used to retrieve the value **\(required\)** |
| `place` | array | Specifies where (page and tab) this option will be rendered |
| `title` | string | Shows a heading to the left of the field |
| `desc` | string | Shows a description text \(can have HTML\) |

