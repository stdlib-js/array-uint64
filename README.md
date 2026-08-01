<!--

@license Apache-2.0

Copyright (c) 2026 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# Uint64Array

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> 64-bit unsigned integer array.

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->



<section class="usage">

## Usage

```javascript
import Uint64Array from 'https://cdn.jsdelivr.net/gh/stdlib-js/array-uint64@deno/mod.js';
```

#### Uint64Array()

Creates a 64-bit unsigned integer array.

```javascript
var arr = new Uint64Array();
// returns <Uint64Array>
```

#### Uint64Array( length )

Creates a 64-bit unsigned integer array having a specified length.

```javascript
var arr = new Uint64Array( 5 );
// returns <Uint64Array>[ 0n, 0n, 0n, 0n, 0n ]
```

#### Uint64Array( typedarray )

Creates a 64-bit unsigned integer array from another [typed array][mdn-typed-array].

```javascript
import Uint32Array from 'https://cdn.jsdelivr.net/gh/stdlib-js/array-uint32@deno/mod.js';

var arr1 = new Uint32Array( [ 5, 5, 5 ] );
var arr2 = new Uint64Array( arr1 );
// returns <Uint64Array>[ 5n, 5n, 5n ]
```

#### Uint64Array( obj )

Creates a 64-bit unsigned integer array from an array-like object or iterable.

```javascript
var arr = new Uint64Array( [ 5.0, 5.0, 5.0 ] );
// returns <Uint64Array>[ 5n, 5n, 5n ]
```

#### Uint64Array( buffer\[, byteOffset\[, length]] )

Returns a 64-bit unsigned integer array view of an [`ArrayBuffer`][@stdlib/array/buffer].

```javascript
import ArrayBuffer from 'https://cdn.jsdelivr.net/gh/stdlib-js/array-buffer@deno/mod.js';

var buf = new ArrayBuffer( 32 );
var arr = new Uint64Array( buf, 0, 4 );
// returns <Uint64Array>[ 0n, 0n, 0n, 0n ]
```

* * *

### Properties

<a name="static-prop-bytes-per-element"></a>

#### Uint64Array.BYTES_PER_ELEMENT

Static property returning the size (in bytes) of each array element.

```javascript
var nbytes = Uint64Array.BYTES_PER_ELEMENT;
// returns 8
```

<a name="static-prop-name"></a>

#### Uint64Array.name

Static property returning the constructor name.

```javascript
var str = Uint64Array.name;
// returns 'Uint64Array'
```

<a name="prop-buffer"></a>

#### Uint64Array.prototype.buffer

**Read-only** property which returns the underlying [`ArrayBuffer`][@stdlib/array/buffer] referenced by array instance.

```javascript
var arr = new Uint64Array( 5 );

var buf = arr.buffer;
// returns <ArrayBuffer>
```

<a name="prop-byte-length"></a>

#### Uint64Array.prototype.byteLength

**Read-only** property which returns the length (in bytes) of the array instance.

```javascript
var arr = new Uint64Array( 5 );

var byteLength = arr.byteLength;
// returns 40
```

<a name="prop-byte-offset"></a>

#### Uint64Array.prototype.byteOffset

**Read-only** property which returns the offset (in bytes) of the array instance from the start of its underlying [`ArrayBuffer`][@stdlib/array/buffer].

```javascript
var arr = new Uint64Array( 5 );

var byteOffset = arr.byteOffset;
// returns 0
```

<a name="prop-bytes-per-element"></a>

#### Uint64Array.prototype.BYTES_PER_ELEMENT

Size (in bytes) of each array element.

```javascript
var arr = new Uint64Array( 5 );

var nbytes = arr.BYTES_PER_ELEMENT;
// returns 8
```

<a name="prop-length"></a>

#### Uint64Array.prototype.length

**Read-only** property which returns the number of array elements.

```javascript
var arr = new Uint64Array( 5 );

var len = arr.length;
// returns 5
```

* * *

### Methods

<a name="static-method-from"></a>

#### Uint64Array.from( src\[, map\[, thisArg]] )

Creates a new 64-bit unsigned integer array from an array-like object or an iterable.

```javascript
var arr = Uint64Array.from( [ 1, 2 ] );
// returns <Uint64Array>[ 1n, 2n ]
```

To invoke a function for each `src` value, provide a callback function.

