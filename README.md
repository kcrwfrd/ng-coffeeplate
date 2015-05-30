# ng-coffeeplate
ng-coffeeplate is an Angular project boilerplate and Gulp.js build system. It features

* [CoffeeScript](http://coffeescript.org/) linting, transpilation, concatenation, and minification
* Vendor asset management, courtesy of [Bower](http://bower.io/)
* [Jade](http://jade-lang.com/) template compilation (cached as an Angular module)
* [SASS](http://sass-lang.com/) stylesheet compilation
* [Bootstrap](http://getbootstrap.com/), imported as a SASS module, giving you full access to mixins and configuration options.
* [Karma test runner](http://karma-runner.github.io/0.12/index.html) + the [Jasmine test assertion library](http://jasmine.github.io/)
* Static webserver with [LiveReload](http://livereload.com/)

# Getting Started

```bash
# Clone the repo
git clone git@github.com:kvcrawford/ng-coffeeplate.git
cd ng-coffeeplate

# Install dependencies
npm install
bower install

# Note: if you haven't already, you'll need to install
# Gulp globally to use the CLI.
npm install --global gulp

# And start developing!
gulp
```

Each Gulp task is defined in its own file within `lib/gulp`.

The default task builds the app, launches a web server at [http://localhost:4040/](http://localhost:4040/), and runs the test suite. It will then rebuild the app and re-run the test suite any time a file is changed.

Vendor scripts are managed by Bower. To add a new one, you must specify the path in `lib/gulp/vendor.coffee` for their concatenation into a single `vendor.js` file.

# App Organization
All templates and CoffeeScript files are located in `src/`, with the main template in `src/index.jade`. SASS stylesheets are in `styles/`.

It is recommended that the app be broken up into folders by feature. For example,

```
|-- src
  |-- post
    |-- controller
      |-- post-edit-controller.coffee
      |-- post-list-controller.coffee
    |-- directive
      |-- post-component-directive.coffee
    |-- service
      |-- post-service.coffee
    |-- model
      |-- post-model.coffee
      |-- post-collection.coffee
    |-- test
      |-- post-model.spec.coffee
      |-- post-collection.spec.coffee
      |-- post-service.spec.coffee
      |-- post-controller.spec.coffee
    |-- _post-component.jade
    |-- post.coffee
    |-- post-edit.jade
    |-- post-list.jade
```
