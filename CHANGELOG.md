# Changelog

All notable changes to Proxy Explorer are documented in this file.

## [1.1] - 2026-09-22

### Added

- Resolve two-letter ISO country codes to full country names using the Windows
  `GetGeoInfoEx` API. Names follow the current Windows user-interface language;
  unknown codes retain their normalized two-letter value.
- Distinguish proxies that merely return an HTTP response (`Reachable`) from
  proxies whose identity response was successfully validated (`Verified`).
- Include Windows file and product version information in the executable.
- Add automated run-state, country-name, layout and multi-DPI regression checks.

### Changed

- Updated the application, executable metadata, manifest, documentation and
  installer version from 1.0 to 1.1.
- Moved **Press F1 for help** to the upper-right header position previously used
  by the export command.
- Moved **Export usable list** beside **Load list and test** in the main action
  area.
- Increased the minimum width of the Country column to accommodate localized
  full country names.
- Limited proxy testing to a bounded pool of 24 concurrent workers, reducing
  thread and resource pressure when testing large candidate lists.
- Export now includes only identity-verified proxies. A reachable HTTP error,
  authentication response or unrelated page is no longer considered usable.
- Updated the discovery and proxy-test HTTP user-agent strings for version 1.1.
- Updated the integrated help and README to describe the revised controls,
  country display and result semantics.

### Fixed

- Prevented false address-disclosure detections caused by matching an IP address
  as a substring of another value; address checks now use token boundaries.
- Bounded identity-response downloads to 256 KiB to prevent unexpectedly large
  responses from consuming excessive memory.
- Corrected the icon verification test so project units are resolved reliably.

### Distribution and verification

- Updated the Inno Setup package name to
  `ProxyExplorer-1.1-Win64-Setup.exe` and its version metadata to `1.1.0.0`.
- Verified Win64 builds, parser and classification behavior, import/export and
  run-state behavior, icons, integrated help, and layouts at 96, 120, 144 and
  192 DPI.
- Verified PEPack payload and import-table integrity, packed startup, a live
  discovery/proxy test, and isolated current-user installer install/uninstall.

