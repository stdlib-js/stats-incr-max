<!--

@license Apache-2.0

Copyright (c) 2018 The Stdlib Authors.

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

# incrmax

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Compute a maximum value incrementally.

<section class="installation">

## Installation

```bash
npm install @stdlib/stats-incr-max
```

Alternatively,

-   To load the package in a website via a `script` tag without installation and bundlers, use the [ES Module][es-module] available on the [`esm` branch][esm-url].
-   If you are using Deno, visit the [`deno` branch][deno-url].
-   For use in Observable, or in browser/node environments, use the [Universal Module Definition (UMD)][umd] build available on the [`umd` branch][umd-url].

The [branches.md][branches-url] file summarizes the available branches and displays a diagram illustrating their relationships.

</section>

<section class="usage">

## Usage

```javascript
var incrmax = require( '@stdlib/stats-incr-max' );
```

#### incrmax()

Returns an accumulator `function` which incrementally computes a maximum value.

```javascript
var accumulator = incrmax();
```

#### accumulator( \[x] )

If provided an input value `x`, the accumulator function returns an updated maximum value. If not provided an input value `x`, the accumulator function returns the current maximum value.

```javascript
var accumulator = incrmax();

var max = accumulator( 2.0 );
// returns 2.0

max = accumulator( 1.0 );
// returns 2.0

max = accumulator( 3.0 );
// returns 3.0

max = accumulator();
// returns 3.0
```

</section>

<!-- /.usage -->

<section class="notes">

## Notes

-   Input values are **not** type checked. If provided `NaN`, the accumulated value is `NaN` for **all** future invocations. If non-numeric inputs are possible, you are advised to type check and handle accordingly **before** passing the value to the accumulator function.

</section>

<!-- /.notes -->

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```javascript
var randu = require( '@stdlib/random-base-randu' );
var incrmax = require( '@stdlib/stats-incr-max' );

var accumulator;
var v;
var i;

// Initialize an accumulator:
accumulator = incrmax();

// For each simulated datum, update the max...
for ( i = 0; i < 100; i++ ) {
    v = randu() * 100.0;
    accumulator( v );
}
console.log( accumulator() );
```

</section>

<!-- /.examples -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

* * *

## See Also

-   <span class="package-name">[`@stdlib/stats-incr/midrange`][@stdlib/stats/incr/midrange]</span><span class="delimiter">: </span><span class="description">compute a mid-range incrementally.</span>
-   <span class="package-name">[`@stdlib/stats-incr/min`][@stdlib/stats/incr/min]</span><span class="delimiter">: </span><span class="description">compute a minimum value incrementally.</span>
-   <span class="package-name">[`@stdlib/stats-incr/mmax`][@stdlib/stats/incr/mmax]</span><span class="delimiter">: </span><span class="description">compute a moving maximum incrementally.</span>
-   <span class="package-name">[`@stdlib/stats-incr/range`][@stdlib/stats/incr/range]</span><span class="delimiter">: </span><span class="description">compute a range incrementally.</span>
-   <span class="package-name">[`@stdlib/stats-incr/summary`][@stdlib/stats/incr/summary]</span><span class="delimiter">: </span><span class="description">compute a statistical summary incrementally.</span>

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2023. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/stats-incr-max.svg
[npm-url]: https://npmjs.org/package/@stdlib/stats-incr-max

[test-image]: https://github.com/stdlib-js/stats-incr-max/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/stats-incr-max/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/stats-incr-max/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/stats-incr-max?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/stats-incr-max.svg
[dependencies-url]: https://david-dm.org/stdlib-js/stats-incr-max/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/stats-incr-max/tree/deno
[umd-url]: https://github.com/stdlib-js/stats-incr-max/tree/umd
[esm-url]: https://github.com/stdlib-js/stats-incr-max/tree/esm
[branches-url]: https://github.com/stdlib-js/stats-incr-max/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/stats-incr-max/main/LICENSE

<!-- <related-links> -->

[@stdlib/stats/incr/midrange]: https://github.com/stdlib-js/stats-incr-midrange

[@stdlib/stats/incr/min]: https://github.com/stdlib-js/stats-incr-min

[@stdlib/stats/incr/mmax]: https://github.com/stdlib-js/stats-incr-mmax

[@stdlib/stats/incr/range]: https://github.com/stdlib-js/stats-incr-range

[@stdlib/stats/incr/summary]: https://github.com/stdlib-js/stats-incr-summary

<!-- </related-links> -->

</section>

<!-- /.links -->
