# Jexl Change Log
This project adheres to [Semantic Versioning](http://semver.org/).

## [Development]
Nothing yet!

## [v2.0.1]
### Fixed
- Issue where Jexl might mistake an identifier as being relative to a parent
when it should refer to the top level of the context in one specific case

## [v2.0.0]
### Changed
- The pre-minified Jexl has been removed; in modern times, frontend
webapps have their own build stack, and Jexl should't make assumptions
about the module format a frontend app wants to use.
- Support for Node 4 and earlier has been dropped.
- The codebase has been modernized to the subset of ES6 supported in
Node 6 LTS and beyond. Tests require Node 8 or later.
- The codebase has been shifted to Standard JS style.
- jexl.eval no longer accepts a callback function. Jexl is now promises-only.
- Tests have been converted to Jest to eliminate sneaky error swallowing

## [v1.1.4]
### Fixed
- Falsey identifiers are no longer treated as undefined

## [v1.1.3]
### Fixed
- Binary operators after nested identifiers were not balanced properly,
resulting in a broken expression/AST
- Gulp (or one of its plugins) had a breaking change in a minor release,
preventing the frontend build from running. This build method will be
removed from the next major version of Jexl. For now, Jexl is now version-
locked to the original gulp+plugins that worked.

## [v1.1.2]
### Changed
- Code coverage thresholds are now enforced through `gulp coverage-test`

### Fixed
- Operators found in identifier names (such as 'in' in 'incident') were being
tokenized separately from the rest of the identifier

## [v1.1.1]
### Fixed
- Minus did not denote a negative number at the start of a ternary's consequent
section

## [v1.1.0]
### Added
- The ability to define new binary and unary operators, or override existing
ones.
- The ability to delete existing binary and unary operators.

## [v1.0.2]
### Fixed
- Bad Gulpfile resulted in frontend dist falling out of sync. Fixed and
re-synced.

## [v1.0.1]
### Changed
- Refactored Parser and Evaluator. Both operations are now marginally faster.
- Removed balance tracking in favor of passing maps of token types at which
the sub-parser should stop.

### Fixed
- Object literals could not be defined in the consequent section of a ternary
expression.

## [v1.0.0]
### Added
- Object literals. Objects can now be defined inline with
`{standard: 'syntax'}`.
- Array literals. Arrays can also be defined with `["standard", 'syntax']`.
- The 'in' operator, for checking to see if a string appears inside a larger
string, or if an element exists in an array.
- Ternary expressions with `this ? "standard" : "syntax"`
- Ternary expressions with `alternate ?: "syntax"`

### Changed
- Simplified Grammar, reduced RAM footprint
- Dot notation can now be used to access properties of literals, such as
`"someString".length` or `{foo: 'bar'}.foo`.
- Transform syntax has changed. Arguments are now passed in parentheses, and
multiple arguments can be defined. Arguments are no longer limited to object
literals.

## [v0.2.0]
### Added
- "Divide and floor" operator: //
- Documentation outlining running expressions against XML.

## v0.1.0
### Added
- Initial release

[Development]: https://github.com/TomFrost/Jexl/compare/2.0.1...HEAD
[v2.0.1]: https://github.com/TomFrost/Jexl/compare/2.0.0...2.0.1
[v2.0.0]: https://github.com/TomFrost/Jexl/compare/1.1.4...2.0.0
[v1.1.4]: https://github.com/TomFrost/Jexl/compare/1.1.3...1.1.4
[v1.1.3]: https://github.com/TomFrost/Jexl/compare/1.1.2...1.1.3
[v1.1.2]: https://github.com/TomFrost/Jexl/compare/1.1.1...1.1.2
[v1.1.1]: https://github.com/TomFrost/Jexl/compare/1.1.0...1.1.1
[v1.1.0]: https://github.com/TomFrost/Jexl/compare/1.0.2...1.1.0
[v1.0.2]: https://github.com/TomFrost/Jexl/compare/1.0.1...1.0.2
[v1.0.1]: https://github.com/TomFrost/Jexl/compare/1.0.0...1.0.1
[v1.0.0]: https://github.com/TomFrost/Jexl/compare/0.2.0...1.0.0
[v0.2.0]: https://github.com/TomFrost/Jexl/compare/0.1.0...0.2.0
