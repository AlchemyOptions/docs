# Datalist Field

Datalist field renders a searchable [Select 2](https://select2.github.io/) field. Handy when the number of options is rather big (e.g. A list of countries in a regular [Select field](select.md) may arguably not be a good UX). Supports [multiple choice](#multiple-choice).
 
## Example configuration

```php
...
array(
    'title' => 'My datalist field title',
    'id' => 'first-datalist-option',
    'desc' => 'Short description for the field',
    'tab' => 'main',
    'type' => 'datalist',
    'options' => array(
        array(
            'name' => 'Name one',
            'value' => 'Value one',
        ),
        array(
            'name' => 'Name two',
            'value' => 'Value two',
        ),
        array(
            'name' => 'Name three',
            'value' => 'Value three',
        ),
    ),
),
...
```

This will produce the following

![](../assets/datalist-one.png)

## Multiple choice

if `'multiple' => true` is added to the [configuration object](#example-configuration), the field will respect it. The following configuration

```php
...
array(
    'title' => 'My datalist field title',
    'id' => 'first-datalist-option',
    'desc' => 'Short description for the field',
    'tab' => 'main',
    'multiple' => true,
    'type' => 'datalist',
    'options' => array(
        array(
            'name' => 'Name one',
            'value' => 'Value one',
        ),
        array(
            'name' => 'Name two',
            'value' => 'Value two',
        ),
        array(
            'name' => 'Name three',
            'value' => 'Value three',
        ),
    ),
),
...
```

will result in the following

![](../assets/datalist-two.png)

## Params

| Name | Type | Description |
| --- | --- | --- |
| `type` | string | `datalist` **(required)**
| `id` | string | Unique ID that will be used to retrieve the value **(required)**
| `tab` | string | Specifies in which tab this option will be rendered
| `title` | string | Shows a heading to the left of the field
| `desc` | string | Shows a description text (can have HTML)
| `multiple` | boolean | Set to `true` if multiple values are needed. See [an example](#multiple-choice) above.
| `options` | array | Array of arrays with `value` and `name` keys. See [examples](#example-configuration) above.