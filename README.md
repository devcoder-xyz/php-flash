# PHP Flash

PHP Flash is a lightweight library for managing message flash functionality in PHP applications. It allows you to easily display temporary messages, such as success messages, warnings, and error notifications, to enhance the user experience.

[![Latest Stable Version](http://poser.pugx.org/devcoder-xyz/php-flash/v)](https://packagist.org/packages/devcoder-xyz/php-flash) [![Total Downloads](http://poser.pugx.org/devcoder-xyz/php-flash/downloads)](https://packagist.org/packages/devcoder-xyz/php-flash) [![Latest Unstable Version](http://poser.pugx.org/devcoder-xyz/php-flash/v/unstable)](https://packagist.org/packages/devcoder-xyz/php-flash) [![License](http://poser.pugx.org/devcoder-xyz/php-flash/license)](https://packagist.org/packages/devcoder-xyz/php-flash) [![PHP Version Require](http://poser.pugx.org/devcoder-xyz/php-flash/require/php)](https://packagist.org/packages/devcoder-xyz/php-flash)
## Features

- Simple and intuitive message flash management.
- Display success messages, warnings, and error notifications.
- Automatic clearing of messages after retrieval.

## Installation

To install PHP Flash, use [Composer](https://getcomposer.org/):

```bash
composer require devcoder-xyz/php-flash
```

## Usage

### Basic Usage

```php
use DevCoder\Flash\Flash;

// Assuming you already have session_start() called in your script
$flash = new Flash($_SESSION);

// Set flash messages
$flash->set('success', 'Operation completed successfully.');
$flash->set('error', 'An error occurred.');

// Get and display flash messages
if ($message = $flash->get('success')) {
    echo '<div class="success">' . $message . '</div>';
}

if ($message = $flash->get('error')) {
    echo '<div class="error">' . $message . '</div>';
}
```

### Custom Flash Key

By default, PHP Flash uses the key "__flash" in the session storage. You can use a custom key if needed:

```php
// Assuming you already have session_start() called in your script
$customFlashKey = 'my_custom_flash_key';
$flash = new Flash($_SESSION, $customFlashKey);
```

## Contribution

Contributions are welcome! If you find any issues or have suggestions, please open an issue or submit a pull request.

## License

PHP Flash is open-source software licensed under the [MIT license](https://opensource.org/licenses/MIT).