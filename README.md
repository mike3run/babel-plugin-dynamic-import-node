# babel-plugin-dynamic-import-node

## NOTE: THE ORIGINAL NOW SUPPORTS BABEL 7

As of March 2019, [airbnb/babel-plugin-dynamic-import-node](https://github.com/airbnb/babel-plugin-dynamic-import-node) supports Babel 7 out-of-the-box, so you probably don't need to use this.

## FORK OF THE ORIGINAL TO TEST WITH BABEL 7

If you're looking for the original one, check on: [Github](https://github.com/airbnb/babel-plugin-dynamic-import-node)
This fork was created to add support for Babel 7: [Github](https://github.com/mike3run/babel-plugin-dynamic-import-node-babel-7)

Babel plugin to transpile `import()` to a deferred `require()`, for node. Matches the [proposed spec](https://github.com/domenic/proposal-import-function).

**NOTE:** Babylon >= v6.12.0 is required to correct parse dynamic imports.

## Installation

```sh
$ npm install babel-plugin-dynamic-import-node-babel-7 --save-dev
```

## Usage

### Via `.babelrc` (Recommended)

**.babelrc**

```json
{
  "plugins": ["dynamic-import-node-babel-7"]
}
```

### Via CLI

```sh
$ babel --plugins dynamic-import-node script.js
```

### Via Node API

```javascript
require('babel-core').transform('code', {
  plugins: ['dynamic-import-node']
});
```

### Code Example
```javascript
Promise.all([
  import('./lib/import1'),
  import('./lib/import2')
 ]).then(([
   Import1,
   Import2
  ]) => {
   console.log(Import1);
   /* CODE HERE*/
  });
```
