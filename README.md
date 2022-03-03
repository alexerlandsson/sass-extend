# Sass extend

Extends sass built-in functions with many useful functions.

## How to use

Add `sass-extend` to your scss project and import the modules you want to use using `@use`, just like sass native modules.

## Modules
### string

```scss
@use 'sass-extend/string';
```

#### replace

`string.replace` replaces a substring in a string.

```scss
string.replace($string, $search, $replace: '')
```

The following example shows an example on how to use it.

```scss
@use 'sass-extend/string';

$string: 'Lorem ipsum';
$replaced-string: string.replace($string, 'ipsum', 'dolor sit'); // Lorem dolor sit
```

To use with unquoted strings you need to interpolate `$string`.

```scss
@use 'sass-extend/string';

$hex: #f5f5f5;
$hex-digits: string.replace(#{$hex}, '#', ''); // f5f5f5
```

### math

#### strip-unit

Function used to remove the unit from a _CSS_ value (number).

```scss
math.strip-unit($number)
```

```scss
@use 'sass-extend/math';

$strip-unit: math.strip-unit(16px); // 16
```
