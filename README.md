# Prettier Config Dslemay

[![CircleCI](https://circleci.com/gh/dslemay/prettier-config-dslemay.svg?style=svg)](https://circleci.com/gh/dslemay/prettier-config-dslemay)
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)

Prettier is an excellent tool to reduce bike shedding on code formatting. It ships with reasonable defaults and reduces the time spent thinking about various formatting issues that don't matter in the long term. There are several rules which I prefer to override. As of v1.17 Prettier offers first class support for shared configuration. This package shares my preferred base Prettier configuration.

## Installation and configuration

This package has a peerDependency of Prettier `>=1.17.0` to support both means of extending the configuration.

**Install:**

```shell
yarn add --dev prettier prettier-config-dslemay
```

```shell
npm i -D prettier prettier-config-dslemay
```

### Configure

There are several ways to configure your project to use this configuration depending on your preferences and if you want to override any of the settings it provides.

```json
{
  "name": "my-cool-package",
  "version": "1.0.0",
  "prettier": "prettier-config-dslemay"
}
```

You can also use any of the supported Prettier config extensions that can export a string such as the example `.prettierrc.json` below.

```json
"prettier-config-dslemay"
```

If you would like to override any of the settings in the config, use a JavaScript config file such as the example `.prettierrc.js` below.

```javascript
module.exports = {
  ...require('prettier-config-dslemay'),
  singleQuote: false,
}
```

## Deviations from default config

Below are the deviations this config takes from the default Prettier configuration.

- **jsxSingleQuote**: `true`. Prefer single quotes in both JSX and JS for consistent quote usage.
- **semi**: `false`. After working on some projects which don't use them, I have come to appreciate their removal. There are only a few cases where they are necessary. Kent C Dodds has a well written [post](https://kentcdodds.com/blog/semicolons-in-javascript-a-preference) on the matter as well.
- **singleQuote**: `true`. Prefer single quotes in JavaScript.
- **trailingComma**: `'all'`. This makes for cleaner git diffs.
