# Config Split Recipe

## Introduction

Recipe for installing and configuring `config_split` into stackable client
environments.

## Installation

This recipe requires some manual intervention to install given the greedy
matching nature of how `config_split` is being configured in the `client_core`
split.

1. Require the recipe:
   ```composer require discoverygarden/config_split_recipe:^1```
1. Apply the recipe:
   ```php core/scripts/drupal recipe /path/to/the/recipe```
1. Unpack the recipe.
   ```composer unpack discoverygarden/config_split_recipe```
1. Override the state to disable the `client_core` split.
   ```drush csso client_core inactive```
1. Export the configuration.
   ```drush cex```
1. Remove the state override.
   ```drush csso client_core active```
1. Remove the recipe.
  ```composer remove discoverygarden/config_split_recipe```

## Troubleshooting/Issues

The `apply` recipe command will need to be run from Drupal's web root, for
`ddev` environments this will be `/var/www/html/web`.

Having problems or solved one? contact
[discoverygarden](http://support.discoverygarden.ca).

## Maintainers/Sponsors

Current maintainers:

* [discoverygarden](http://www.discoverygarden.ca)

## Development

If you would like to contribute to this module create an issue, pull request
and or contact
[discoverygarden](http://support.discoverygarden.ca).

## License

[GPLv3](http://www.gnu.org/licenses/gpl-3.0.txt)
