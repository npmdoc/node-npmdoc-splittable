# api documentation for  [splittable (v4.0.0)](https://github.com/cramforce/splittable#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-splittable.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-splittable) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-splittable.svg)](https://travis-ci.org/npmdoc/node-npmdoc-splittable)
#### Module bundler with support for code splitting, ES6 & CommonJS modules.

[![NPM](https://nodei.co/npm/splittable.png?downloads=true)](https://www.npmjs.com/package/splittable)

[![apidoc](https://npmdoc.github.io/node-npmdoc-splittable/build/screenCapture.buildNpmdoc.browser.%2Fhome%2Ftravis%2Fbuild%2Fnpmdoc%2Fnode-npmdoc-splittable%2Ftmp%2Fbuild%2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-splittable/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-splittable/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-splittable/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "cramforce"
    },
    "bin": {
        "splittable": "bin.js"
    },
    "bugs": {
        "url": "https://github.com/cramforce/splittable/issues"
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
    "description": "Module bundler with support for code splitting, ES6 & CommonJS modules.",
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
    "directories": {},
    "dist": {
        "shasum": "185e2a5f828fd075a99b02d7a9571bf07962d6ff",
        "tarball": "https://registry.npmjs.org/splittable/-/splittable-4.0.0.tgz"
    },
    "gitHead": "f31525b70d35ca87a7dc69ed27c0b5cef775511a",
    "homepage": "https://github.com/cramforce/splittable#readme",
    "keywords": [
        "bundler",
        "module",
        "code splitting",
        "commonjs",
        "es6",
        "closure compiler",
        "JSX"
    ],
    "license": "Apache-2.0",
    "main": "index.js",
    "maintainers": [
        {
            "name": "cramforce",
            "email": "malte.ubl@gmail.com"
        }
    ],
    "name": "splittable",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/cramforce/splittable.git"
    },
    "scripts": {
        "test": "tap test/*.js"
    },
    "version": "4.0.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module splittable](#apidoc.module.splittable)
1.  object <span class="apidocSignatureSpan"></span>splittable

#### [module splittable.splittable](#apidoc.module.splittable.splittable)
1.  [function <span class="apidocSignatureSpan">splittable.</span>splittable (config)](#apidoc.element.splittable.splittable.splittable)
1.  [function <span class="apidocSignatureSpan">splittable.splittable.</span>getBundleFlags (g)](#apidoc.element.splittable.splittable.getBundleFlags)
1.  [function <span class="apidocSignatureSpan">splittable.splittable.</span>getFlags (config)](#apidoc.element.splittable.splittable.getFlags)
1.  [function <span class="apidocSignatureSpan">splittable.splittable.</span>getGraph (entryModules, config)](#apidoc.element.splittable.splittable.getGraph)
1.  [function <span class="apidocSignatureSpan">splittable.splittable.</span>maybeAddDotJs (id)](#apidoc.element.splittable.splittable.maybeAddDotJs)
1.  string <span class="apidocSignatureSpan">splittable.splittable.</span>baseBundleWrapper
1.  string <span class="apidocSignatureSpan">splittable.splittable.</span>bundleWrapper
1.  string <span class="apidocSignatureSpan">splittable.splittable.</span>defaultWrapper



# <a name="apidoc.module.splittable"></a>[module splittable](#apidoc.module.splittable)



# <a name="apidoc.module.splittable.splittable"></a>[module splittable.splittable](#apidoc.module.splittable.splittable)

#### <a name="apidoc.element.splittable.splittable.splittable"></a>[function <span class="apidocSignatureSpan">splittable.</span>splittable (config)](#apidoc.element.splittable.splittable.splittable)
- description and source-code
```javascript
splittable = function (config) {

  if (!config || !config.modules) {
    return Promise.reject(
        new Error('Pass an array of entry modules via modules option. ' +
            'Example: {modules: ["./first", "./second"]}'));
  }

  return exports.getFlags(config).then(function(flagsArray) {
    return new Promise(function(resolve, reject) {
      new ClosureCompiler(flagsArray).run(function(exitCode, stdOut, stdErr) {
        if (exitCode == 0) {
          resolve({
            warnings: config.warnings ? stdErr : null,
          });
        } else {
          reject(
              new Error('Closure compiler compilation of bundles failed.\n' +
                  stdOut + '\n' +
                  stdErr));
        }
      });
    })
  });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.splittable.splittable.getBundleFlags"></a>[function <span class="apidocSignatureSpan">splittable.splittable.</span>getBundleFlags (g)](#apidoc.element.splittable.splittable.getBundleFlags)
- description and source-code
```javascript
getBundleFlags = function (g) {
  var flagsArray = [];

  // Write all the packages (directories with a package.json) as --js
  // inputs to the flags. Closure compiler reads the packages to resolve
  // non-relative module names.
  var packageCount = 0;
  Object.keys(g.packages).sort().forEach(function(package) {
    flagsArray.push('--js', package);
    packageCount++;
  });
  // Build up the weird flag structure that closure compiler calls
  // modules and we call bundles.
  var bundleKeys = Object.keys(g.bundles);
  bundleKeys.sort().forEach(function(name) {
    var isBase = name == '_base';
    var extraModules = 0;
    var bundle = g.bundles[name];
    if (isBase || bundleKeys.length == 1) {
      flagsArray.push('--js', relativePath(process.cwd(),
          require.resolve('./base.js')));
      extraModules++;
      Object.keys(g.browserMask).sort().forEach(function(mask) {
        flagsArray.push('--js', mask);
        extraModules++;
      });
    }
    // In each bundle, first list JS files that belong into it.
    bundle.modules.forEach(function(js) {
      if (g.transformed[js]) {
        js = g.transformed[js];
      }
      flagsArray.push('--js', js);
    });
    if (!isBase && bundleKeys.length > 1) {
      flagsArray.push('--js', bundleTrailModule(bundle.name));
      extraModules++;
    }
    // The packages count as inputs to the first module.
    if (packageCount) {
      extraModules += packageCount;
      packageCount = 0;
    }
    // Replace directory separator with - in bundle filename
    var name = bundle.name
        .replace(/\.js$/g, '')
        .replace(/[\/\\]/g, '-');
    // And now build --module $name:$numberOfJsFiles:$bundleDeps
    var cmd = name + ':' + (bundle.modules.length + extraModules);
    // All non _base bundles depend on _base.
    if (!isBase && g.bundles._base) {
      cmd += ':_base';
    }
    flagsArray.push('--module', cmd);
    if (bundleKeys.length > 1) {
      if (isBase) {
        flagsArray.push('--module_wrapper', name + ':' +
            exports.baseBundleWrapper);
      } else {
        flagsArray.push('--module_wrapper', name + ':' +
            exports.bundleWrapper);
      }
    } else {
      flagsArray.push('--module_wrapper', name + ':' +
            exports.defaultWrapper);
    }
  });
  flagsArray.push('--js_module_root', './splittable-build/transformed/');
  flagsArray.push('--js_module_root', './splittable-build/browser/');
  flagsArray.push('--js_module_root', './');
  return flagsArray;
}
```
- example usage
```shell
...
  } else {
    flagsArray.push('--' + flag, val);
  }
});

return exports.getGraph(config.modules, config).then(function(g) {
  return flagsArray.concat(
      exports.getBundleFlags(g, flagsArray));
});
};

exports.getBundleFlags = function(g) {
var flagsArray = [];

// Write all the packages (directories with a package.json) as --js
...
```

#### <a name="apidoc.element.splittable.splittable.getFlags"></a>[function <span class="apidocSignatureSpan">splittable.splittable.</span>getFlags (config)](#apidoc.element.splittable.splittable.getFlags)
- description and source-code
```javascript
getFlags = function (config) {
  // Reasonable defaults.
  var flags = {
    compilation_level: 'ADVANCED',
    process_common_js_modules: true,
    rewrite_polyfills: true,
    create_source_map: '%outname%.map',
    parse_inline_source_maps: true,
    apply_input_source_maps: true,
    source_map_location_mapping: [
      'splittable-build/transformed/|/',
      'splittable-build/browser/|/',
      '|/',
    ],
    new_type_inf: true,
    language_in: 'ES6',
    language_out: 'ES5',
    module_output_path_prefix: config.writeTo || 'out/',
    externs: path.dirname(module.filename) + '/splittable.extern.js',
    jscomp_off: [
      'accessControls',
      'globalThis',
      'misplacedTypeAnnotation',
      'nonStandardJsDocs',
      'suspiciousCode',
      'uselessCode',
    ],
  };

  // Turn object into deterministically sorted array.
  var flagsArray = [];
  Object.keys(flags).sort().forEach(function(flag) {
    var val = flags[flag];
    if (val instanceof Array) {
      val.forEach(function(item) {
        flagsArray.push('--' + flag, item);
      })
    } else {
      flagsArray.push('--' + flag, val);
    }
  });

  return exports.getGraph(config.modules, config).then(function(g) {
    return flagsArray.concat(
        exports.getBundleFlags(g, flagsArray));
  });
}
```
- example usage
```shell
...

if (!config || !config.modules) {
  return Promise.reject(
      new Error('Pass an array of entry modules via modules option. ' +
          'Example: {modules: ["./first", "./second"]}'));
}

return exports.getFlags(config).then(function(flagsArray) {
  return new Promise(function(resolve, reject) {
    new ClosureCompiler(flagsArray).run(function(exitCode, stdOut, stdErr) {
      if (exitCode == 0) {
        resolve({
          warnings: config.warnings ? stdErr : null,
        });
      } else {
...
```

#### <a name="apidoc.element.splittable.splittable.getGraph"></a>[function <span class="apidocSignatureSpan">splittable.splittable.</span>getGraph (entryModules, config)](#apidoc.element.splittable.splittable.getGraph)
- description and source-code
```javascript
getGraph = function (entryModules, config) {
  var resolve;
  var reject;
  var promise = new Promise(function(res, rej) {
    resolve = res;
    reject = rej;
  });
  var topo = new TopologicalSort({});
  var graph = {
    entryModules: entryModules,
    // Lookup whether a module is a dep of a given entry module
    depOf: {},
    // Map of module id to its deps array.
    deps: {},
    // Topological sorted array of all deps.
    sorted: undefined,
    // Generated bundles
    bundles: {
      // We always have a _base bundle.
      _base: {
        isBase: true,
        name: '_base',
        // The modules in the bundle.
        modules: [],
      },
    },
    packages: {},
    // Map of original to transformed filename.
    transformed: {},
    browserMask: {},
  };

  config.babel = config.babel || {};

  // Use browserify with babel to learn about deps.
  var b = browserify(entryModules, {
    debug: true,
    deps: true,
    detectGlobals: false,
  })
  // We register 2 separate transforms. The initial stage are
  // transforms that closure compiler does not support.
  .transform(babel, {
    babelrc: !!config.babel.babelrc,
    plugins: config.babel.plugins || [
      require.resolve("babel-plugin-transform-react-jsx"),
    ],
    presets: config.babel.presets,
  }).
  // The second stage are transforms that closure compiler supports
  // directly and which we don't want to apply during deps finding.
  transform(babel, {
    babelrc: false,
    plugins: [
      require.resolve("babel-plugin-transform-es2015-modules-commonjs"),
    ]
  });

  b.on('package', function(pkg) {
    if (!pkg.browser) {
      return;
    }
    Object.keys(pkg.browser).sort().forEach(function(entry) {
      if (/^\./.test(entry)) {
        throw new Error(
            'Relative entries in package.json#browser not yet supported: ' +
            entry + ' [' + pkg.__dirname + '.package.json]');
      }
      if (pkg.browser[entry] !== false) {
        throw new Error(
            'Only masking of entire modules via false supported in ' +
            'package.json#browser:' + entry +
            ' [' + pkg.__dirname + '.package.json]');
      }
      var filename =
          'splittable-build/browser/node_modules/' + entry;
      var maskedPkg = 'splittable-build/browser/node_modules/' +
          entry.split('/')[0] + '/package.json';
      if (!/\//.test(entry)) {
        filename += '/index';
      }
      filename = exports.maybeAddDotJs(filename);
      if (graph.browserMask[filename]) {
        return;
      }
      graph.browserMask[filename] = true;
      mkpath.sync(path.dirname(filename));
      fs.writeFileSync(filename,
          '// Generated to mask module via package.json#browser.\n' +
          'module.exports = {};\n');
      if (graph.browserMask[pkg]) {
        return;
      }
      graph.browserMask[maskedPkg] = true;
      fs.writeFileSync(maskedPkg,
          '{"Generated to mask module via package.json#browser":true}\n');
    });
  });
  // TODO: Replace with proper plugin system.
  var seenTransform = {};
  b.on('transform', function(tr) {
    if (tr instanceof babel) {
      tr.once("babelify", function(result, filename) {
        if (seenTransform[filename]) {
          return;  // We only care about the first transform per file.
        }
        seenTransform[filename] = true;
        filename = relativePath(process.cwd(), filename);
        // Copy transformed code into shadow path. Files in this path
        // have precedence over regular relative paths.
        var target = './splittable-build/transformed/' + filename;
        mkpath.sync(path.dirname(target));
        fs.writeFileSync(target, result.code);
        graph.transformed[filename] = target;
      });
    }
  });
  // This gets us the actual deps. We collect them in an array, so
  // we can sort them prior to building the dep tree. Otherwise the tree
  // will not be stable.
  var depEntries = [];
  b.pipeline.get('deps').push(through.obj(function(row, enc, next) {
    row.source = null;  // Release memory
    depEntries.push(row);
    next();
  }));

  b. ...
```
- example usage
```shell
...
      flagsArray.push('--' + flag, item);
    })
  } else {
    flagsArray.push('--' + flag, val);
  }
});

return exports.getGraph(config.modules, config).then(function(g) {
  return flagsArray.concat(
      exports.getBundleFlags(g, flagsArray));
});
};

exports.getBundleFlags = function(g) {
var flagsArray = [];
...
```

#### <a name="apidoc.element.splittable.splittable.maybeAddDotJs"></a>[function <span class="apidocSignatureSpan">splittable.splittable.</span>maybeAddDotJs (id)](#apidoc.element.splittable.splittable.maybeAddDotJs)
- description and source-code
```javascript
maybeAddDotJs = function (id) {
  var extensionMatch = id.match(/\.([a-zA-Z0-9]+)$/);
  var extension = extensionMatch ? extensionMatch[1].toLowerCase() : null;
  if (!knownExtensions[extension]) {
    id += '.js'
  }
  return id;
}
```
- example usage
```shell
...
var filename =
    'splittable-build/browser/node_modules/' + entry;
var maskedPkg = 'splittable-build/browser/node_modules/' +
    entry.split('/')[0] + '/package.json';
if (!/\//.test(entry)) {
  filename += '/index';
}
filename = exports.maybeAddDotJs(filename);
if (graph.browserMask[filename]) {
  return;
}
graph.browserMask[filename] = true;
mkpath.sync(path.dirname(filename));
fs.writeFileSync(filename,
    '// Generated to mask module via package.json#browser.\n' +
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
