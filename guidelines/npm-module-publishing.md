# NPM module publishing

Before publishing module update `package.json` and fill following fields as specified.

## Required fields to fill in package.json

Fill following fields:

#### name

Use following format `@sandstreamdev/[your_package_name]`. Please make sure that scope `@sandstreamdev/` is used.

#### description

Add brief description - think what users can search as this field is used by `npm search`

#### version

Start from version 0.1.0 - [initial development phase](https://semver.org/#how-should-i-deal-with-revisions-in-the-0yz-initial-development-phase)

#### author

Set author `name` to `Sandstream Development` and the `url` field - `https://www.sandstream.pl/`

#### keywords

Add keywords - think about what user could type in search field to find your package. This field is used by `npm search`. These could be same keywords that were used during Github repository configuration in `topics`.

#### license

Make sure that correct license is set. `npm init` sets `ISC` as default. For opensource use `MIT`.

#### repository

Make sure this field is also present and filled.

```json
"repository": {
  "type": "git",
  "url": "[url_to_github_package_repository]"
}
```

#### files

Make sure that it points to `dist` folder so that only necessary files are added to package.

#### scripts

Add following script to prevent publishing empty package.
```json
"prepare": "npm run build"
```

### template

```json
"name": "@sandstreamdev/[your_package_name]",
"description": "[project_description]",
"version": "0.1.0",
"author": {
  "name": "Sandstream Development",
  "url": "https://www.sandstream.pl/"
},
"keywords": ["keyword_1", "keyword_2"],
"license": "MIT",
"repository": {
  "type": "git",
  "url": "[url_to_github_package_repository]"
},
"files": ["dist"],
"scripts": {
  "prepare": "npm run build"
}
```

## Publishing to npm

:warning: Remeber to build your module before publishing
:warning: Remeber to [test](./npm-module-testing) if module works correctly before publishing.

* `npm login` - use your account that is linked to `sandstreamdev` organization
* `npm publish --access public` - by default scoped packages are published as [private](https://docs.npmjs.com/creating-and-publishing-scoped-public-packages#publishing-scoped-public-packages). Use this command to publish with `public` visibility.

## Using `np` tool for publishing

To simplify process and add additional checks before publishing use ["A better `npm publish`"](https://github.com/sindresorhus/np)
:warning: This tool does not build your module and does not warn about empty module publishing. Make sure you run build script before publishing or add [mentioned script]()

## :warning: Always test published module

After module is published to NPM test if it works by installing package in some new test app.
