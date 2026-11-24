# Changelog

All notable changes to this project will be documented in this file.

## [Unreleased]

### Changed
- Updated `README.md` with project overview, feature summary, and file structure.
- Added `CHANGELOG.md` to track project changes.

## [2026-11-24]

### Changed
- Extracted inline `<style>` rules and `#loginBtn` inline width styling from `index.html` into an external `styles.css` stylesheet linked from `index.html`.
- Restricted record deletion in the UI (`index.html`) to the configured administrator UID (`ADMIN_UID`).

### Added
- `styles.css` containing all responsive layout and component styles.
- `SETUP.md` documenting Firebase Authentication, Firestore setup, Spark plan considerations, hosting, and limitations.
- `index.html` with Firebase Authentication, Cloud Firestore (`farmRecords`) integration, overview stats, search, and 8 farm record tabs (Animals, Breeding, Health, Purchases & sales, Weights, Expenses, Deaths & losses, Feed stock).
- `firestore.rules` restricting read/write access on `/farmRecords/{recordId}` to authenticated users.
- Initial repository commit with `README.md`.
