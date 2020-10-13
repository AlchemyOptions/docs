# Tel

Tel field renders a text input. Uses the native `input[type="tel"]`.

## Example configuration

```php
...
array(
    'title' => 'My tel field title',
    'id' => 'tel-option',
    'desc' => 'Short description for the field',
    'tab' => 'main',
    'type' => 'tel',
),
...
```

This will produce the following

![](../.gitbook/assets/tel.png)

## Params

| Name | Type | Description |
| :--- | :--- | :--- |
| `type` | string | `tel` **\(required\)** |
| `id` | string | Unique ID that will be used to retrieve the value **\(required\)** |
| `tab` | string | Specifies in which tab this option will be rendered |
| `title` | string | Shows a heading to the left of the field |
| `desc` | string | Shows a description text \(can have HTML\) |

