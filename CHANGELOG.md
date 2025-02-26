# Changelog
All notable changes for Scriptable Sheets will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

Questions? Email us at [support@lunawolfstudios.com](mailto:support@lunawolfstudios.com)

## [1.4.1] - 2025-02-27
### Fixes
- Improved support for Addressable Asset References and their Sub Assets.
- Improved friendly header formatting for serialized fields that use backing field attributes.

## [1.4.0] - 2025-02-25
### Features
- Default Scan Option now detects and includes Sub Assets of ScriptableObjects and Prefab Components.
- Filter, view, and edit Components attached to your Prefabs, including Transforms, Colliders, Rigidbodies, and more.
- Manage and filter Sub Assets for ScriptableObject types.
- New setting to toggle Sub Asset filters.
- New setting for creating ScriptableObjects as Sub Assets under a specified Main Asset.
- New Samples to showcase ScriptableObject Sub Assets and Prefab Components.
- New search filter operations for contains `~=` and does not contain `!~`.

### Fixes
- Sub Assets can now be deleted without deleting the Main Asset.
- Fixed an IOException that occurred when creating assets due to an invalid asset path from Sub Assets.
- Fixed an issue where some of the Unity built-in assets were not being found.
- Properly defaults to the correct Sheet Asset primary type when no types are pinned.
- Fixed lag when performing an advanced filter on an unsupported property type.
- Fixed an issue where PhysicsMaterials weren't being found in Unity 6 and up.

## [1.3.0] - 2025-02-19
### Features
- Session state cache now restores visible columns and the sorted column index.
- Single click import from Google Sheets that are viewable by anyone with the link.

### Fixes
- Fixed a 'missing class attribute' error when using Override Array Size with non-ScriptableObject types.

## [1.2.1] - 2024-09-26
### Fixes
- Fixed an issue where TextFields in custom editor windows were not stretching properly.

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
