# Text Field

Text field renders a simple text input.
 
## Example configuration

```php
...
array(
    'title' => 'My text field title',
    'id' => 'text-option',
    'desc' => 'Short description for the field',
    'tab' => 'main',
    'type' => 'text',
),
...
```

This will produce the following

![](../assets/text.png)

## Params

| Name | Description |
| --- | --- |
| `type` | `text` **(required)**
| `id` | Unique ID that will be used to retrieve the value **(required)**
| `tab` | Specifies in which tab this option will be rendered
| `title` | Shows a heading to the left of the field
| `desc` | Shows a description text (can have HTML)