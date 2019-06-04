# 45PRESS PHPCS

## Installation

Install the library via Composer:

```bash
composer require --dev 45press/phpcs:dev-master
```

## Usage

Lint your PHP files with the following command:

```bash
./vendor/bin/phpcs .
```

Edit the `composer.json` file by adding the following:

```json
  "scripts": {
    "lint": [
      "phpcs ."
    ],
  }
```

Then lint with...

```bash
composer run lint
```

### Continuous Integration

Library loads the `45PRESS-Standard` ruleset, and checks for syntax errors for PHP 7.1 or higher.

To override the default PHP version check, set the `--runtime-set testVersion 7.1-` configuration option. Example for PHP version 7.2 and above:

```bash
./vendor/bin/phpcs --runtime-set testVersion 7.2-
```

Note that you can only overrule PHP version check from the command-line.

### IDE

IDE integrations of PHPCS can fail to register the `45PRESS-Standard` ruleset. If this happens, place `.phpcs.xml.dist` at your project root:

```xml
<?xml version="1.0"?>
<ruleset name="Project PHPCS">
	<rule ref="45PRESS-Standard" />
</ruleset>
```
