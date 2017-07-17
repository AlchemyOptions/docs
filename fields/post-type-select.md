# Post Type Select Field

Post type select field renders a searchable [Select 2](https://select2.github.io/) field that will provide a list of post type titles when a user has typed at least two characters (the values will be loaded dynamically). Similar to the [Datalist](datalist.md) field. Supports [multiple choice](#multiple-choice).

## Description

The field uses [AJAX](https://developer.mozilla.org/en/docs/AJAX) to load the values dynamically, so depending on your configuration, there may be some latency before the results are presented to the user. Uses the [Search Parameter](https://codex.wordpress.org/Class_Reference/WP_Query#Search_Parameter) of the `WP_Query` class on the back end.
 
## Example configuration

```php
...
array(
    'title' => 'My post type select field title',
    'id' => 'post-type-select-option',
    'desc' => 'Short description for the field',
    'tab' => 'main',
    'post-type' => 'page',
    'type' => 'post-type-select',
),
...
```

This will produce the following

![](../assets/post-type-select-one.png)

## Multiple choice

if `'multiple' => true` is added to the [configuration object](#example-configuration), the field will respect it. The following configuration

```php
...
array(
    'title' => 'My post type select field title',
    'id' => 'post-type-select-option',
    'desc' => 'Short description for the field',
    'tab' => 'main',
    'post-type' => 'page',
    'multiple' => true,
    'type' => 'post-type-select',
),
...
```

will result in the following

![](../assets/post-type-select-two.png)

## Params

| Name | Type | Description |
| --- | --- | --- |
| `type` | string | `post-type-select` **(required)**
| `id` | string | Unique ID that will be used to retrieve the value **(required)**
| `tab` | string | Specifies in which tab this option will be rendered
| `title` | string | Shows a heading to the left of the field
| `desc` | string | Shows a description text (can have HTML)
| `multiple` | boolean | Set to `true` if multiple values are needed. See [an example](#multiple-choice) above.
| `post-type` | string | Post type (standard or custom) to search for. If not specified, searches in `post`.