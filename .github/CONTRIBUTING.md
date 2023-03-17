# Contributing

## Issues & Feature Requests
* Disable plugins and addon themes before opening an issue
* Use the relevant template
* Don't 'bulk report' unrelated issues in the same issue
* Don't report a new issue in the comments of an existing issue
* Check previous feature requests using the *Feature request* tag before making a new one
### Scope
The following is out of scope of this project
* Issues affecting the canary and PTB clients
* Discord in the web browser
* Features gated behind a Discord Nitro subscription (or HypeSquad membership)

## Plugin Compatibility Requests
* You may request compatibility for any plugin published on [betterdiscord.app](https://betterdiscord.app/plugins).
* Open an issue using the [template](https://github.com/TakosThings/Fluent-Discord/issues/new?assignees=&labels=better+discord%2Cplugin+compatibility&template=plugin_compat.yml&title=Plugin+name+here). 

## Pull Requests
* Major changes: Open an issue using the *Change proposal* template to discuss your changes 
* Small changes and tweaks can get away without an issue
* Clone/rebase the repo
* Make sure your editor is obeying `.editorconfig` (VS Code needs the plugin!)
* Make changes in a new branch (not develop or gh-pages)
* Submit your PR

## Development
### Environment
* Visual Studio Code
* [EditorConfig Plugin](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig) for VS Code
* Git
* Node.js

### Setup
* `npm i` to install required packages (Dart SASS and Cross-OS)

#### NPM Commands
* `npm run dev` watches files for changes and automatically builds and emits the theme to your BetterDiscord themes folder. BD will reload the theme with the changes each time.
* `npm run build-static` builds and emits a 'static' theme file to the dist directory
* `npm run build-auto` builds and emits the auto-updating theme file. This file only contains user vars and imports the theme from GitHub.

### Comments & Debugging
* Add a comment with `TODO, NOTE, DEV, DEBUG or HACK` and the date when something needs to be explained or revisited later:
  ```SCSS
  // TODO: 2021-07-01 - Find better icon
  ```
* Add the icon description when including a Fluent Icon:
  ```SCSS
  content: "\F159"; // DialShape4
  ```
* Explain why an `!important` is being used:
  ```SCSS
  width: 32px !important; // Override in-line style
  ```
* Use `red`, `$red` or `#F00` for debugging

### Icon usage
* Avoid using the same icon for multiple purposes.
* In context menus, when an appropriate icon isn't available set the icon to `\E9CE` (Unknown) and add `visibility: hidden;` This will provide the correct spacing to indent the item label and hides the icon.

### Plugin Compatibility
Use the [Plugin Compatibility Request](https://github.com/TakosThings/Fluent-Discord/issues/new?assignees=&labels=better+discord%2Cplugin+compatibility&template=plugin_compat.yml&title=Plugin+name+here) issue template to request compatibility for a plugin. The plugin __must__ be approved on [betterdiscord.app](https://betterdiscord.app)

If you are interested in creating a PR for a plugin use the following formatting:
* Create a new file in `src/modules/betterdiscord/plugins` with the following formatting: `_GitHubUsername.PluginName.scss`. Note the underscore at the start of the filename. Capitalisation should also match the username and plugin name. Example: `_TakosThings.FluentDiscord.scss`
* Add an import to `src/modules/betterdiscord/_plugin_compat.scss` with the following formatting:
```SCSS
// https://betterdiscord.app/plugin/PluginName
@import "_GitHubUsername.PluginName.scss";
```
