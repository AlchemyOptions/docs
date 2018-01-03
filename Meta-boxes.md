# Usage in Meta Boxes

Alchemy Options fields can be used in [Meta Boxes](https://developer.wordpress.org/plugins/metadata/custom-meta-boxes/). Please take a look at the following configuration example.

```php
function add_custom_meta_boxes() {
    $meta_boxes = array(
        array(
            'id' => 'meta_box',
            'title' => 'Meta box title',
            'post-types' => array( 'page' ),
            'meta' => array(
                'options' => array(),
            ),
        ),
    );

    foreach ( $meta_boxes as $meta_box ) {
        new Alchemy_Options\Includes\Meta_Box( $meta_box );
    }
}

add_action( 'admin_init', 'add_custom_meta_boxes' );
```

## Params

| Name | Type | Description |
| --- | --- | --- |
| `id` | string | Unique ID **(required)**
| `title` | string | Shows a heading on the meta box **(required)**
| `post-types` | array | A list of post types where this meta box should appear **(required)**
| `meta` | array | A list of meta options. Should have the `options` array containing regular options signatures **(required)**