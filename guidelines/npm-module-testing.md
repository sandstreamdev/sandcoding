# NPM module testing

## Testing app in repository

You can use your testing app and import sources (of a future module) from a local drive. An example of such a case can be found in [react-swipeable-list repository](https://github.com/sandstreamdev/react-swipeable-list).

:warning: Note that this speeds up development but you should test with one of below ways before publishing.

## `npm link`

You can use this [command](https://docs.npmjs.com/cli/link) to simluate usage of your (not yet published) module as all other modules.

```
cd ~/projects/[your_package_folder]    # go into the package directory
npm link                               # creates global link
cd ~/projects/[your_test_app]          # go into some other package directory.
npm link [your_package_name]           # link-install the package
```

Now [your_test_app] will 'see' the module and you can simply `import` it in your source code.

## Install from GitHub

If you would like to test latest package code pushed to the Github, you can install it from there.

`npm i sandstreamdev/[you_package_name]`
