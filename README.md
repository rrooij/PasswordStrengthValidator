RollerworksPasswordStrength Validator
=====================================

This package provides various password strength validators for the [Symfony Validator
component](http://symfony.com/doc/current/components/validator.html). 

_To use this bundle with a Symfony application use the [RollerworksPasswordStrengthBundle][1]._

Passwords can be validated using either strength-levels (weak, medium, strong etc)
or by configuring explicit requirements (needs letters, numbers etc).

> This library provides the same level of functionality as the
> [PasswordStrengthBundle](https://github.com/jbafford/PasswordStrengthBundle) created by John Bafford.

## Installation

To install this package, add `rollerworks/password-strength-validator` to your composer.json:

```bash
$ php composer.phar require rollerworks/password-strength-validator
```

Now, [Composer][2] will automatically download all required files, and install them
for you.

## Requirements

You need at least PHP 5.6 or PHP 7.0, mbstring is recommended but not required.
For the provided blacklist providers you may need SQLite3 or PDO compatible driver. 

## Basic Usage

**Caution:**

> The password validators do not enforce that the field must have a value!
> To make a field "required" use the [NotBlank constraint](http://symfony.com/doc/current/reference/constraints/NotBlank.html)
> in combination with the password validator(s).

All examples assume you have the Composer autoloader already in your code,
see also [How to Install and Use the Symfony Components](http://symfony.com/doc/current/components/using_components.html)
for more information.

### [Strength validation](docs/strength-validation.md)

Validates the passwords strength-level (weak, medium, strong etc).

### [Requirements validation](docs/requirements-validation.md)

Validates the passwords using explicitly configured requirements (letters, caseDiff, numbers, requireSpecialCharacter).

### [Password blacklisting](docs/blacklist.md)

There are times you want forbid (blacklist) a password from usage.

Passwords are blacklisted using providers which can either be an array or
(flat-file) database (which you can update regularly).

With the default installation the following providers can be used.

* Noop: Default provider, does nothing.

* Array: Simple in memory blacklist provider (not recommended for big lists)

* Sqlite: Provides the blacklist using a SQLite3 database file.

* Pdo: Provides the blacklist using the PDO extension.

But building your own is also possible.
__Documentation on this is currently missing,
see current providers for more information.__

## Versioning

For transparency and insight into the release cycle, and for striving
to maintain backward compatibility, this package is maintained under
the Semantic Versioning guidelines as much as possible.

Releases will be numbered with the following format:

`<major>.<minor>.<patch>`

And constructed with the following guidelines:

* Breaking backward compatibility bumps the major (and resets the minor and patch)
* New additions without breaking backward compatibility bumps the minor (and resets the patch)
* Bug fixes and misc changes bumps the patch

For more information on SemVer, please visit <http://semver.org/>.

## License

This library is released under the [MIT license](LICENSE).

## Contributing

This is an open source project. If you'd like to contribute,
please read the [Contributing Guidelines][3]. If you're submitting
a pull request, please follow the guidelines in the [Submitting a Patch][4] section.

[1]: https://github.com/rollerworks/PasswordStrengthBundle]
[2]: https://getcomposer.org/doc/00-intro.md
[3]: https://github.com/rollerworks/contributing
[4]: https://contributing.readthedocs.org/en/latest/code/patches.html
