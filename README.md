# stylelint-scss

[![NPM version](https://img.shields.io/npm/v/stylelint-scss.svg)](https://www.npmjs.org/package/stylelint-scss)
[![Build Status](https://travis-ci.org/kristerkari/stylelint-scss.svg?branch=master)](https://travis-ci.org/kristerkari/stylelint-scss)
[![Build status](https://ci.appveyor.com/api/projects/status/xa12kju6qmvmqs1n?svg=true)](https://ci.appveyor.com/project/kristerkari/stylelint-scss)
[![v1.0.0 progress](http://progressed.io/bar/100?title=v1.0.0)](https://github.com/kristerkari/stylelint-scss/milestones/1.0.0)

A collection of SCSS specific linting rules for [stylelint](https://github.com/stylelint/stylelint) (in a form of a plugin).

(Work in progress - not released yet).
	
[TODO/Checklist for release v1.0.0](https://github.com/kristerkari/stylelint-scss/issues/14)

## Purpose

stylelint by itself supports [SCSS syntax](http://stylelint.io/user-guide/css-processors/#parsing-non-standard-syntax) very well (as well as other preprocessors' syntaxes). Moreover, it introduces some specific rules that can be used to lint SCSS, e.g. to limit [`nesting`](http://stylelint.io/user-guide/rules/max-nesting-depth/), control the way [`@-rules`](http://stylelint.io/user-guide/rules/#at-rule) are written. Yet stylelint is in general focused on standard CSS.

stylelint-scss introduces rules specific to SCSS syntax. That said, the rules from this plugin can be used with other syntaxes, like Less or some PostCSS syntaxes. That's why the rules' names are not tied to SCSS only (`at-function-pattern` instead of `scss-function-pattern`).

The plugin follows stylelint's guidelines (about [rule names](http://stylelint.io/user-guide/about-rules/), testing and [so on](https://github.com/stylelint/stylelint/tree/master/docs/developer-guide)).

## Installation and usage

stylelint-scss is a plugin for [stylelint](http://stylelint.io/user-guide/), so it's meant to be used with it. First, install stylelint-scss (and stylelint, if you haven't done so yet) via NPM:

```
npm install stylelint stylelint-scss
```

Create the `.stylelintrc.json` config file (or open the existing one), add `stylelint-scss` to the plugins array and the rules you need to the rules list. All rules from stylelint-scss need to be namespaced with `scss`.

```json
{
  "plugins": [
    "stylelint-scss"
  ],
  "rules": {
    "scss/dollar-variable-pattern": "^foo",
    "scss/selector-no-redundant-parent": true,
    ...
  }
}
```

Please refer to [stylelint docs](http://stylelint.io/user-guide/) for the detailed info on using this linter.

## List of rules

Here are stylelint-scss' rules, grouped by the [*thing*](http://apps.workflower.fi/vocabs/css/en) they apply to (just like in [stylelint](http://stylelint.io/user-guide/about-rules/)).

### `@`-function

- [`at-function-pattern`](../../src/rules/at-function-pattern/README.md): Specify a pattern for Sass/SCSS-like function names.

### `@`-mixin

- [`at-mixin-pattern`](../../src/rules/at-mixin-pattern/README.md): Specify a pattern for Sass/SCSS-like mixin names.

### `$`-variable

- [`dollar-variable-no-missing-interpolation`](../../src/rules/dollar-variable-no-missing-interpolation/README.md): Disallow Sass variables that are used without interpolation with CSS features that use custom identifiers.
- [`dollar-variable-pattern`](../../src/rules/dollar-variable-pattern/README.md): Specify a pattern for Sass-like variables.

### Extend

- [`extend-require-placeholder`](../../src/rules/extend-require-placeholder/README.md): Require placeholder selectors to be used with `@extend`.

### Selector

- [`selector-no-redundant-parent`](../../src/rules/extend-require-placeholder/README.md): Disallow unnecessary parent selector references (`&`).

## Help out

There work on the plugin's rules is still in progress, so if you feel like it, you're welcome to help out in any of these (the plugin follows stylelint guidelines so most part of this is based on its docs):

* Create, enhance, and debug rules (see stylelint's guide to "[Working on rules](https://github.com/stylelint/stylelint/blob/master/docs/developer-guide/rules.md)").
* Improve documentation.
* Chime in on any open issue or pull request.
* Open new issues about your ideas on new rules, or for how to improve the existing ones, and pull requests to show us how your idea works.
* Add new tests to absolutely anything.
* Work on improving performance of rules.
* Contribute to [stylelint](https://github.com/stylelint/stylelint)
* Spread the word.

We communicate via [issues](https://github.com/kristerkari/stylelint-scss/issues) and [pull requests](https://github.com/kristerkari/stylelint-scss/pulls).

There is also [stackoverflow](http://stackoverflow.com/questions/tagged/stylelint), which would be the preferred QA forum.

## Important documents

- [Changelog](https://github.com/kristerkari/stylelint-scss/blob/master/CHANGELOG.md)
- [Contributing guidelines](https://github.com/stylelint/stylelint/blob/master/CONTRIBUTING.md)
- [License](https://github.com/kristerkari/stylelint-scss/blob/master/LICENSE)