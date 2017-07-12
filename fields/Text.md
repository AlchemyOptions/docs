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
![gras](/assets/text.jpg)

## Params

| Name  | Required | Description |
| ------------- | ------------- | ------------- |
| `title`  | No  | If added, shows a heading to the left of the field
| `id`  | Yes  | Unique ID that will be used to retrieve the value