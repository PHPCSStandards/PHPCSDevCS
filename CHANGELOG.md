# Change Log for the PHPCSDevCS standard for PHP Codesniffer

All notable changes to this project will be documented in this file.

This projects adheres to [Keep a CHANGELOG](http://keepachangelog.com/) and uses [Semantic Versioning](http://semver.org/).


## [Unreleased]

_Nothing yet._


## 1.1.3 - 2021-12-23

### Changed
- Updated the version constraints for [PHP_CodeSniffer] to `^3.6.2`.
- CI is now running on GitHub Actions.

### Fixed
- To prevent conflicting expectations between a newly introduced PSR12 sniff and this ruleset as it was, the new `PSR12.Classes.OpeningBraceSpace` sniff will be ignored.

## 1.1.2 - 2020-12-01

### Changed
- The few more token constant error codes for the `PHPCompatibility.Constants.NewConstants` sniff are excluded as the constants have been backfilled by PHPCS.

## 1.1.1 - 2020-09-03

### Changed
- The few more token constant error codes for the `PHPCompatibility.Constants.NewConstants` and `PHPCompatibility.Constants.RemovedConstants` sniffs are excluded as the constants are, or soon will be, backfilled by PHPCS.
- Updated the version constraints for the [PHPCompatibility] standard to allow for installing version `10.0` (currently in dev).

## 1.1.0 - 2020-09-03

### Added
- Short array syntax is now required by default via the `Generic.Arrays.DisallowLongArraySyntax` sniff.

### Changed
- The `Squiz.PHP.NonExecutableCode.ReturnNotRequired` code is excluded to allow for a `return` statement in an otherwise empty function (typical use: overloadable methods in an abstract class).
- The `PHPCompatibility.Constants.NewConstants.t_fnFound` code is excluded as the constant is backfilled by PHPCS since PHPCS 3.5.3.
- Updated the version constraints for the [Dealerdirect Composer PHPCS plugin]. The minimum supported version is now `0.4.1`, while the maximum is `^0.7` (latest release).
- Updated the inline ruleset documentation.

## 1.0.0 - 2020-02-12

Initial release.

[Dealerdirect Composer PHPCS plugin]: https://github.com/Dealerdirect/phpcodesniffer-composer-installer/
[PHP_CodeSniffer]: https://github.com/squizlabs/php_codesniffer/
[PHPCompatibility]: https://github.com/PHPCompatibility/PHPCompatibility

[Unreleased]: https://github.com/PHPCSStandards/PHPCSDevCS/compare/master...HEAD
[1.1.3]: https://github.com/PHPCSStandards/PHPCSDevCS/compare/1.1.2...1.1.3
[1.1.2]: https://github.com/PHPCSStandards/PHPCSDevCS/compare/1.1.1...1.1.2
[1.1.1]: https://github.com/PHPCSStandards/PHPCSDevCS/compare/1.1.0...1.1.1
[1.1.0]: https://github.com/PHPCSStandards/PHPCSDevCS/compare/1.0.0...1.1.0
