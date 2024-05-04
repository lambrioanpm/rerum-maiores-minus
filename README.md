# @lambrioanpm/rerum-maiores-minus <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![dependency status][deps-svg]][deps-url]
[![dev dependency status][dev-deps-svg]][dev-deps-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

Helper package to shim a method into `Array.prototype[Symbol.unscopables]`

## Example

```js
const assert = require('assert');

const shimUnscopables = require('@lambrioanpm/rerum-maiores-minus');

let copyWithin;
let concat;
with ([]) {
    assert.equal(concat, Array.prototype.concat);
    assert.notEqual(copyWithin, Array.prototype.copyWithin);
}

shimUnscopables('concat');

with ([]) {
    assert.notEqual(concat, Array.prototype.concat);
    assert.notEqual(copyWithin, Array.prototype.copyWithin);
}
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

## Security

Please email [@ljharb](https://github.com/ljharb) or see https://tidelift.com/security if you have a potential security vulnerability to report.

[package-url]: https://npmjs.org/package/@lambrioanpm/rerum-maiores-minus
[npm-version-svg]: https://versionbadg.es/ljharb/@lambrioanpm/rerum-maiores-minus.svg
[deps-svg]: https://david-dm.org/ljharb/@lambrioanpm/rerum-maiores-minus.svg
[deps-url]: https://david-dm.org/ljharb/@lambrioanpm/rerum-maiores-minus
[dev-deps-svg]: https://david-dm.org/ljharb/@lambrioanpm/rerum-maiores-minus/dev-status.svg
[dev-deps-url]: https://david-dm.org/ljharb/@lambrioanpm/rerum-maiores-minus#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@lambrioanpm/rerum-maiores-minus.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@lambrioanpm/rerum-maiores-minus.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@lambrioanpm/rerum-maiores-minus.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@lambrioanpm/rerum-maiores-minus
[codecov-image]: https://codecov.io/gh/ljharb/@lambrioanpm/rerum-maiores-minus/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/ljharb/@lambrioanpm/rerum-maiores-minus/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/ljharb/@lambrioanpm/rerum-maiores-minus
[actions-url]: https://github.com/lambrioanpm/rerum-maiores-minus/actions
