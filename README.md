# npmdoc-splittable

#### api documentation for  splittable (v4.0.0)  [![npm package](https://img.shields.io/npm/v/npmdoc-splittable.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-splittable) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-splittable.svg)](https://travis-ci.org/npmdoc/node-npmdoc-splittable)

#### Module bundler with support for code splitting, ES6 & CommonJS modules.

[![NPM](https://nodei.co/npm/splittable.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/splittable)

- [https://npmdoc.github.io/node-npmdoc-splittable/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-splittable/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-splittable/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-splittable/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-splittable/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-splittable/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "name": "splittable",
    "version": "4.0.0",
    "description": "Module bundler with support for code splitting, ES6 & CommonJS modules.",
    "main": "index.js",
    "scripts": {
        "test": "tap test/*.js"
    },
    "bin": {
        "splittable": "bin.js"
    },
    "keywords": [
        "bundler",
        "module",
        "code splitting",
        "commonjs",
        "es6",
        "closure compiler",
        "JSX"
    ],
    "author": "cramforce",
    "license": "Apache-2.0",
    "devDependencies": {
        "babel-plugin-transform-object-rest-spread": "^6.20.2",
        "babel-preset-es2015": "^6.18.0",
        "babel-preset-stage-0": "^6.16.0",
        "bel": "^4.5.1",
        "d3-array": "^1.0.1",
        "d3-shape": "^1.0.3",
        "fs-extra": "^1.0.0",
        "json-stable-stringify": "^1.0.1",
        "left-pad": "^1.1.3",
        "promise-pjs": "^1.1.2",
        "react": "^15.4.1",
        "react-dom": "^15.4.1",
        "tap": "^8.0.0"
    },
    "dependencies": {
        "babel-plugin-transform-es2015-modules-commonjs": "^6.18.0",
        "babel-plugin-transform-react-jsx": "^6.8.0",
        "babelify": "^7.3.0",
        "bluebird": "^3.4.6",
        "browserify": "^13.1.1",
        "deps-sort": "^2.0.0",
        "dev-null": "^0.1.1",
        "find-root": "^1.0.0",
        "google-closure-compiler": "20161024.3.0",
        "minimist": "^1.2.0",
        "mkpath": "^1.0.0",
        "through2": "^2.0.1",
        "tmp": "0.0.30",
        "topological-sort": "^0.1.5"
    },
    "repository": {
        "type": "git",
        "url": "https://github.com/cramforce/splittable.git"
    }
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
