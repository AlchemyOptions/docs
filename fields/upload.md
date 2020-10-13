# Image upload

Upload field renders an Add media button. Clicking it opens the standard Select or Upload Media dialogue and will render the `thumbnail` size of the selected image. Clicking the Trash button resets the field.

## Example configuration

```php
...
array(
    'title' => 'My upload field title',
    'id' => 'upload-option',
    'desc' => 'Short description for the field',
    'tab' => 'main',
    'type' => 'upload',
),
...
```

This will produce the following

![](../.gitbook/assets/upload.png)

## Params

| Name | Type | Description |
| :--- | :--- | :--- |
| `type` | string | `upload` **\(required\)** |
| `id` | string | Unique ID that will be used to retrieve the value **\(required\)** |
| `tab` | string | Specifies in which tab this option will be rendered |
| `title` | string | Shows a heading to the left of the field |
| `desc` | string | Shows a description text \(can have HTML\) |

