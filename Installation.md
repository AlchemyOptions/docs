# How to install Alchemy Options

Alchemy Options can be used as a plugin and can be included into the theme.

## Using Alchemy Options as a plugin

1. download the [zip file of the plugin](https://github.com/AlchemyOptions/AlchemyOptions/raw/master/dist/alchemy-options.zip)
2. go to the *Add New* plugin page of your WordPress site
3. click the *Upload Plugin* button which will bring you a file input
4. choose the zip-file you've downloaded and press *Install Now*
5. activate Alchemy Options

### Installing via WP-CLI

You can install (and activate) Alchemy Options via WP-CLI, like so:

`wp plugin install https://github.com/AlchemyOptions/AlchemyOptions/raw/master/dist/alchemy-options.zip --activate`

## Using Alchemy Options in your theme

1. manually download the [zip file of the plugin](https://github.com/AlchemyOptions/AlchemyOptions/raw/master/dist/alchemy-options.zip)
2. unpack the archive
3. add the `alchemy-options` folder to your theme
4. add the following code at the top of your `functions.php` (without any hooks)

```php
define( 'ALCHEMY_OPTIONS_THEME_MODE', '__return_true' );

// you may want to correct the path if it's not in the root of the theme
require_once( get_stylesheet_directory() . '/alchemy-options/alchemy-options.php' );
```

**Note**. Make sure you do not rename the `alchemy-options` folder, otherwise it's not going to work, since Alchemy Options files rely on this folder name.

## Cannot redeclare Alchemy_Options\alch_run_plugin

If you see the `Cannot redeclare Alchemy_Options\alch_run_plugin` error, it means that Alchemy Options is already loaded. Make sure you do not load it in 2 places, as a plugin and as part of your theme.

The same error will be triggered if you try to activate it as a plugin having already loaded it as part of a theme.

After the installation you are ready to [configure it](Configuration.md) in your theme. Sample [configuration examples](Samples.md) are also available.