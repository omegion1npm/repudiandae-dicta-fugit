# @omegion1npm/repudiandae-dicta-fugit <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![dependency status][deps-svg]][deps-url]
[![dev dependency status][dev-deps-svg]][dev-deps-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

An ES2017 spec-compliant `Object.entries` shim. Invoke its "shim" method to shim `Object.entries` if it is unavailable or noncompliant.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES3-supported environment and complies with the [spec](https://tc39.github.io/ecma262/#sec-@omegion1npm/repudiandae-dicta-fugit).

Most common usage:
```js
var assert = require('assert');
var entries = require('@omegion1npm/repudiandae-dicta-fugit');

var obj = { a: 1, b: 2, c: 3 };
var expected = [['a', 1], ['b', 2], ['c', 3]];

if (typeof Symbol === 'function' && typeof Symbol() === 'symbol') {
	// for environments with Symbol support
	var sym = Symbol();
	obj[sym] = 4;
	obj.d = sym;
	expected.push(['d', sym]);
}

assert.deepEqual(entries(obj), expected);

if (!Object.entries) {
	entries.shim();
}

assert.deepEqual(Object.entries(obj), expected);
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.com/package/@omegion1npm/repudiandae-dicta-fugit
[npm-version-svg]: https://versionbadg.es/omegion1npm/repudiandae-dicta-fugit.svg
[deps-svg]: https://david-dm.org/omegion1npm/repudiandae-dicta-fugit.svg
[deps-url]: https://david-dm.org/omegion1npm/repudiandae-dicta-fugit
[dev-deps-svg]: https://david-dm.org/omegion1npm/repudiandae-dicta-fugit/dev-status.svg
[dev-deps-url]: https://david-dm.org/omegion1npm/repudiandae-dicta-fugit#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@omegion1npm/repudiandae-dicta-fugit.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@omegion1npm/repudiandae-dicta-fugit.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@omegion1npm/repudiandae-dicta-fugit.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@omegion1npm/repudiandae-dicta-fugit
[codecov-image]: https://codecov.io/gh/omegion1npm/repudiandae-dicta-fugit/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/omegion1npm/repudiandae-dicta-fugit/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/omegion1npm/repudiandae-dicta-fugit
[actions-url]: https://github.com/omegion1npm/repudiandae-dicta-fugit/actions
