# Drupal Decoupled Integrations: Drupal GraphQL demo site

## Get Started

### Clone site

```bash
git clone git@github.com:octahedroid/drupal-graphql-example.git
```

### Start ddev

```bash
ddev start
```

### Install dependencies using composer

```bash
ddev composer install
```

### Install Drupal site using drush

```bash
ddev drush site:install graphql_example -y
```

### Import content using drush

Installation process takes care of importing content, but you may want to import it again, if that is your case you can use this drush command

```bash
ddev drush content:import profiles/graphql_example/assets/content.zip
```

If you are not familiar with the CLI you can visit `admin/content/import` and upload the content file located at `web/profiles/graphql_example/assets/content.zip`

### Login using drush

```bash
ddev drush uli admin
```

### Configure Simple OAuth Settings

You can reuse the previously generated Consumers at the site by visiting `admin/config/services/consumer` to edit the consumers labeled as `Viewer` & `Previewer` and assigning them a secret value.

If you prefer you can created new Consumers is this case, make sure you assign the `editor` user and the proper scope of `Viewer` & `Previewer` depending on the usage you are planing to give to each one.

> Make sure you remember the values used as secret on each Consumer because you will need them as env variables for the front-end configuration.

More info about it at this blog post [Implementing Content Previews with Drupal and Remix](https://octahedroid.com/blog/implementing-content-previews-drupal-and-remix)
