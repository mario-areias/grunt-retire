# grunt-retire v0.1.0

> Grunt task for retire. Scanner detecting the use of JavaScript libraries with known vulnerabilites.



## Getting Started
This plugin requires Grunt `~0.4.0`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-retire --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-retire');
```




## Retire task
_Run this task with the `grunt retire` command._

Task targets, files and options may be specified according to the grunt [Configuring tasks](http://gruntjs.com/configuring-tasks) guide.
### Options
`verbose: true/false`, default is `true`.

This task primarily delegates to [Retire][], so please consider the [Retire documentation][] as required reading for advanced configuration.

[Retire]: https://github.com/bekk/retire.js

## Scan node dependencies example
TODO

## Scan javascript files only
```js
    retire: {
      files: ['app/src/*'], /** Scan js-files in app/src/ directory. **/
      options: {
      }
    }
```

Running ```grunt retire``` will scan files in app/src/ for vulnerabilities.


## Limit node scan to packages where parent is mentioned in package.json (ignore node_modules)
TODO

Setting ```debug: true``` will log identified files


## Example output


## No vulnerabilities
```
➜  grunt-retire git:(master) ✗ grunt
Running "jshint:all" (jshint) task
>> 2 files lint free.

Running "retire:all" (retire) task
Downloading http://localhost:8000/repository/jsrepository.json ...
Checking: Gruntfile.js

Done, without errors.
```
## Found 1 vulnerability in jquery-1.6.js
```
➜  grunt-retire git:(master) ✗ grunt
Running "jshint:all" (jshint) task
>> 2 files lint free.

Running "retire:all" (retire) task
Downloading http://localhost:8000/repository/jsrepository.json ...
Checking: test-files/dojo.js
Checking: test-files/jquery-1.6.js
>> test-files/jquery-1.6.js
>> ↳ jquery 1.6
>> Vulnerabilities found! Please review log for details.
Checking: test-files/safe.js
Warning: Task "retire:all" failed. Use --force to continue.

Aborted due to warnings.
```
## Release History

 * 2013-10-30   v0.1.0   First version.