# Changelog
All notable changes for Scriptable Sheets will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

Questions? Email us at [support@lunawolfstudios.com](mailto:support@lunawolfstudios.com)

## [1.2.0] - 2024-09-25
### Features
- New settings to override column display count for arrays and collections.
- New setting to override the starting index when creating new Objects.
- New setting for index padding when creating new Objects.
- New setting to prevent direct editing of Object names.
- Session state cache now restores the last Window closed.

### Fixes
- Fixed issue with editing cells introduced in Unity 2022.3.44f1 and 6000.0.16f1.
- Improved sorting for strings containing numbers.

### Refactors
- Moved row line height to a constant in the SheetLayout script.

## [1.1.1] - 2024-07-31
### Fixes
- Resolved issues with creating new Scriptable Objects in empty projects using the Assembly scan option.

## [1.1.0] - 2024-07-30
### Features
- Added advanced search filtering by guid, asset path, and other property values.
- Enhanced animation curve comparison and sorting.

### Fixes
- Resolved unit test failures related to culture-specific float value conversions.

## [1.0.0] - 2024-07-24
Initial release.
