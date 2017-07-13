# URL Field

URL field renders a text input. Uses the native `input[type="url"]`.
 
## Example configuration

```php
...
array(
    'title' => 'My URL field title',
    'id' => 'url-option',
    'desc' => 'Short description for the field',
    'tab' => 'main',
    'type' => 'url',
),
...
```

This will produce the following

![](../assets/url.png)

## Params

| Name | Type | Description |
| --- | --- | --- |
| `type` | string | `url` **(required)**
| `id` | string | Unique ID that will be used to retrieve the value **(required)**
| `tab` | string | Specifies in which tab this option will be rendered
| `title` | string | Shows a heading to the left of the field
| `desc` | string | Shows a description text (can have HTML)