```javascript
function mapFcn( v ) {
    return v * 2;
}

var arr = Uint64Array.from( [ 1, 2 ], mapFcn );
// returns <Uint64Array>[ 2n, 4n ]
```

A callback function is provided two arguments:

-   **value**: source value.
-   **index**: source index.

To set the callback execution context, provide a `thisArg`.

```javascript
function mapFcn( v ) {
    this.count += 1;
    return v * 2;
}

var ctx = {
    'count': 0
};

var arr = Uint64Array.from( [ 1, 2 ], mapFcn, ctx );
// returns <Uint64Array>[ 2n, 4n ]

var n = ctx.count;
// returns 2
```

<a name="static-method-of"></a>

#### Uint64Array.of( element0\[, element1\[, ...elementN]] )

Creates a new 64-bit unsigned integer array from a variable number of arguments.

```javascript
var arr = Uint64Array.of( 1, 2 );
// returns <Uint64Array>[ 1n, 2n ]
```

<a name="method-at"></a>

#### Uint64Array.prototype.at( i )

Returns an array element located at integer position (index) `i`, with support for both nonnegative and negative integer positions.

```javascript
var arr = new Uint64Array( 10 );

// Set the first, second, and last elements:
arr.set( 1, 0 );
arr.set( 2, 1 );
arr.set( 9, 9 );

// Get the first element:
var z = arr.at( 0 );
// returns <Uint64>[ 1n ]

// Get the last element:
z = arr.at( -1 );
// returns <Uint64>[ 9n ]
```

If provided an out-of-bounds index, the method returns `undefined`.

```javascript
var arr = new Uint64Array( 10 );

var z = arr.at( 100 );
// returns undefined

z = arr.at( -100 );
// returns undefined
```

<a name="method-get"></a>

#### Uint64Array.prototype.get( i )

Returns an array element located at position (index) `i`.

```javascript
var arr = new Uint64Array( 10 );

// Set the first element:
arr.set( 1, 0 );

// Get the first element:
var z = arr.get( 0 );
// returns <Uint64>[ 1n ]
```

If provided an out-of-bounds index, the method returns `undefined`.

```javascript
var arr = new Uint64Array( 10 );

var z = arr.get( 100 );
// returns undefined
```

<a name="method-set"></a>

#### Uint64Array.prototype.set( value\[, i] )

Sets one or more array elements.

```javascript
import Uint64 from 'https://cdn.jsdelivr.net/gh/stdlib-js/number-uint64-ctor@deno/mod.js';

var arr = new Uint64Array( [ 1, 2, 3 ] );
// returns <Uint64Array>[ 1n, 2n, 3n ]

// Get the first element:
var z = arr.get( 0 );
// returns <Uint64>[ 1n ]

// Set the first element:
arr.set( new Uint64( 5 ) );

// Get the first element:
z = arr.get( 0 );
// returns <Uint64>[ 5n ]
```

By default, the method sets array elements starting at position (index) `i = 0`. To set elements starting elsewhere in the array, provide an index argument `i`.

```javascript
import Uint64 from 'https://cdn.jsdelivr.net/gh/stdlib-js/number-uint64-ctor@deno/mod.js';

var arr = new Uint64Array( [ 1, 2, 3 ] );
// returns <Uint64Array>[ 1n, 2n, 3n ]

// Get the third element:
var z = arr.get( 2 );
// returns <Uint64>[ 3n ]

// Set the third element:
arr.set( new Uint64( 5 ), 2 );

// Get the third element:
z = arr.get( 2 );
// returns <Uint64>[ 5n ]
```

In addition to providing a scalar value (e.g., nonnegative integer, [`bigint`][@stdlib/bigint/ctor], or [`Uint64`][@stdlib/number/uint64/ctor]), to set one or more array elements, provide an array-like object containing scalar values

```javascript
import Uint64 from 'https://cdn.jsdelivr.net/gh/stdlib-js/number-uint64-ctor@deno/mod.js';

var arr = new Uint64Array( [ 1, 2, 3 ] );
// returns <Uint64Array>[ 1n, 2n, 3n ]

// Set the first two array elements:
arr.set( [ 4, 5 ] );

var z = arr.get( 0 );
// returns <Uint64>[ 4n ]

z = arr.get( 1 );
// returns <Uint64>[ 5n ]
```

A few notes:

