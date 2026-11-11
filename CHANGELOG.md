# Changelog

All notable changes to this project will be documented in this file.

## [1.0.9] - 2026-11-11

### Fixed
- Guest checkout: `getInfoFromOrder()` now returns a full customer-like record with `meta` instead of a shortened object without `meta`, fixing `TypeError: Cannot read properties of undefined (reading 'firstname')` in the Magento Connector sidebar.
- Guest orders placed with an email that belongs to a registered customer now return the registered customer's full data.
- Guest records now include `website_id`, `website_name`, `total_sales`, `created_at`, `billing_address`, `shipping_address`, `is_guest`, and a plain-text address fallback when billing address is missing.

## [1.0.8] - 2026-09-03

### Security
- Fixed timing attack vulnerability in token comparison (replaced `==` with `hash_equals()`)
- Token generation now uses cryptographically secure `random_bytes()` instead of predictable `hash('sha256', time())`
- Removed stack trace exposure from API error responses (errors are now logged server-side only)
- Replaced direct `$_SERVER` access with Magento Request interface

### Added
- Default configuration values in `config.xml`
- This changelog file
- `.gitignore` file

### Fixed
- Typos in README.md
- XSS template warnings in renderer templates (bundle, downloadable, default) for Magento Marketplace EQP

## [1.0.7] - Previous release

- Initial public version