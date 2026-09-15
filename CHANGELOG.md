# Changelog

All notable changes to this extension are documented here.
The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and versions follow [Semantic Versioning](https://semver.org/).

## [1.0.2] - 2026-09-15

### Fixed

- The element right after an open `<summary>` now always gets top spacing,
  even when its own top margin is reset by other styles.

## [1.0.1] - 2026-08-26

### Changed

- Folded `<details>` blocks no longer use a tinted background when open;
  they keep only the rounded border.

## [1.0.0] - 2026-08-17

### Added

- Styling for `<details>` / `<summary>` blocks in the Markdown preview:
  rounded border, tinted background when open, separator under the summary,
  and horizontal indentation for the expanded content.
- All colors come from VS Code theme variables, so the style follows the
  active light/dark theme.
