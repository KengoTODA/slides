# RequireJS + r.js

!SLIDE

# RequireJS

### what we can improve
### by RequireJS and r.js

!SLIDE left

## Agenda

* Self introduction
* Motivation
* What is RequireJS?
* How to use

!SLIDE left

## Self introduction

户田 健互 (@eller86)

* Came from the country of 忍者.

!SLIDE left

## Self introduction

* I can use,
    * Java, JavaScript, CoffeeScript
    * BASIC, COBOL, Fortran, Pascal etc.
    * ObjectWeb ASM, FindBugs, PMD, Jenkins

* https://github.com/eller86/findbugs-slf4j

!SLIDE

# Motivation

!SLIDE left

## Why RequireJS?

* JS switched from accessory to application
* Plugin &amp; library hell
    * Order to load
    * Too many HTTP connection to load

!SLIDE

## Solution = RequireJS

<image src="images/requirejs.png" width="440" height="276">

!SLIDE

# What is RequireJS?

!SLIDE left

## What is RequireJS?

* RequireJS is a AMD loader
* [AMD](https://github.com/amdjs/amdjs-api/wiki/AMD) means:
    * **A**synchronous
    * **M**odule
    * **D**efinition
* A mechanism for defining modules, their dependencies can be asynchronously loaded. 

!SLIDE

## Sort complex dependency

<img src="images/dependency.png" width="450" height="283">

./jquery.js -> ./template.js -> ./jquery-plugin.js -> ./bootstrap.js -> ./bootstrap-plugin.js -> ./main.js

!SLIDE

## Optimize (join + minify)

<img src="images/optimize.png" width="580" height="155">

Loading time =  
_HTTP connections_ * latency +  
_data size_ * throughput

!SLIDE

# HOW to use

!SLIDE

## like this

```javascript
define([
    // here you can list dependencies
    'jquery'
  ],
  function($){
    // here you can use $ as local variable
    $('#message').text('Hello, world!');
});
```

```coffeescript
define ['event','header/view','header/server'], (event, view, server) ->
  view.on 'logout', ->
    server.logout()

  event.on 'change-tab', (e) ->
    view.updateTitle e.activeTab
```

!SLIDE left

## Advanced solution

* [github.com/eller86/requirejs-best-practice](https://github.com/eller86/requirejs-best-practice)
    * Cache bust
    * A/B test
    * Responsive JavaScript
    * i18n
    * Resource preloading

!SLIDE left

# Try it!

* [requirejs.org](http://requirejs.org/)
* [github.com/jrburke/requirejs](https://github.com/jrburke/requirejs)

