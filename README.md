# Simport [![License][LicenseIMGURL]][LicenseURL] [![NPM version][NPMIMGURL]][NPMURL] [![Dependency Status][DependencyStatusIMGURL]][DependencyStatusURL] [![Build Status][BuildStatusIMGURL]][BuildStatusURL] [![Coverage Status][CoverageIMGURL]][CoverageURL]

Use [dynamic imports](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import#Dynamic_Imports) just like plain old [require](https://nodejs.org/api/esm.html#esm_require).

With simport you can:

- get `require`
- get `__filename` or `__dirname`
- load json
- avoid extensions
- avoid destructuring default
- pass `simport` into functions like [tryCatch](https://github.com/coderaiser/try-to-catch).

## Install

`npm i simport`

## API

### simport(name)

```js
import simpor from 'simport';

// you can import json
await simport('./package.json');
// returns
({
    name: simport,
});

// you can avoid .js extension
await simport('./server');

// you can avoid destructure default
const validate = await simport('./validate');
// same as
const {default: validate2} = await import('./validate.js');
```

### createCommons(import.meta.url)

```js
import {createCommons} from 'simport';

const {
    __filename,
    __dirname,
    require,
} = createCommons(import.meta.url);

// now you have plain old CommonJS variables
```


## License

MIT

[NPMIMGURL]:                https://img.shields.io/npm/v/thread-it.svg?style=flat
[BuildStatusIMGURL]:        https://travis-ci.com/coderaiser/simport.svg?branch=master
[DependencyStatusIMGURL]:   https://img.shields.io/david/coderaiser/simport.svg?style=flat
[LicenseIMGURL]:            https://img.shields.io/badge/license-MIT-317BF9.svg?style=flat
[NPMURL]:                   https://npmjs.org/package/thread-it "npm"
[BuildStatusURL]:           https://travis-ci.com/coderaiser/simport  "Build Status"
[DependencyStatusURL]:      https://david-dm.org/coderaiser/simport "Dependency Status"
[LicenseURL]:               https://tldrlegal.com/license/mit-license "MIT License"

[CoverageURL]:              https://coveralls.io/github/coderaiser/simport?branch=master
[CoverageIMGURL]:           https://coveralls.io/repos/coderaiser/simport/badge.svg?branch=master&service=github