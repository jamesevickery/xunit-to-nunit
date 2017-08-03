# xunit-to-nunit

[![npm version](https://badge.fury.io/js/xunit-to-nunit.svg)](https://badge.fury.io/js/xunit-to-nunit)
[![circleci status](https://circleci.com/gh/jamesevickery/xunit-to-nunit.svg?style=shield)](https://circleci.com/gh/jamesevickery/xunit-to-nunit)
[![Build Status](https://travis-ci.org/jamesevickery/xunit-to-nunit.svg?branch=master)](https://travis-ci.org/jamesevickery/xunit-to-nunit)
[![Dependencies](https://www.versioneye.com/user/projects/59819587368b080078e5cabc/badge.svg)](https://www.versioneye.com/user/projects/59819587368b080078e5cabc?child=summary)

[![NPM](https://nodei.co/npm/xunit-to-nunit.png)](https://nodei.co/npm/xunit-to-nunit/)

Converts C# XUnit tests to NUnit tests.

_Disclaimer: Far from perfect - something I used as a quick hack to convert loads of large tests_

## Links

- Interactive converter app ([gh-pages](https://github.com/jamesevickery/xunit-to-nunit/tree/gh-pages)): [jamesevickery.github.io/xunit-to-nunit](https://jamesevickery.github.io/xunit-to-nunit)
- Node module: [npmjs.com/package/xunit-to-nunit](https://www.npmjs.com/package/xunit-to-nunit)

## :package: Installation

```bash
npm install xunit-to-nunit --save
```

## Usage

### Require

```javascript
var x2n = require('xunit-to-nunit')
```

### Convert test from string

```javascript
var nunitTest = x2n.convertCode(xunitTest)
```

### Convert test from file

```javascript
x2n.convertFile('xunit-source-path.cs', 'nunit-destination-path.cs')
```

### Convert tests from directory

```javascript
x2n.convertFiles('xunit/source/directory', 'nunit/destination/directory')
```

This function calls `convertFile` for all files in the source directory.

#### Options

`convertFiles` has a third (optional) parameter: `options`. This should be a dictionary value, containing all or any of the following  parameters:

##### :wrench: recursive (default: `false`)

Set to `true`, this parameter will convert tests in all subdirectories including those at the source root. Directory structure is maintained at the conversion destination.

##### :wrench: verbose (default: `true`)

When `true`, the module logs an info message to the terminal when a file is converted. When a file conversion fails, a error log message is displayed regardless of the value of `verbose`.

For example,

```javascript
var options = {
  recursive: true,
  verbose: false
}
x2n.convertFiles('xunit/source/directory', 'nunit/destination/directory', options)
```

## Contributing

Feel free to add things / suggest things to be added by either [opening an issue](https://github.com/jamesevickery/xunit-to-nunit/issues) or by submitting a pull request.

## References

- https://xunit.github.io/docs/comparisons.html
