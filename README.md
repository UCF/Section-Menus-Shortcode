# Section Menus Shortcode #

Provides a shortcode that automatically generates a menu for each section on your page with a particular selector.


## Description ##

Provides a shortcode that automatically generates a menu for each section on your page with a particular selector. This menu system is meant to be used with Bootstrap 4 or the [Athena Framework](https://ucf.github.io/Athena-Framework/).

Note: jQuery is *required* for the JavaScript included with this plugin to work.  See [#Installation-Requirements](Installation Requirements) for more information.

## Installation ##

### Manual Installation ###
1. Upload the plugin files (unzipped) to the `/wp-content/plugins` directory, or install the plugin through the WordPress plugins screen directly.
2. Activate the plugin through the "Plugins" screen in WordPress

### WP CLI Installation ###
1. `$ wp plugin install --activate https://github.com/UCF/Section-Menus-Shortcode/archive/master.zip`.  See [WP-CLI Docs](http://wp-cli.org/commands/plugin/install/) for more command options.

### Github Updater Installation ###
This theme supports installation and updates via the [Github Updater plugin](https://github.com/afragen/github-updater). See their documentation for more information on setup and usage. (Requires PHP 5.6.0+)


## Changelog ##

### 1.1.0 ###
Enhancements:
* Added the ability to manually define section menu links instead of them being generated automatically via JavaScript.

  The new `[section-menu-item]` allows you to define a link within a section menu.  Links can be internal page anchors or external links.  Parameters are available for adding `rel` attributes, adjusting CSS classes on the generated `<li>` and `<a>` elements, and to open the generated link in a new window.

  Example:

  ```
  [section-menu]
  [section-menu-item href="#some-section"]Page Section Link[/section-menu-item]
  [section-menu-item a_class="..." li_class="..." href="https://www.ucf.edu/" rel="nofollow" new_window="true"]External Link[/section-menu-item]
  [/section-menu]
  ```

  Manually-defined link items will only take effect if at least one valid inner `[section-menu-item]` shortcode is present within an enclosing `[section-menu][/section-menu]` shortcode.  Otherwise, links will still be generated automatically based on existing sections on the page.

Bug Fixes:
* Fixed issue where empty section menus would still be visible at smaller screen sizes.

### 1.0.4 ###
Bug Fix:
* Updated mobile menu to close when menu item is clicked

### 1.0.3 ###
Enhancements:
* Added affix offset calculations that account for the UCF Header

Bug Fixes:
* Added fix for "jump" when the navbar affixes
* Fixed bug where two nav links could be highlighted at the same time

### 1.0.2 ###
* Added "Skip to Section" text to the mobile nav toggle button for clarity
* Fixed minor PHP notice

### 1.0.1 ###
* Updated mobile styles and bug fix

### 1.0.0 ###
* Initial release


## Upgrade Notice ##

n/a


## Installation Requirements ##

- A version of jQuery compatible with [Bootstrap 4](https://getbootstrap.com/) or the [Athena Framework](https://ucf.github.io/Athena-Framework/) is required on sites that utilize this plugin.


## Development ##

Note that compiled, minified css and js files are included within the repo.  Changes to these files should be tracked via git (so that users installing the plugin using traditional installation methods will have a working plugin out-of-the-box.)

[Enabling debug mode](https://codex.wordpress.org/Debugging_in_WordPress) in your `wp-config.php` file is recommended during development to help catch warnings and bugs.

### Requirements ###
* node
* gulp-cli

### Instructions ###
1. Clone the Section-Menus-Shortcode repo into your local development environment, within your WordPress installation's `plugins/` directory: `git clone https://github.com/UCF/Section-Menus-Shortcode.git`
2. `cd` into the new Section-Menus-Shortcode directory, and run `npm install` to install required packages for development into `node_modules/` within the repo
3. Optional: If you'd like to enable [BrowserSync](https://browsersync.io) for local development, or make other changes to this project's default gulp configuration, copy `gulp-config.template.json`, make any desired changes, and save as `gulp-config.json`.

    To enable BrowserSync, set `sync` to `true` and assign `syncTarget` the base URL of a site on your local WordPress instance that will use this plugin, such as `http://localhost/wordpress/my-site/`.  Your `syncTarget` value will vary depending on your local host setup.

    The full list of modifiable config values can be viewed in `gulpfile.js` (see `config` variable).
3. Run `gulp default` to process front-end assets.
4. If you haven't already done so, create a new WordPress site on your development environment to test this plugin against.
5. Activate this plugin on your development WordPress site.
6. Run `gulp watch` to continuously watch changes to scss and js files.  If you enabled BrowserSync in `gulp-config.json`, it will also reload your browser when plugin files change.

### Other Notes ###
* This plugin's README.md file is automatically generated. Please only make modifications to the README.txt file, and make sure the `gulp readme` command has been run before committing README changes.  See the [contributing guidelines](https://github.com/UCF/Section-Menus-Shortcode/blob/master/CONTRIBUTING.md) for more information.


## Contributing ##

Want to submit a bug report or feature request?  Check out our [contributing guidelines](https://github.com/UCF/Section-Menus-Shortcode/blob/master/CONTRIBUTING.md) for more information.  We'd love to hear from you!
