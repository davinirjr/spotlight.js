# Spotlight.js v1.1.0

An object crawler/property search library that works on nearly all JavaScript platforms.

## Documentation

* [doc/README.md](https://github.com/bestiejs/spotlight.js/blob/master/doc/README.md#readme)
* [wiki/Roadmap](https://github.com/bestiejs/spotlight.js/wiki/Roadmap)

## Installation

Spotlight.js’ only hard dependency is [lodash](https://lodash.com/).

In a browser:

```html
<script src="lodash.js"></script>
<script src="spotlight.js"></script>
```

In an AMD loader:

```js
require({
  'paths': {
    'spotlight': 'path/to/spotlight',
    'lodash': 'path/to/lodash'
  }
},
['spotlight'], function(spotlight) {/*…*/});
```

Using npm:

```bash
$ npm i --save spotlight
```

In Node.js:

```js
var spotlight = require('spotlight');
```

Usage example:

```js
// find all "length" properties
spotlight.byName('length');

// or find all "map" properties on jQuery
spotlight.byName('map', { 'object': jQuery, 'path': '$' });

// or all properties with `jQuery` objects
spotlight.byKind(jQuery);

// or all properties with `RegExp` values
spotlight.byKind('RegExp');

// or all properties with `null` values
spotlight.byKind('null');

// or all properties with `undefined` values
spotlight.byKind('undefined');

// or all constructors
spotlight.byKind('constructor');

// or all properties with the value `0`
spotlight.byValue(0);

// or all properties containing "oo" in their name
spotlight.custom(function(value, key) { return key.indexOf('oo') > -1; });

// or all properties with falsey values
spotlight.custom(function(value) { return !value; });
```

## Support

Tested in Chrome 38-39, Firefox 33-34, IE 6-11, Opera 25-26, Safari 5-8, Node.js 0.8.26~0.10.35, PhantomJS 1.9.8, RingoJS 0.11, & Rhino 1.7RC5.

## BestieJS

Spotlight.js is part of the BestieJS *“Best in Class”* module collection. This means we promote solid browser/environment support, ES5+ precedents, unit testing, & plenty of documentation.
