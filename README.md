# Sass extend

Extends sass built-in functions with many useful functions.

## How to use

Add `sass-extend` to your scss project and import the modules you want to use using `@use`, just like sass native modules.

## Modules

These are the modules included in `sass-extend`.

### string

```scss
@use "sass-extend/string";
```

#### replace

`string.replace` replaces a substring in a string.

```scss
string.replace($string, $search, $replace: '')
```

The following example shows an example on how to use it.

```scss
@use "sass-extend/string";

$string: "Lorem ipsum";
$replaced-string: string.replace($string, "ipsum", "dolor sit"); // Lorem dolor sit
```

To use with unquoted strings you need to interpolate `$string`.

```scss
@use "sass-extend/string";

$hex: #f5f5f5;
$hex-digits: string.replace(#{$hex}, "#", ""); // f5f5f5
```

### math

```scss
@use "sass-extend/math";
```

#### strip-unit

Function used to remove the unit from a _CSS_ value (number).

```scss
math.strip-unit($number)
```

```scss
@use "sass-extend/math";

$strip-unit: math.strip-unit(16px); // 16
```

## Import all modules at once

It is also possible to import all modues at once. To do so, import `sass-extend` directly.

```scss
@use "sass-extend";
```

All modules will be namespaced with `sass-extend` instead of the module category name. It is possible to change the namespace adding an alias to the import.

```scss
@use "sass-extend" as se;
```

## Demo

This repository includes a demo used to test the functions. Run the demo using the following command. The output will be logged in the terminal.

```bash
npm run demo
```

## Work in this repository

Guidelines for working in this repository.

### Before you start

Install dependencies.

```bash
npm install
```

### Code formatting

This project uses [Prettier](https://prettier.io/) to format the code. To format all files, run the following command.

```bash
npm run prettier
```

### Lint

This project uses [Stylelint](https://stylelint.io) to lint the _scss_. The settings is based on `stylelint-config-standard-scss`. To run the lint, run the following command.

```bash
npm run stylelint
```
