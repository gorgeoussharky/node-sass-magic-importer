# node-sass-once-importer
[![Build Status](https://travis-ci.org/maoberlehner/node-sass-magic-importer.svg?branch=master)](https://travis-ci.org/maoberlehner/node-sass-magic-importer)

Import files only once. If the same file is imported in multiple `@import` statements, this package will ignore subsequent imports of the same file.

## Usage
```node
var sass = require('node-sass');
var onceImporter = require('node-sass-once-importer');

sass.render({
  ...
  importer: onceImporter()
  ...
});
```

```scss
// Example:
@import 'style1.scss';
@import 'style1.scss';
@import 'style2.scss';
```

```scss
// Contents of style1.scss:
.selector1 { }
.selector2 { }

// Contents of style2.scss:
.selector3 { }
.selector4 { }
```

### CLI
```bash
node-sass --importer node_modules/node-sass-once-importer/dist/cli.js -o dist src/index.scss
```

## Why is there no 1.x, 2.x, 3.x or 4.x version?
This module is maintained in [one repository](https://github.com/maoberlehner/node-sass-magic-importer) together with multiple other node-sass custom importers. The node-sass-magic-importer repository is using a [monorepo approach](https://medium.com/@maoberlehner/monorepos-in-the-wild-33c6eb246cb9) with fixed versions for all packages. The projects maintained in the node-sass-magic-importer monorepo started out as separate repositories with separate versioning, so when they were integrated into the monorepo, the versions of all projects were raised to 5.0.0 and are in sync since then.

## node-sass-magic-importer
This module is powered by [node-sass-magic-importer](https://github.com/maoberlehner/node-sass-magic-importer).

## About
### Author
Markus Oberlehner  
Website: https://markus.oberlehner.net  
Twitter: https://twitter.com/MaOberlehner  
PayPal.me: https://paypal.me/maoberlehner

### License
MIT