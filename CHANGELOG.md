# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).


## [Unreleased]

There are no changes yet.


## [1.0.1] - 2018-12-01

### Added

- Flow typings.


## [1.0.0] - 2018-07-26

### Changed

- **BREAKING**: Exporting only named exports.

    This change enable exporting `UbjsonEncoder` and `UbjsonDecoder`, so better utilization
    of tree-shaking is now possible ([#3](https://bitbucket.org/shelacek/ubjson/issues/3)).
      
    Please change

        import Ubjson from '@shelacek/ubjson';

    to

        import { Ubjson } from '@shelacek/ubjson';
  
    Now, you can also import `UbjsonEncoder`, `UbjsonDecoder`, `encode` and `decode` ;-).

- **BREAKING**: Some options refactoring ([#2](https://bitbucket.org/shelacek/ubjson/issues/2)).
    - `UbjsonDecoderOptions.useTypedArrays` defaults to `false`. Please allow it explicitly, if you
      used this behavior previously.
    - Renamed value `onlyTypedArray` of `UbjsonEncoderOptions.optimizeArrays` to `onlyTypedArrays`.


### Fixed

- Fix encoding of empty optimized containers.
- Respect `onlyTypedArrays` on encoding of non-8bit typed arrays. Previously it was serialized
  as standard not-optimized containers.


## [0.2.3] - 2018-07-22

### Fixed

- Fix encoding of non-8bit typed arrays.


## [0.2.2] - 2018-07-21

### Fixed

- Fix handling of no-op values.
- All option's properties are now optional in typings.
- Fix encoding of big integers > `int32` ([#1](https://bitbucket.org/shelacek/ubjson/issues/1)).


## [0.2.1] - 2018-07-18

### Changed

-  `README.md` updated only.


## [0.2.0] - 2018-07-17

### Changed

- **BREAKING**: Export static `Ubjson` class as default.

    Please change

        import { Ubjson } from '@shelacek/ubjson';
        // - or -
        const ubjson = require('@shelacek/ubjson').Ubjson;

    to

        import Ubjson from '@shelacek/ubjson';
        // - or -
        const ubjson = require('@shelacek/ubjson');


### Fixed

- Take `TextEncoder`/`TextDecoder` from `require('util')`, if they are not available globally.
  This makes it possible to use the library on the *node.js* >= 8 without polyfills.


## [0.1.1] - 2018-07-17

### Fixed

- Fix inappropriate promotion of `uint8` type to `int16` for STC.
- Fix encoding of typed arrays.
- Fix encoding of strongly typed containers.


## [0.1.0] - 2018-07-17

### Added

- Initial version.


[Unreleased]: https://bitbucket.org/shelacek/ubjson/branches/compare/master..v1.0.1
[1.0.1]: https://bitbucket.org/shelacek/ubjson/branches/compare/v1.0.1..v1.0.0
[1.0.0]: https://bitbucket.org/shelacek/ubjson/branches/compare/v1.0.0..v0.2.3
[0.2.3]: https://bitbucket.org/shelacek/ubjson/branches/compare/v0.2.3..v0.2.2
[0.2.2]: https://bitbucket.org/shelacek/ubjson/branches/compare/v0.2.2..v0.2.1
[0.2.1]: https://bitbucket.org/shelacek/ubjson/branches/compare/v0.2.1..v0.2.0
[0.2.0]: https://bitbucket.org/shelacek/ubjson/branches/compare/v0.2.0..v0.1.1
[0.1.1]: https://bitbucket.org/shelacek/ubjson/branches/compare/v0.1.1..v0.1.0
[0.1.0]: https://bitbucket.org/shelacek/ubjson/commits/tag/v0.1.0
