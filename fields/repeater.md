# Repeater Field

Repeater field is one of the most powerful Alchemy Options fields. Alongside the [Sections](sections.md) and [Field Group](field-group.md) fields it groups fields and allows to [produce arrays of values](#return-value). Can be [sorted by drag-and-drop](#sorting). Can [temporarily remove values](#temporary-hiding) from the front end.
 
2 things were taken as the key features of a repeater:

1. [Reusability](#reusing-the-repeaters-signature) of a repeater's signature
2. Possibility to [nest repeaters](#nested-repeaters) into one another

Thus a repeater field consists of 2 parts: a) the field itself and b) its signature (like a mould for the field).

## Repeater signatures

All repeater signatures should be specified in their own `repeaters` section of the main config. Each signature is an array with [`id` and `fields` keys](#signature-params). Much like the [Field Group](field-group.md) field.

The fields themselves are added just like any other fields in the `options` part with one exception - the type of the field should be in the following format: `repeater:signatureID`.

Enough talking, let's see some code :)
 
## Example configuration

```php
...
'options' => array(
    array(
        'title' => 'My repeater field title',
        'id' => 'repeater-field',
        'desc' => 'Short description for the field',
        'type' => 'repeater:my-repeater',
        'tab' => 'homepage',
    ),
),
'repeaters' => array(
    array(
        'id' => 'my-repeater',
        'fields' => array(
            array(
                'title' => 'My content title',
                'desc' => 'Short description for the field',
                'id' => 'content',
                'type' => 'editor',
            ),
        ),
    ),
),
...
```

This will produce the following

![](../assets/repeater-one.png)

Doesn't look like much unless you click the `Add new` button which will result in the following

![](../assets/repeater-two.png)

Thus pressing the `Add new` button again and again will generate as many items (a.k.a. 'repeatees') as needed.

Note that although I've specified one field in the configuration above (which is the [Editor field](editor.md)) **2** of them are present on the screenshot. The `title` field is there by default and will show the value in the title bar of the repeatee as soon as you type something in. Repeatees would have been harder to distinguish if they weren't 'labeled'.

![](../assets/repeater-three.png)

## Sorting

Single click on the toolbar will toggle the visibility of the item, while click and drag will allow to sort

![](../assets/repeater-four.png)

You can sort 'closed' items or 'open' it doesn't matter. 

## Temporary hiding

If you hover over or expand a repeatee there's a button group that allows to delete or to temporarily hide it. If you press the `Hide` button, the repeatee's value will not be included in the return value and the item itself will indicate that it's hidden.

![](../assets/repeater-five.png)

## Reusing the repeater's signature

Since the repeaters' signatures are defined in their own `repeaters` block of the config it allows developers to reuse a repeater's signature to create several repeater fields.

E.g. the following configuration

```php
...
'options' => array(
    array(
        'title' => 'My repeater field title',
        'id' => 'repeater-field',
        'desc' => 'Short description for the field',
        'type' => 'repeater:my-repeater',
        'tab' => 'homepage',
    ),
    array(
        'title' => 'Another repeater field',
        'id' => 'repeater-field-two',
        'desc' => 'Short description for the field',
        'type' => 'repeater:my-repeater',
        'tab' => 'homepage',
    ),
),
'repeaters' => array(
    array(
        'id' => 'my-repeater',
        'fields' => array(
            array(
                'title' => 'My content title',
                'desc' => 'Short description for the field',
                'id' => 'content',
                'type' => 'editor',
            ),
        ),
    ),
),
...
```

will create two separate repeater fields with identical fields using the same signature

![](../assets/repeater-six.png)

## Nested repeaters

You can nest repeaters, make sure that the repeaters' signatures are not nested. Here's an example of a repeater inside a repeater inside a repeater (that's right - 3 levels deep)

```php
...
'options' => array(
    array(
        'title' => 'My repeater field title',
        'id' => 'repeater-field',
        'desc' => 'Short description for the field',
        'type' => 'repeater:my-repeater',
        'tab' => 'homepage',
    ),
),
'repeaters' => array(
    array(
        'id' => 'my-repeater',
        'fields' => array(
            array(
                'title' => 'My upload title',
                'id' => 'upload',
                'desc' => 'Short description for the field',
                'type' => 'repeater:upload-repeater',
            ),
        ),
    ),
    array(
        'id' => 'upload-repeater',
        'fields' => array(
            array(
                'title' => 'My upload title',
                'desc' => 'Short description for the field',
                'id' => 'upload',
                'type' => 'upload',
            ),
            array(
                'title' => 'My select title',
                'id' => 'checks',
                'desc' => 'Short description for the field',
                'type' => 'repeater:select-repeater',
            ),
        ),
    ),
    array(
        'id' => 'select-repeater',
        'fields' => array(
            array(
                'title' => 'My upload title',
                'desc' => 'Short description for the field',
                'id' => 'select',
                'type' => 'select',
                'choices' => ['Label one', 'Label two', 'Label three']
            ),
        ),
    ),
),
...
```

![](../assets/repeater-seven.png)

Note that all 3 different signatures are top level (not nested) but the `fields` part reference them. Thus creating the needed nesting.

## Params

| Name | Type | Description |
| --- | --- | --- |
| `type` | string | `repeater:signatureID`. [Signature ID](#repeater-signatures) should match one from the `repeaters` part of the config. **(required)**
| `id` | string | Unique ID that will be used to retrieve the value **(required)**
| `tab` | string | Specifies in which tab this option will be rendered
| `title` | string | Shows a heading to the left of the field
| `desc` | string | Shows a description text (can have HTML)

## Signature params

| Name | Type | Description |
| --- | --- | --- |
| `id` | string | Unique ID that will be used in the `type` parameter of the field **(required)**
| `fields` | array | Array of fields usual configurations. Can have [nested repeater fields](#nested-repeaters). **(required)**

## Return value

Repeater field returns an array of associative arrays where array keys are the signature's fields IDs. The results will not include the [hidden repeatees](#temporary-hiding).

A nested sample config above may return something as follows:

```php
Array
(
    [0] => Array
        (
            [title] => Level one
            [upload] => Array
                (
                    [0] => Array
                        (
                            [title] => Level two
                            [upload] =>
                            [checks] => Array
                                (
                                    [0] => Array
                                        (
                                            [title] => Level three
                                            [select] => Label one
                                        )
                                )
                        )
                )
        )
    [1] => Array
        (
            [title] => Another field
            [upload] => Array
                (
                )
        )
)
```