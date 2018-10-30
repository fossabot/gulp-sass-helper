# next-io-gulp

Helper app to unify gulp implementations for next-io gulp task builds.

[![Henrique](https://img.shields.io/badge/maintainer-Henrique-blue.svg?colorB=0066ff)](https://henriquecarv.com)
[![LICENSE](https://img.shields.io/github/license/henriquecarv/gulp-sass-helper.svg)](./LICENSE)
[![Dependabot Status](https://api.dependabot.com/badges/status?host=github&repo=henriquecarv/gulp-sass-helper)](https://dependabot.com)

## System Requirements

- **[NodeJS](https://nodejs.org/en/)** (version >= 8).

## Installing

- `npm i -D gulp@next next-io-gulp stylelint stylelint-config-sass-guidelines stylelint-scss`

## Usage

```javascript
const gulp = require('gulp');
const nextIOGulp = require('next-io-gulp');

const paths = {sass: {src: './react/**/*.scss', dest: './react'}};

let isDev = true;

const runSassCompiler = done => {
	nextIOGulp.sassCompiler(paths);
	done();
};

const runSassLint = done => {
	nextIOGulp.sassLint(paths, isDev);
	done();
};

const build = gulp.series(runSassLint, runSassCompiler);
```