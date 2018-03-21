# alch_get_post_meta

Function `alch_get_post_meta` allows you to get the saved meta value of a post.

For client-side use [getPostMeta](/javascript/get_post_meta.md).

## Parameters

The function takes `$postID`, `$metaID` and optional `$default` as parameters. `$metaID` should match the `id` of some field in the [Meta Boxes `options` array](Meta-boxes.md).

## Return values

Return value can be of several types, depending on the [type of the field](/fields/README.md).

**NB:** If the field is of [`editor`](/fields/editor.md) type, the value will not be autop'ed, make sure you wrap it in [wpautop](https://developer.wordpress.org/reference/functions/wpautop/) yourself.

## Example

### In the loop

```php
if( have_posts() ) {
    while ( have_posts() ) {
        the_post();

        $postMeta = alch_get_post_meta( get_the_ID(), 'meta-id' );
    }
}
```

### Outside the loop

```php
$postMeta = alch_get_post_meta( 42, 'meta-id' );
```

### Default value

You can pass the default value as the 3rd argument.

```php
$postMeta = alch_get_post_meta( 42, 'meta-id', 'Some default value' );
```

In this case `$postMeta` will always have a value.