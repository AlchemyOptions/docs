# Textarea Field

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

![](../assets/textarea.png)

## Params

| Name | Description |
| --- | --- |
| `type` | `textarea` **(required)**
| `id` | Unique ID that will be used to retrieve the value **(required)**
| `tab` | Specifies in which tab this option will be rendered.
| `title` | Shows a heading to the left of the field
| `desc` | Shows a description text (can have HTML)