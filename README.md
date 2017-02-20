# Order of the Arrow Drupal 8 Theme

[![License][license-image]][license-url]
[![built with gulp][gulp-image]][gulp-url]

The files contained in this repo are a Drupal 8 theme designed to be used by the Order of the Arrow, Boy Scouts of 
America. It is a sub-theme of the Classy base theme.

There are many techniques used by this theme to provide increased performance, accessibility, testing, and fast 
development.

## Basics

This repo includes:
* [Gulp](http://gulpjs.com) for task-running
* [Sass](http://sass-lang.com) for CSS pre-processing using libsass
* [Browser Sync](http://www.browsersync.io) for simultaneous testing on multiple browsers
* [Pattern Lab](http://patternlab.io) for designing in the browser and creating a living style guide

## Getting started

Before getting started, make sure that you have the latest version of [node.js](https://nodejs.org) and 
[yeoman](http://yeoman.io) installed. It is preferred to install node via [n](https://www.npmjs.com/package/n) 
using `curl -L http://git.io/n-install | bash`.  

Also, you will need to have [composer](https://getcomposer.org/doc/00-intro.md) installed. On a Mac, this is easiest 
with [homebrew](http://brew.sh/).

The OA theme needs the [**Components Libraries**](https://www.drupal.org/project/components) module to run. You must 
install it prior to enabling the theme. Additionally, you will need to enable both the **search** and 
**responsive image** modules (these two ship with core but need to be enabled) before installing the theme.

When ready to work, refer to [Gulp tasks for front-end development](docs/gulp.md) to get started.

## Installation Instructions

We are assuming here you have already installed Drupal 8 and it is running on your development server. To begin 
installing this theme, navigate to the themes directory (`cd themes`). If you wish, you can add a new directory for 
your custom themes (`mkdir custom && cd custom`).

Now install the theme files using: 

```bash
git clone https://github.com/oabsa/oabsa-theme.git oabsa_theme
```

Change directories to where your put your theme.

```bash
cd oabsa_theme
```

Edit line 1 of `gulpfile.js`, replacing `your-site.tld` with the domain of your local site.

Now install all of the Node.js modules we need. (This will take a while.)

```bash
npm install
```

Finally, set up Pattern Lab.

```bash
gulp generate-pattern-lab
```

You're now ready to visit your Drupal site and enable the new theme.

## Post-installation Notes

Running `npm install` and `gulp install` will add several files in directories called node_modules. The .gitignore file 
in your theme will prevent these files from being added to your repo. This is intentional because the files are only 
needed for development. 

If you are adding developers on a team who are editing the theme, after they have cloned your site's repo they will 
need to navigate to the theme directory and run these commands:

```bash
npm install
```
As well as either
```bash
gulp generate-pattern-lab
```
or
```bash
gulp build-dev
```

## Documentation

1. [Enabling dev mode](docs/dev_mode.md) in Drupal 8 to provide template suggestions and disabling the cache
1. [Gulp tasks for front-end development](docs/gulp.md)
    - [Building CSS](docs/gulp.md#building-css)
    - [Adding Google Fonts](docs/gulp.md#adding-google-fonts)
    - [Generating fav/app icons](docs/gulp.md#generating-favicons)
    - [Visual regression testing](docs/gulp.md#visual-regression-testing)
1. [Renaming the theme files and its functions](docs/rename.md)
1. [Using Pattern Lab](docs/pattern_lab.md)
    - [Generate Pattern Lab files](docs/pattern_lab.md#generate-pattern-lab-files)
    - [Watching Pattern Lab](docs/pattern_lab.md#watching-pattern-lab)
    - [Generate a new pattern](docs/pattern_lab.md#generate-a-pattern)
1. [Inheritance in Pattern Lab](docs/pattern_lab_inheritance.md) (this applies to inheritance in Twig too)
1. [Bower for front-end plugins](docs/bower.md)
    - [Serving location of Bower files](docs/bower.md#serving-location-of-bower-files)
    - [Forcing usage of specific files from Bower](docs/bower.md#forcing-usage-of-specific-files-from-bower)
1. [Using Probo.CI](docs/probo.md)
    - [Linting with Probo](docs/probo.md#linting-with-probo)
1. [Sass Structure](docs/sass.md)
1. [Local Google Fonts](docs/local_google_fonts.md)

