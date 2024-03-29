# Button group

Button group field renders a set of buttons. It's a single-choice field, much like the [Radio field](radio.md). Supports initial [`checked` or `disabled` attributes](button-group.md#checked-and-disabled).

## Example configuration

```php
...
array(
    'title' => 'My button group title',
    'id' => 'button-group-option',
    'desc' => 'Short description for the field',
    'place' => array(
        'page' => 'my-options-page',
        'tab' => 'main',
    ),
    'type' => 'button_group',
    'choices' => ['First label', 'Second label', 'Third label']
),
...
```

This will produce the following

![](../.gitbook/assets/button-group-one.png)

It will use the label text as the value. If you wish to separate values from labels use the following syntax for the `choices` key:

```php
...
'choices' => array(
    array(
        'value' => 'First value',
        'label' => 'First label',
    ),
    array(
        'value' => 'Second value',
        'label' => 'Second label',
    ),
    array(
        'value' => 'Third value',
        'label' => 'Third label',
    ),
)
...
```

## `checked` and `disabled`

If `checked` or `disabled` keys are specified, they'll be respected. E.g:

```php
...
'choices' => array(
    array(
        'value' => 'First value',
        'label' => 'First label',
    ),
    array(
        'value' => 'Second value',
        'label' => 'Second label',
        'checked' => true,
    ),
    array(
        'value' => 'Third value',
        'label' => 'Third label',
        'disabled' => true,
    ),
)
...
```

will result in the following

![](../.gitbook/assets/button-group-two.png)

Notice that the second option is checked on initial page load and the third option is not clickable.

## Params

| Name | Type | Description |
| :--- | :--- | :--- |
| `type` | string | `button-group` **\(required\)** |
| `id` | string | Unique ID that will be used to retrieve the value **\(required\)** |
| `place` | array | Specifies where (page and tab) this option will be rendered |
| `title` | string | Shows a heading to the left of the field |
| `desc` | string | Shows a description text \(can have HTML\) |
| `choices` | array | Kind of required, but will not render anything if no radio choices are provided. Can be an array of strings or an array of arrays with `value` and `label` keys. See [examples](button-group.md#example-configuration) above. |

