![saplings](https://github.com/kanopi/saplings/assets/5177009/a6377e32-deb2-49d8-873a-f3dd5a36fa7c)

# Saplings - Demo Content Recipe

This recipe provides content for a demo site using the Saplings recipe.

## How it was created.

We used the Default Content module to export content we created on a local
environment.  The Default Content module should only be used as a `--dev`
module. It is not needed in production.

To apply the recipe, you can use the php script, or in drush 13+, you can use
`drush recipe`

## Instructions to use the Default Content module to create a recipe.

Require the module in dev. We don't need it in production.
`fin composer require --dev 'drupal/default_content:^2.0@alpha'`

Enable the module.
`fin drush en -y default_content`

Export all nodes and dependencies.
`dcer` gets all the dependencies of the entity you are exporting.
`fin drush dcer node --folder=recipes/saplings-content/content`

Export all Menu links.
`fin drush dcer menu_link_content --folder=recipes/saplings-content/content`

All all taxonomy terms.
`fin drush dcer taxonomy_term --folder=recipes/saplings-content/content`

You can add an ID or bundle to each if you want to limit.
`fin drush dcer menu_link_content 42 --folder=recipes/saplings-content/content`

Disable the module when done.
`fin drush pmu -y default_content`
