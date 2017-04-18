# npmtest-famous

#### test coverage for  [famous (v0.7.1)](https://github.com/Famous/engine#readme)  [![npm package](https://img.shields.io/npm/v/npmtest-famous.svg?style=flat-square)](https://www.npmjs.org/package/npmtest-famous) [![travis-ci.org build-status](https://api.travis-ci.org/npmtest/node-npmtest-famous.svg)](https://travis-ci.org/npmtest/node-npmtest-famous)

#### Famous Engine =================

[![NPM](https://nodei.co/npm/famous.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/famous)

| git-branch : | [alpha](https://github.com/npmtest/node-npmtest-famous/tree/alpha)|
|--:|:--|
| coverage : | [![istanbul-coverage](https://npmtest.github.io/node-npmtest-famous/build/coverage.badge.svg)](https://npmtest.github.io/node-npmtest-famous/build/coverage.html/index.html)|
| test-report : | [![test-report](https://npmtest.github.io/node-npmtest-famous/build/test-report.badge.svg)](https://npmtest.github.io/node-npmtest-famous/build/test-report.html)|
| build-artifacts : | [![build-artifacts](https://npmtest.github.io/node-npmtest-famous/glyphicons_144_folder_open.png)](https://github.com/npmtest/node-npmtest-famous/tree/gh-pages/build)|

- [https://npmtest.github.io/node-npmtest-famous/build/coverage.html/index.html](https://npmtest.github.io/node-npmtest-famous/build/coverage.html/index.html)

[![istanbul-coverage](https://npmtest.github.io/node-npmtest-famous/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fcoverage.lib.html.png)](https://npmtest.github.io/node-npmtest-famous/build/coverage.html/index.html)

- [https://npmtest.github.io/node-npmtest-famous/build/test-report.html](https://npmtest.github.io/node-npmtest-famous/build/test-report.html)

[![test-report](https://npmtest.github.io/node-npmtest-famous/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Ftest-report.html.png)](https://npmtest.github.io/node-npmtest-famous/build/test-report.html)

- [https://npmdoc.github.io/node-npmdoc-famous/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-famous/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-famous/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-famous/build/apidoc.html)

![npmPackageListing](https://npmtest.github.io/node-npmtest-famous/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmtest.github.io/node-npmtest-famous/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Famous"
    },
    "browserify": {
        "transform": [
            "glslify"
        ]
    },
    "bugs": {
        "url": "https://github.com/Famous/engine/issues"
    },
    "dependencies": {
        "glslify": "^2.0.0"
    },
    "description": "Famous Engine =================",
    "devDependencies": {
        "browserify": "^10.2.1",
        "colors": "^1.1.0",
        "eslint": "^0.21.2",
        "glob": "^5.0.10",
        "istanbul": "^0.3.15",
        "rewire": "^2.3.3",
        "sinon": "^1.14.1",
        "smokestack": "^3.2.2",
        "tap-closer": "^1.0.0",
        "tap-spec": "^4.0.0",
        "tape": "^4.0.0",
        "uglify-js": "^2.4.17"
    },
    "directories": {},
    "dist": {
        "shasum": "1e3751912b2f44ac4a22930c153e647dce52a5c8",
        "tarball": "https://registry.npmjs.org/famous/-/famous-0.7.1.tgz"
    },
    "gitHead": "68dd0345078ef44daa74de6a22b89e19eaeaaa9f",
    "homepage": "https://github.com/Famous/engine#readme",
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "thealphanerd"
        },
        {
            "name": "famous"
        },
        {
            "name": "michaelobriena"
        }
    ],
    "name": "famous",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git+https://github.com/Famous/engine.git"
    },
    "scripts": {
        "build": "npm run build-debug && npm run build-min",
        "build-debug": "browserify index.js -d --standalone famous > dist/famous.js",
        "build-min": "browserify index.js --standalone famous | uglifyjs --screw-ie8 -m -c dead_code,sequences,conditionals,booleans,unused,if_return,join_vars,drop_debugger > dist/famous.min.js",
        "check-jsdoc": "eslint --reset --no-eslintrc --rule 'valid-jsdoc: 2' --ignore-path .gitignore .",
        "lint": "eslint --ignore-path .gitignore .",
        "tape": "tap-closer | smokestack -b firefox | tap-spec",
        "test": "EXIT_STATUS=0; npm run test-components || EXIT_STATUS=$?; npm run test-core || EXIT_STATUS=$?; npm run test-dom-renderables || EXIT_STATUS=$?; npm run test-dom-renderers || EXIT_STATUS=$?; npm run test-render-loops || EXIT_STATUS=$?; npm run test-math || EXIT_STATUS=$?; npm run test-physics || EXIT_STATUS=$?; npm run test-polyfills || EXIT_STATUS=$?; npm run test-renderers || EXIT_STATUS=$?; npm run test-transitions || EXIT_STATUS=$?; npm run test-utilities || EXIT_STATUS=$?; npm run test-webgl-geometries || EXIT_STATUS=$?; npm run test-webgl-materials || EXIT_STATUS=$?; npm run test-webgl-renderables || EXIT_STATUS=$?; npm run test-webgl-renderers; exit $EXIT_STATUS",
        "test-components": "browserify components/test/*.js | npm run tape",
        "test-core": "npm run test-new",
        "test-dom-renderables": "browserify dom-renderables/test/*.js | npm run tape",
        "test-dom-renderers": "browserify dom-renderers/test/*.js | npm run tape",
        "test-math": "browserify math/test/*.js | npm run tape",
        "test-new": "node ./scripts/test.js ./core/**/*.spec.js",
        "test-physics": "browserify physics/test/*.js physics/test/*/*.js | npm run tape",
        "test-polyfills": "browserify polyfills/test/*.js | npm run tape",
        "test-render-loops": "browserify render-loops/test/*.js | npm run tape",
        "test-renderers": "browserify renderers/test/*.js | npm run tape",
        "test-transitions": "browserify transitions/test/*.js | npm run tape",
        "test-utilities": "browserify utilities/test/*.js | npm run tape",
        "test-webgl-geometries": "browserify webgl-geometries/test/*.js | npm run tape",
        "test-webgl-materials": "browserify webgl-materials/test/*.js | npm run tape",
        "test-webgl-renderables": "browserify webgl-renderables/test/*.js | npm run tape",
        "test-webgl-renderers": "browserify webgl-renderers/test/*.js | npm run tape"
    },
    "version": "0.7.1"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
