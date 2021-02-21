# DDEV + Drupal + Gitpod.io

## Description

This library adds the required files to a DDEV-Local configured Drupal 9 site so that the site can be used with Gitpod.io.

## Instructions for use

1.  Start with a Drupal 9 site (based on the drupal/recommended-project Composer template) with a DDEV-Local configuration file, committed to a GitHub.com repository. 
1.  Add the following to the Drupal site's composer.json file "repositories" section (once this library is published on https://packagist.org, this step will no longer be necessary):

```
{
    "type": "vcs",
    "url": "https://github.com/ultimike/ddevdrupalgitpod"
}
```

1.  Add the following to the Drupal site's composer.json file "drupal-scaffold" section:

```
"allowed-packages": [
    "ultimike/ddevdrupalgitpod"
]
```

1.  `composer require ultimike/ddevdrupalgitpod:dev-main`

1.  Manually (for now) give execute permissions to the following files:

```
chmod +x .ddev/generate-fqdns.sh
chmod +x .ddev/generate-xdebug-host-ip.sh
```

1.  Commit and push all changes to GitHub.

1.  In your browser, go to https://gitpod.io/#github.com/vendor/name replacing "vendor/name" with your project vendor/name on Github.com.

1. Use `gp url 8080` in the Gitpod.io Terminal to view the Drupal site's URL.