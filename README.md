# @xmgh/stylelint-webpack-plugin

A Stylelint plugin for webpack

## Requirements

This module requires a minimum of Node v6.9.0 and webpack v4.0.0.

## Getting Started

To begin, you'll need to install `@xmgh/stylelint-webpack-plugin`:

```bash
 npm install @xmgh/stylelint-webpack-plugin --save-dev
```

Then add the plugin to your `webpack` config. For example:

```js
// webpack.config.js
const StyleLintPlugin = require('@xmgh/stylelint-webpack-plugin');

module.exports = {
  // ...
  plugins: [
    new StyleLintPlugin(options),
  ],
  // ...
}
```

And run `webpack` via your preferred method.

## Options

See stylelint's [options](http://stylelint.io/user-guide/node-api/#options) for
the complete list of options available. These options are passed through to the
`stylelint` directly.

### `configFile`

Type: `String`
Default: `undefined`

Specify the config file location to be used by `stylelint`.

_Note: By default this is
[handled by `stylelint`](http://stylelint.io/user-guide/configuration/) via
cosmiconfig._

### `context`

Type: `String`
Default: `compiler.context`

A `String` indicating the root of your `SCSS` files.

### `emitErrors`

Type: `Boolean`
Default: `true`

If true, pipes `stylelint` error severity messages to the `webpack` compiler's
error message handler.

_Note: When this property is disabled all `stylelint` messages are piped to the
`webpack` compiler's warning message handler._

### `failOnError`

Type: `Boolean`
Default: `false`

If true, throws a fatal error in the global build process. This will end the
build process on any `stylelint` error.

### `files`

Type: `String|Array[String]`
Default: `'**/*.s?(a|c)ss'`

Specify the glob pattern for finding files. Must be relative to `options.context`.

### `formatter`

Type: `Object`
Default: `require('stylelint').formatters.string`

Specify a custom formatter to format errors printed to the console.

### `lintDirtyModulesOnly`

Type: `Boolean`
Default: `false`

Lint only changed files, skip lint on start.

### `syntax`

Type: `String`
Default: `undefined`

See the `styelint`
[user guide](https://stylelint.io/user-guide/node-api/#syntax) for more info.
e.g. use `'scss'` to lint .scss files.

## Error Reporting

By default the plugin will dump full reporting of errors. Set `failOnError` to
true if you want `webpack` build process breaking with any stylelint error. You
can use the `quiet` option to avoid error output to the console.

## Acknowledgement

This project was forked by [webpack-contrib/stylelint-webpack-plugin](https://github.com/webpack-contrib/stylelint-webpack-plugin), and `update peerDependencies stylelint to ^10.0.0`
