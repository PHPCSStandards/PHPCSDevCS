# Change Log for the PHPCSDevCS standard for PHP Codesniffer

All notable changes to this project will be documented in this file.

This projects adheres to [Keep a CHANGELOG](http://keepachangelog.com/) and uses [Semantic Versioning](http://semver.org/).


## [Unreleased]

_Nothing yet._


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

[Unreleased]: https://github.com/PHPCSStandards/PHPCSDevCS/compare/1.1.0...HEAD
[1.1.0]: https://github.com/PHPCSStandards/PHPCSDevCS/compare/1.0.0...1.1.0
