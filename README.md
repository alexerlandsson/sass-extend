# sass-extend

Extends [sass](https://sass-lang.com/) built-in modules with additional useful functions.

## How to use

Add _sass-extend_ to your scss project and import the modules you want to use using `@use`, just like native [sass modules](https://sass-lang.com/documentation/modules).

> If you are using native sass modules within the same namespace, use an alias for _sass-extend_ to prevent namespace conflicts.

## Modules

These are the modules included in _sass-extend_.

### string

```scss
@use "sass-extend/string";
```

#### replace

`string.replace` replaces a substring in a string.

```scss
string.replace($string, $search, $replace: "")
```

The following snippet shows an example on how to use it.

```scss
@use "sass-extend/string";

$string: "Lorem ipsum";
$replaced-string: string.replace($string, "ipsum", "dolor sit"); // Lorem dolor sit
```

To use with an unquoted string, you need to interpolate it.

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

The following snippet shows an example on how to use it.

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
