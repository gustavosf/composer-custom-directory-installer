composer-custom-directory-installer
===================================

A composer plugin, to install differenty types of composer packages in custom directories outside the default composer default installation path which is in the `vendor` folder.

Installation
------------

- Include the composer plugin into your `composer.json` `require` section::

```
  "require":{
    "php": ">=5.3",
    "gustavosf/composer-custom-directory-installer": "1.1.*",
    "fuel/core": "*",
    "fuel/email": "*",
    "fuel/parser": "*"
  }
```

- In the `extra` section define the custom directory you want to the package to be installed in::

```
  "extra":{
    "installer-paths":{
      "app/core": ["fuel/core"],
      "app/packages/{$name}": ["fuel/email", "fuel/parser"]
    }
```

 by adding the `installer-paths` part, you are telling composer to install the `monolog` package inside the `monolog` folder in your root directory.

You can rewrite or customize your destination folder depending on the vendor or the name of the package. For this, just use `{$vendor}` or `{$name}` as placeholders. In the example above, the package `fuel/email` should be installed in the path `./app/packages/email`.