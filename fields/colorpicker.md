# Colorpicker

Colorpicker field renders a simple text input which shows a default [Iris Colorpicker](http://automattic.github.io/Iris/) on input focus, current color sample and a button to clear the color.

## Example configuration

```php
...
array(
    'title' => 'My colorpicker field title',
    'id' => 'colorpicker-option',
    'desc' => 'Short description for the field',
    'tab' => 'main',
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
| `tab` | string | Specifies in which tab this option will be rendered |
| `title` | string | Shows a heading to the left of the field |
| `desc` | string | Shows a description text \(can have HTML\) |

