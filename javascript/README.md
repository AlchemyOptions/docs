# Javascript functions available in Alchemy Options

Alchemy Options comes with some client-side helpers, available in the global `alchemyOptions` variable. Functions use the wonderful [kew](https://github.com/Medium/kew) library as a light-weight promises polyfill.

Functions have been tested in Internet Explorer 10 and newer. All modern browsers should do just fine.

## Howto

A light-weight(10Kb minified, NOT gzipped) script is registered as `alchemy-options-client-scripts`. Add it as a dependency if you want to use it, like so:

```php
wp_enqueue_script( 'my-scripts', '/path/to/my-scripts.js', array( 'alchemy-options-client-scripts' ), '1.0', true );
```

## Available functions

* [getOption](get_option.md)
* [getNetworkOption](get_network_option.md)