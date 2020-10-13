# Datepicker

Datepicker field renders a simple text input which shows a default [jQuery UI Datepicker](https://jqueryui.com/datepicker/) on input focus.

## Example configuration

```php
...
array(
    'title' => 'My datepicker field title',
    'id' => 'datepicker-option',
    'desc' => 'Short description for the field',
    'tab' => 'main',
    'type' => 'datepicker',
),
...
```

This will produce the following

![](../.gitbook/assets/datepicker.png)

## Params

| Name | Type | Description |
| :--- | :--- | :--- |
| `type` | string | `datepicker` **\(required\)** |
| `id` | string | Unique ID that will be used to retrieve the value **\(required\)** |
| `tab` | string | Specifies in which tab this option will be rendered |
| `title` | string | Shows a heading to the left of the field |
| `desc` | string | Shows a description text \(can have HTML\) |

