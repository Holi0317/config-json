# @easy-webpack/config-json
__NOTE__: The config is only required in webpack 1. See [this issue](https://github.com/webpack/webpack/issues/3363) for detail. 

Load in JSON files using [json-loader](https://github.com/webpack/json-loader). 


# Installation
```
npm install --save-dev @easy-webpack/config-json
```
[easy-webpack](https://github.com/easy-webpack/core) is also required.

# Usage
```js
// webpack.config.js
const generateConfig = require('@easy-webpack/core').generateConfig;

const baseConfig = { ... }; // project-specific config like the entry file

module.exports = generateConfig(
  baseConfig,

  require('@easy-webpack/config-json')
    ({ /* Options object */ exclude: /(node_modules|bower_components)/ })
);

// This config will allow webpack bundle to load in JSON files
```

# Options
### exclude
Type: `(Array of) Webpack Exclude Object` Default: `node_modules`

Files to be excluded from being proceed by json-loader.

Check [webpack documentation](https://webpack.js.org/configuration/module/#condition) on how to write valid exclude files.
