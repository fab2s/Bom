# Bom

[![Build Status](https://travis-ci.com/fab2s/Bom.svg?branch=master)](https://travis-ci.com/fab2s/Bom) [![Total Downloads](https://poser.pugx.org/fab2s/bom/downloads)](//packagist.org/packages/fab2s/bom) [![Monthly Downloads](https://poser.pugx.org/fab2s/bom/d/monthly)](//packagist.org/packages/fab2s/bom) [![Latest Stable Version](https://poser.pugx.org/fab2s/bom/v/stable)](https://packagist.org/packages/fab2s/bom) [![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/fab2s/Bom/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/fab2s/Bom/?branch=master) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat)](http://makeapullrequest.com) [![License](https://poser.pugx.org/fab2s/bom/license)](https://packagist.org/packages/fab2s/bom)

A purely static zero dependencies [byte Order Mark](https://en.wikipedia.org/wiki/Byte_order_mark) Helper to handle unicode BOMs

## Installation

`Bom` can be installed using composer:

```
composer require "fab2s/bom"
```

`Bom` is also included in [OpinHelper](https://github.com/fab2s/OpinHelpers) which packages several bellow "Swiss Army Knife" level Helpers covering some of the most annoying aspects of php programing, such as UTF8 string manipulation, high precision Mathematics or properly locking a file

Should you need to work with php bellow 7.1, you can still use [OpinHelper](https://github.com/fab2s/OpinHelpers) `0.x`

## Prerequisites

`Bom` has no specific dependencies 

## In practice

`Bom` supports `UTF-8|16|32` BOMs in both [_Little_](https://en.wikipedia.org/wiki/Endianness#Little) and [_Big_](https://en.wikipedia.org/wiki/Endianness#Big) [Endianness](https://en.wikipedia.org/wiki/Endianness)

`Bom` is minimalistic, it only exposes five methods

```php
// get Bom
$bomAtStartOfString = Bom::extract($string); // returns null when none are found

// remove eventual BOM from beging of string
$bomLessString = Bom::drop($string);

// get encoding from a supported BOM
$encoding = Bom::getBomEncoding($bom); // returns null if the BOM is not valid

// get BOM for a supported encoding
$bom = Bom::getEncodingBom($encoding); // returns null if the encoding is not supported (has no BOM)

// get the list of BOMs as an array with corresponding encodings as indexes
$boms = Bom::getBoms(); // returns an associatiove array of encodings and correesponding BOMs

foreach ($boms as $encoding => $bom) {
    // do something ...
}
```

## Requirements

`Bom` is tested against php 7.1, 7.2, 7.3, 7.4 and 8.0

## Contributing

Contributions are welcome, do not hesitate to open issues and submit pull requests.

## License

`Bom` is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).