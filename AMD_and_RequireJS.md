# AMD and RequireJS

## background
Client side of our [OSS product](http://partake.in/) wasn't tested. Especially, JavaScript is written in HTML template so it is difficult to do unit test.

![partake.in](https://0.gravatar.com/avatar/4e1e9b35ad10ca9af30cfa8387b6239d?s=180)

Now [Play! framework](playframework.com/) supports RequireJS, it's a good chance to change bad implementation!

## What is AMD?
* AMD = Asynchronous Module Definition
* dependency can be asynchronously loaded

## What is RequireJS?
RequireJS is a module loader for JavaScript.

```coffee
# module.coffee
define ['jquery'], ($) ->
  greet: (name) ->
    $('#foo').text("Hello, #{name}")

# main.coffee
require ['module'], (module) ->
  module.greet 'world'
```

## Why RequireJS?
### Useful configurations
* [`paths`](http://requirejs.org/docs/api.html#config-paths) for path mapping and CDN fallback
* [`shim`](http://requirejs.org/docs/api.html#config-shim) to change legacy script to AMD module
* [`config`](http://requirejs.org/docs/api.html#config-moduleconfig) to give parameter to module

## Why RequireJS?
### Useful tools
* [`r.js`](https://github.com/jrburke/r.js) combines &amp; minifies modules
* [`almond.js`](https://github.com/jrburke/almond) is small and runs optimized build
* [`has.js`](http://requirejs.org/docs/optimization.html#hasjs) makes optimization better

## Use case
* Genius optimization
* CDN fallback

## Use case
### Genius optimization
* Before optimization
    * Download each JS files individually
    * [Disable browser cache](https://github.com/eller86/requirejs-best-practice/tree/master/src/bustCache) for comfortable development
* After optimiation
    * Download combined &amp; minified file
    * Use browser cache to make system fast

## Use case
### CDN fallback
* CDN is good way to improve performance
* But CDN may be down
* `paths` option [ease fallback](http://requirejs.org/docs/api.html#pathsfallbacks)!

```coffee
requirejs.config
  enforceDefine: true
  path:
    jquery: [
      'http://path/to/cdn',
      'lib/jquery'
    ]
```

## See also
* about AMD
    * [Spec](https://github.com/amdjs/amdjs-api/wiki/AMD)
    * [Why AMD?](http://requirejs.org/docs/whyamd.html)
* [RequireJS official site](http://requirejs.org/)
* Other solution
    * [CommonJS modules](http://wiki.commonjs.org/wiki/Modules)
    * [browserify](http://browserify.org/)

## Summary
* optimization makes your product fast
* options makes your development comfortable

Visit [eller86/requirejs-best-practice](https://github.com/eller86/requirejs-best-practice) to read examples.
Thanks!