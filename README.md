[![view on npm](http://img.shields.io/npm/v/jsdoc-to-markdown.svg)](https://www.npmjs.org/package/jsdoc-to-markdown)
[![npm module downloads](http://img.shields.io/npm/dt/jsdoc-to-markdown.svg)](https://www.npmjs.org/package/jsdoc-to-markdown)
[![Build Status](https://travis-ci.org/jsdoc2md/jsdoc-to-markdown.svg?branch=master)](https://travis-ci.org/jsdoc2md/jsdoc-to-markdown)
[![Dependency Status](https://david-dm.org/jsdoc2md/jsdoc-to-markdown.svg)](https://david-dm.org/jsdoc2md/jsdoc-to-markdown)
[![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg)](https://github.com/feross/standard)
[![Join the chat at https://gitter.im/jsdoc2md/jsdoc2md](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/jsdoc2md/jsdoc2md?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

***The is the next version of the tool, a work in progress.***

# jsdoc-to-markdown
This tool generates API documentation from [jsdoc](http://usejsdoc.org) annotated source code.

There are two documentation templates built in: terminal and markdown. If you direct the output of jsdoc2md to a file it will use the markdown template, otherwise the more human-readable terminal template. Tweaking or building your own templates is simple.

You can inject jsdoc2md output into a template of your own, e.g. a README file.

## Synopsis
write documented code:
```js
/**
 * a quite wonderful function
 * @param {object} - privacy gown
 * @param {object} - security
 * @returns {survival}
 */
function protection(cloak, dagger){}
```

run a command:
```
$ jsdoc2md example/protection.js
```

get markdown docs! (in [github-flavored-markdown](https://help.github.com/articles/github-flavored-markdown/) format by default)
```handlebars
<a name="protection"></a>
## protection(cloak, dagger) ⇒ survival
a quite wonderful function

**Params**

| name   | type | description  |
| ------ | ---- | ------------ |
| cloak  | TYPE | privacy gown |
| dagger | TYPE | security     |
```

## Features

- Insert API documentation into a README, or any arbitrary document.
- Customisable to a granular level. If the output doesn't suit you, change it.
- Package your modifications, publish to npm and share with others (e.g. [dmd-bitbucket](https://github.com/jsdoc2md/dmd-bitbucket))
- Accepts `.js` or `.html` input files (parsing html is experimental - [more](https://github.com/jsdoc2md/jsdoc-parse/))
- Extends jsdoc with some new tags ([more](https://github.com/jsdoc2md/jsdoc-parse/))
- Use any arbitrary tag, e.g. `@fulfil`, `@reject`, `@hatredlevel` etc.

## More information

- Example output
- Additional tags supported
- How to tweak the output


<a name="module_jsdoc-to-markdown"></a>
## jsdoc-to-markdown
**Example**
```js
var jsdoc2md = require('jsdoc-to-markdown')
```


* * *


<a name="exp_module_jsdoc-to-markdown--jsdoc2md"></a>
### jsdoc2md([options]) ⇒ Duplex  
Transforms jsdoc into markdown documentation.

**Params**

- [options] module:dmd~DmdOptions &#124; module:jsdoc-parse~ParseOptions - the options
**Example**
Pass in filepaths (`**` glob matching supported) of javascript source files:
```js
> jsdoc2md({ src: 'lib/*.js' }).pipe(process.stdout)
```


* * *



* * *

&copy; 2015 Lloyd Brookes <75pound@gmail.com>. Documented by [jsdoc-to-markdown](https://github.com/jsdoc2md/jsdoc-to-markdown).
