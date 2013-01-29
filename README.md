# grunt-angular-templates [![Build Status](https://travis-ci.org/ericclemmons/grunt-angular-templates.png?branch=master)](https://travis-ci.org/ericclemmons/grunt-angular-templates)

Grunt build task to concatenate & register your AngularJS templates in the $templateCache

**NOTE**:

- Use `0.1.x` for Grunt `0.3.x`.
- Use `0.2.x` for Grunt `0.4.x`.


## Getting Started
Install this grunt plugin next to your project's [grunt.js gruntfile][getting_started] with: `npm install grunt-angular-templates`

Then add this line to your project's `grunt.js` gruntfile:

```javascript
grunt.loadNpmTasks('grunt-angular-templates');
```

[grunt]: http://gruntjs.com/
[getting_started]: https://github.com/gruntjs/grunt/blob/master/docs/getting_started.md


## Documentation

This plugin provides the grunt task `ngtemplates`, which will allow you to compile your HTML templates into a single JS file,
which preloads `$templateCache` to prevent round-trips to the server.

### Update Grunt:

```js
// grunt.js
grunt.initConfig({
  ngtemplates:  {
    app:        {
      options:  { base: 'src/views' },
      src:      [ 'src/views/**.html' ],
      dest:     'dist/templates.js'
    }
  }
});
```

### Add template module to your app

```js
// js/app.js
angular.module('app', [
  'app.templates'  // Generated by ngtemplates:app
  ...
]);
```


## Changelog

### v0.2

  - Update to Grunt 0.4, thanks to @jgrund. ([#5](https://github.com/ericclemmons/grunt-angular-templates/issues/5))

### v0.1.3

- Fixes

    - Convert `\\` to `/` in template IDs (for on win32 systems) ([#3](https://github.com/ericclemmons/grunt-angular-templates/issues/3))

### v0.1.2

- Added NPM keywords

### v0.1.1

- Fixes

    - [Fails to combine multiple templates](https://github.com/ericclemmons/grunt-angular-templates/issues/1)

- New

    - Added directions to README on how to integrate with AngularJS app
    - Integrated with TravisCI

### v0.1.0

- Released to [NPM](https://npmjs.org/package/grunt-angular-templates)

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [grunt][grunt].


## License

Copyright (c) 2013 Eric Clemmons
Licensed under the MIT license.