-   If `i` is out-of-bounds, the method throws an error.
-   If a target array cannot accommodate all values (i.e., the length of source array plus `i` exceeds the target array length), the method throws an error.
-   If provided a [typed array][@stdlib/array/typed] which shares an [`ArrayBuffer`][@stdlib/array/buffer] with the target array, the method will intelligently copy the source range to the destination range.

</section>

<!-- /.usage -->

* * *

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

* * *

## Notes

-   While a `Uint64Array` _strives_ to maintain (but does not **guarantee**) consistency with [typed arrays][@stdlib/array/typed], significant deviations from ECMAScript-defined [typed array][@stdlib/array/typed] behavior are as follows:

    -   The constructor does **not** require the `new` operator.
    -   The constructor and associated methods support a broader variety of input argument types in order to better accommodate unsigned integer input.
    -   Accessing array elements using bracket syntax (e.g., `X[i]`) is **not** supported. Instead, one **must** use the `.get()` method.
    -   The `set` method has extended behavior in order to support 64-bit unsigned integer instances.

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

* * *

## Examples

<!-- eslint no-undef: "error" -->

```javascript
import Uint64 from 'https://cdn.jsdelivr.net/gh/stdlib-js/number-uint64-ctor@deno/mod.js';
import logEach from 'https://cdn.jsdelivr.net/gh/stdlib-js/console-log-each@deno/mod.js';
import Uint32Array from 'https://cdn.jsdelivr.net/gh/stdlib-js/array-uint32@deno/mod.js';
import Uint64Array from 'https://cdn.jsdelivr.net/gh/stdlib-js/array-uint64@deno/mod.js';

// Create a 64-bit unsigned integer array by specifying a length:
var out = new Uint64Array( 3 );
logEach( '%s', out );

// Create a 64-bit unsigned integer array from an array of 64-bit unsigned integer numbers:
var arr = [
    new Uint64( 1 ),
    new Uint64( 2 ),
    new Uint64( 3 )
];
out = new Uint64Array( arr );
logEach( '%s', out );

// Create a 64-bit unsigned integer array from a typed array:
arr = new Uint32Array( [ 1, 2, 3, 4 ] );
out = new Uint64Array( arr );
logEach( '%s', out );

// Create a 64-bit unsigned integer array from an array buffer, where underlying storage consists of interleaved high and low 32-bit words:
arr = new Uint32Array( [ 1, 2, 3, 4 ] );
out = new Uint64Array( arr.buffer );
logEach( '%s', out );

// Create a 64-bit unsigned integer array from an array buffer view, where underlying storage represents each 64-bit integer as interleaved high and low 32-bit words:
arr = new Uint32Array( [ 1, 2, 3, 4, 5, 6, 7, 8 ] );
out = new Uint64Array( arr.buffer, 16, 2 );
logEach( '%s', out );
```

</section>

<!-- /.examples -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2026. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/array-uint64.svg
[npm-url]: https://npmjs.org/package/@stdlib/array-uint64

[test-image]: https://github.com/stdlib-js/array-uint64/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/array-uint64/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/array-uint64/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/array-uint64?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/array-uint64.svg
[dependencies-url]: https://david-dm.org/stdlib-js/array-uint64/main

-->

[chat-image]: https://img.shields.io/badge/zulip-join_chat-brightgreen.svg
[chat-url]: https://stdlib.zulipchat.com

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/array-uint64/tree/deno
[deno-readme]: https://github.com/stdlib-js/array-uint64/blob/deno/README.md
[umd-url]: https://github.com/stdlib-js/array-uint64/tree/umd
[umd-readme]: https://github.com/stdlib-js/array-uint64/blob/umd/README.md
[esm-url]: https://github.com/stdlib-js/array-uint64/tree/esm
[esm-readme]: https://github.com/stdlib-js/array-uint64/blob/esm/README.md
[branches-url]: https://github.com/stdlib-js/array-uint64/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/array-uint64/main/LICENSE

[mdn-typed-array]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray

[@stdlib/array/typed]: https://github.com/stdlib-js/array-typed/tree/deno

[@stdlib/array/buffer]: https://github.com/stdlib-js/array-buffer/tree/deno

[@stdlib/number/uint64/ctor]: https://github.com/stdlib-js/number-uint64-ctor/tree/deno

[@stdlib/bigint/ctor]: https://github.com/stdlib-js/bigint-ctor/tree/deno

</section>

<!-- /.links -->
