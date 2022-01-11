# Contributing

## Issues & Feature Requests
* Disable plugins and addon themes before opening an issue
* Use the relevant template
* Don't 'bulk report' unrelated issues in the same issue
* Don't report a new issue in the comments of an existing issue
* Check previous feature requests using the *Feature request* tag before making a new one

## Pull Requests
* Major changes: Open an issue using the *Change proposal* template to discuss your changes 
* Small changes and tweaks can get away without an issue
* Clone/rebase the repo
* Make sure your editor is obeying `.editorconfig` (VS Code needs the plugin!)
* Make changes in a new branch (not master)
* Submit your PR

## Development
### Environment
This assumes a Windows OS. You will need to modify the output paths in `package.json` for Mac and Linux.
* Visual Studio Code
* [Editorconfig Plugin](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig) for VS Code
* Git
* Node.js

### Setup
* `npm i sass -g` to install Dart Sass. This should be all you need to get started.

NPM Commands
* `npm run dev` watches files for changes and automatically builds and emits the theme to your BetterDiscord themes folder. BD will reload the theme with the changes each time.
* `npm run build` builds and emits the theme to the dist directory. Generally just used for building a release.
* `npm run build-translate` builds *all* the translation add-on files and emits them to the dist directory.
* `npm run dev-translate` builds *all* the translation add-on files and emits them to the BetterDiscord themes folder. You should almost never have to use this. Use the below command instead.
* `npm run dev-translate-only --lang=<languageCode>` Substitute `<languageCode>` with the language you want to emit to your BetterDiscord themes folder. Example: `npm run dev-translate-only --lang=de`. This is most useful for fixing spelling and grammar issues.

### Comments & Debugging
* Where required a code comment should start with `TODO, NOTE, DEV, DEBUG or HACK` and the date in YYYY-MM-DD format, followed by the comment: 
```CSS
// TODO: 2021-07-01 - Find better icon
```
* Including a Fluent Icon from the icon font should always inlude the description in a comment at the end of the line: 
```CSS
content: "\F159"; // DialShape4
```
* Use `red` or `#F00` for debugging
