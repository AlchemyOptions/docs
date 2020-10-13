# Email

Email field renders a text input. Uses the native `input[type="email"]`. Native client-side validation.

## Example configuration

```php
...
array(
    'title' => 'My email field title',
    'id' => 'email-option',
    'desc' => 'Short description for the field',
    'tab' => 'main',
    'type' => 'email',
),
...
```

This will produce the following

![](../.gitbook/assets/email.png)

## Params

| Name | Type | Description |
| :--- | :--- | :--- |
| `type` | string | `email` **\(required\)** |
| `id` | string | Unique ID that will be used to retrieve the value **\(required\)** |
| `tab` | string | Specifies in which tab this option will be rendered |
| `title` | string | Shows a heading to the left of the field |
| `desc` | string | Shows a description text \(can have HTML\) |

