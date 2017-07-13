# Password Field

Password field renders a text input with the unlock button. Uses the native `input[type="password"]`. Clicking the Unlock button will toggle the visibility of the entered value.
 
## Example configuration

```php
...
array(
    'title' => 'My password field title',
    'id' => 'password-option',
    'desc' => 'Short description for the field',
    'tab' => 'main',
    'type' => 'password',
),
...
```

This will produce the following

![](../assets/password.png)

## Params

| Name | Description |
| --- | --- |
| `type` | `password` **(required)**
| `id` | Unique ID that will be used to retrieve the value **(required)**
| `tab` | Specifies in which tab this option will be rendered
| `title` | Shows a heading to the left of the field
| `desc` | Shows a description text (can have HTML)