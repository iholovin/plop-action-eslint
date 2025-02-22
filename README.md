# plop-action-eslint

[![npm version](https://badge.fury.io/js/plop-action-eslint.svg)](https://badge.fury.io/js/plop-action-eslint)
[![GitHub license](https://img.shields.io/github/license/natterstefan/plop-action-eslint.svg)](https://github.com/natterstefan/plop-action-eslint/blob/main/LICENSE)

A [Plop](https://github.com/plopjs/plop) action to lint files with
[ESLint](https://eslint.org/) and automatically format with
[Prettier](#prettier-support).

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
  - [Actions](#actions)
- [Prettier Support](#prettier-support)

## Installation

```sh
npm install plop-action-eslint --save-dev

# or with yarn
yarn add plop-action-eslint -D
```

## Usage

Before you can use `plop-action-eslint`, you have to load it into the `plop`
object by adding the folling to your `plopfile.js`:

```javascript
// plopfile.js
module.exports = plop => {
  plop.load('plop-action-eslint')
}
```

Once loaded, you have access the following actions.

### Actions

#### `eslint`

Lints and fixes (autofix is enabled) the file of the given path with your
projects ESLint configuration.

```javascript
{
  type: "eslint",
  path: "src/component/{{pascalCase name}}.js",
}
```

## Prettier Support

In order to automatically format your code with Prettier as well, you have to
use [eslint-config-prettier][1] and [eslint-plugin-prettier][2] in your ESLint
configuration.

## How to release

### Manually trigger release

```bash
yarn lerna:version
npx lerna-changelog --from <tag> --to <tag>
git push --follow-tags
```

## License

[MIT](./LICENSE)

## Credits

This plop action is based on the code that was shared in
[plop#80](https://github.com/plopjs/plop/issues/80#issuecomment-645179250) by
[FDiskas](https://github.com/FDiskas).

[1]: https://github.com/prettier/eslint-config-prettier
[2]: https://github.com/prettier/eslint-plugin-prettier
