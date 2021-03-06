# der-parser

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE-MIT)
[![Apache License 2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](./LICENSE-APACHE)
[![Build Status](https://travis-ci.org/rusticata/der-parser.svg?branch=master)](https://travis-ci.org/rusticata/der-parser)
[![Crates.io Version](https://img.shields.io/crates/v/der-parser.svg)](https://crates.io/crates/der-parser)

## Overview

der-parser is a parser for the DER protocol.

## Important

*This parser is still experimental and very incomplete*

## Changes

### 1.0.0

- Upgrade to nom 4

### 0.5.5

- Add functions `parse_der_u32` and `parse_der_u64` to quickly parse integers
- Remove `Oid::from_vec`, `Oid::from` does the same
- Enforce constraints on DER booleans

### 0.5.4

- Add `BitStringObject` to wrap BitString objects
- Mark constructed BitStrings as unsupported
- Do not try to parse application-specific data in `parse_der`

### 0.5.3

- Add function `DerObject::as_u64`
- Add function `DerObject::as_oid_val`
- Add `parse_der_struct!` variant to check tag

### 0.5.2

- Add functions to test object class and primitive/constructed state
- Add macro `parse_der_application!`
- Add macro `parse_der_tagged!` to parse `[x] EXPLICIT` or `[x] IMPLICIT` tagged values

### 0.5.1

- Add type GeneralString
- Add macro `parse_der_struct!`

### 0.5.0

- Allow use of crate without extra use statements
- Use constants for u32 errors instead of magical numbers
- Rename `tag_of_der_content()` to `DerObjectContent::tag`
- Rename DerElementxxx structs to have a consistent naming scheme
- Add documentation for parsing DER sequences and sets, and fix wrong return type for sets
- Fix a lot of clippy warnings
- QA: add pragma rules (disable unsafe code, unstable features etc.)
- More documentation
- Switch license to MIT + APLv2

### 0.4.4

- Add macro parse_der_defined_m, to parse a defined sequence or set
  This macro differs from `parse_der_defined` because it allows using macros
- Rename `DerObject::new_int` to `DerObject::from_int_slice`
- Rename `Oid::to_hex` to `Oid::to_string`
- Document more functions

### 0.4.1

- Add new feature 'bigint' to export DER integers
- OID is now a specific type
- Add new types T61String and BmpString
- Fix wrong expected tag in parse_der_set_of

### 0.4.0

- Der Integers are now represented as slices (byte arrays) since they can be larger than u64.

## License

Licensed under either of

 * Apache License, Version 2.0
   ([LICENSE-APACHE](LICENSE-APACHE) or http://www.apache.org/licenses/LICENSE-2.0)
 * MIT license
   ([LICENSE-MIT](LICENSE-MIT) or http://opensource.org/licenses/MIT)

at your option.

## Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in the work by you, as defined in the Apache-2.0 license, shall be
dual licensed as above, without any additional terms or conditions.
