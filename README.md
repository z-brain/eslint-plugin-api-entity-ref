<div align="center">

![eslint-logo](docs/assets/eslint-logo.svg?sanitize=true)

# @z-brain/eslint-plugin-api-entity-ref

<p>
  <a target="_blank" href="https://github.com/z-brain/eslint-plugin-api-entity-ref/actions?query=workflow%3A%22Build%22">
    <img alt="Build status" src="https://github.com/z-brain/eslint-plugin-api-entity-ref/workflows/Build/badge.svg">
  </a>
  <a target="_blank" href="https://www.npmjs.com/package/@z-brain/eslint-plugin-api-entity-ref">
    <img alt="NPM version" src="https://img.shields.io/npm/v/@z-brain/eslint-plugin-api-entity-ref.svg">
  </a>
  <a target="_blank" href="https://codecov.io/gh/@z-brain/eslint-plugin-api-entity-ref">
    <img alt="Code Coverage" src="https://codecov.io/gh/@z-brain/eslint-plugin-api-entity-ref/branch/master/graph/badge.svg">
  </a>
  <a target="_blank" href="https://www.gnu.org/licenses/gpl-3.0">
    <img alt="License: GPL v3" src="https://img.shields.io/badge/License-GPLv3-blue.svg">
  </a>
</p>

An [ESLint](http://eslint.org) plugin to disable to check that you didn't forget to add `ApiEntityRef` decorator from [`@z-brain/api-entity-ref`](https://github.com/z-brain/api-entity-ref) to your classes with `ApiPropertyRef` decorators.

</div>

---

*Notice: If you have any propositions feel free to make an issue or create a pull request.*

## Installation


```sh
# Install with npm
npm install eslint eslint-plugin-functional --save-dev

# Install with yarn
yarn add -D eslint eslint-plugin-functional
```

**Note:** If you installed ESLint globally (using the `-g` flag with npm or `global` with yarn) then you must also install `eslint-plugin-functional` globally.


## Usage

Add `api-entity-ref` to the plugins section of your `.eslintrc` configuration file. Then configure the rules you want to use under the rules section.

```jsonc
{
  "plugins": ["api-entity-ref"],
  "rules": {
    "api-entity-ref/check-class-decorator": "error"
  }
}
```

Or enable the ruleset via the `extends` property of your `.eslintrc` configuration file.  
   
```jsonc
{
 // ...
 "extends": [
   "plugin:api-entity-ref/recommended"
 ]
}
```


## Development notes

### How to use NodeJS version from the `.nvmrc`

1. Install NVM
2. Use `.nvmrc` file one of the next ways:

    * Execute `nvm use` in the project root directory
    * Install [NVM Loader](https://github.com/korniychuk/ankor-shell) and your .nvmrc will be loaded automatically when you open the terminal.
      ![NVM Loader demo](docs/assets/readme.nvm-loader.png)

### How to make a build

`yarn run build`

### How to run lint

* Just show problems `yarn run lint`
* Fix problems if it is possible `yarn run lint:fix`

### How to run tests

* All tests

  `yarn run test`  
  `yarn run test:watch`
* Specific tests

  `yarn run test -- src/my.spec.ts`  
  `yarn run test:watch -- src/my.spec.ts`

### How to build and publish NPM package

*NPM Token:* `806f...5e2e`

CI configuration details here: [.github/workflows/npmpublish.yml](.github/workflows/npmpublish.yml)

```bash
yarn run pre-push
&& npm version patch -m 'Update package version version to %s'
&& yarn run gen-public-package.json
&& cp README.md dist/
&& npm publish dist --access public
&& git push --no-verify && git push --tags --no-verify
```

## Author

| [<img src="https://www.korniychuk.pro/avatar.jpg" width="100px;"/><br /><sub>Anton Korniychuk</sub>](https://korniychuk.pro) |
| :---: |
