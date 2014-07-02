[![view on npm](http://img.shields.io/npm/v/jsdoc-to-markdown.svg)](https://www.npmjs.org/package/jsdoc-to-markdown)
[![npm module downloads per month](http://img.shields.io/npm/dm/jsdoc-to-markdown.svg)](https://www.npmjs.org/package/jsdoc-to-markdown)
[![Dependency Status](https://david-dm.org/75lb/jsdoc-to-markdown.svg)](https://david-dm.org/75lb/jsdoc-to-markdown)
![Analytics](https://ga-beacon.appspot.com/UA-27725889-32/jsdoc-to-markdown/README.md?pixel)

***work in progress, unstable, draft documentation***

#jsdoc-to-markdown
[Documented](http://usejsdoc.org) source code in, markdown out.. In development, any feedback welcome.

##Install
Ensure [node.js](http://nodejs.org) is installed first. Linux/Mac users may need to run the following commands with `sudo`.

###Globally
```sh
$ npm install -g jsdoc-to-markdown
```

###Bundled with your project
```sh
$ npm install jsdoc-to-markdown --save-dev
```

Then add an `docs` build task to your `package.json` scripts, e.g.:
```json
{
  "name": "my-web-app",
  "version": "1.0.0",
  "scripts": {
    "docs": "jsdoc2md --index lib/*.js"
  }
}
```
This approach abstracts implementation details away, saving collaborators the hassle of installing / learning `jsdoc-to-markdown`. Docs are generated like so:

```sh
$ npm run docs
```

###As a grunt plug-in
See [grunt-jsdoc-to-markdown](https://github.com/75lb/grunt-jsdoc-to-markdown).

###As a gulp plug-in
Use like this until [gulp-jsdoc-to-markdown](https://github.com/75lb/gulp-jsdoc-to-markdown):

```js
```

##Usage
Document your source code using [correct jsdoc syntax](http://usejsdoc.org), then run it through `jsdoc2md`. 
```
$ jsdoc2md <options> <source_files>

-t, --template <string>  A custom handlebars template to insert the rendered documentation into,
                         overriding the default
-p, --preset <string>    Use a preset template ('default', 'global' or 'modules')
-j, --json               Output the template data only
-h, --help               Print usage information
--src <array>            The javascript source files. The default option.
--index                  Include an index for each module and class, linking to members
--skip-heading           Skip the module heading, useful if you already have the heading
                         elsewhere in your template.
--private                Include symbols marked @private in the output
```

##examples
These projects have readme files rendered by `jsdoc2md`:
* https://github.com/75lb/handbrake-js (exports an object with inner class)
* https://github.com/75lb/array-tools (exports a object)
* https://github.com/75lb/file-set (exports a class)
* https://github.com/75lb/command-line-args  (exports a class)

#API Reference
<a name="module_jsdoc-to-markdown"></a>

  
**Example**  
```js
var jsdoc2md = require("jsdoc-to-markdown");
```

<a name="module_jsdoc-to-markdown.render"></a>
###jsdoc2md.render(options)
**Params**

- options `object` - The render options
  - [template] `string` - A handlebars template to insert your documentation into.
  - [preset] `string` - Choose from one of the built-in templates
  - [json] `boolean` - Return the JSON template data only
  - [src] `Array.<string>` - The javascript source files
  - [index] `boolean` - Include an index for each module and class, linking to members
  - [skip-heading] `boolean` - Skip the module heading, useful if you already have the heading elsewhere in your template.
  - [private] `boolean` - Include symbols marked @private in the output
  - [heading-depth] `number` - Root heading depth, defaults to 2.
-  [onRender](#module_jsdoc-to-markdown.onRender) - a callback invoked on completion

<a name="module_jsdoc-to-markdown.onRender"></a>
###\~callback: onRender
Called by `jsdoc2md.render()` on completion.

**Params**

- err `object` - An error instance if applicable, else `null`
- result `string` - the rendered markdown

**Scope**: inner typedef of [jsdoc-to-markdown](#module_jsdoc-to-markdown)  
**Type**: `function`  
