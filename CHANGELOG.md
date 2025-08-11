# Changelog
All notable changes for Scriptable Sheets will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

Questions? Email us at [support@lunawolfstudios.com](mailto:support@lunawolfstudios.com)

## [1.7.2] - 2025-08-11
### Fixes
- Fixed header setting to allow more flexible matching on import, ignoring whitespace and case differences.

## [1.7.1] - 2025-07-08
### Fixes
- Fixed an ArgumentException when destroying Scriptable Objects immediately after they are created.
- Fixed a missing class attribute error when using Scriptable Objects as Sub Assets of non-ScriptableObject types.
- Fixed an issue where you could instantiate UnityEditorInternal types causing an error.
- Fixed an issue where you could query Scriptable Singletons causing an error.

## [1.7.0] - 2025-07-07
### Features
- Instances are now shown under their concrete base classes in addition to their instance type.
- Added pagination to the column visibility popup.
- New workload setting to specify the max number of properties to iterate over.
- Improved setup guidance and validation for Google Sheets Importers.
- Asset previews and thumbnails for root objects now display under the relevant Name column.

### Fixes
- Batch creating Scriptable Objects is now faster.
- Fixed a crash when iterating over arrays with thousands of elements.
- Fixed Google Sheets Importers not appearing under Assembly scan option.
- Fixed a gui layout error message when using the Assembly scan option.
- Improved performance of the column visibility popup.

## [1.6.0] - 2025-07-01
### Features
- New setting to adjust the row line height.
- New setting to toggle asset preview icons and thumbnails for object references.
- New setting to adjust the scale mode for asset previews.
- When editing text fields you can now add new lines with ctrl/cmd + enter.
- Tests have been moved into a new category called Scriptable Sheets.
- Google Sheets Importers now have an optional Scriptable Sheets window name field.
- Improved and added various tooltips for Google Sheets Importers.

### Fixes
- Fixed an issue when trying to rename binary files with smart paste.

## [1.5.1] - 2025-04-25
### Fixes
- Fixed an argument exception caused by restoring invalid sorted column indexes.
- Fixed an issue where column visibility toggles remained interactable after reaching the column limit.

## [1.5.0] - 2025-04-24
### Features
- Scriptable Sheets windows can now be renamed, opened, deleted, and cloned via the context menu.
- Session state cache now tracks and restores column widths.
- New popup for toggling column visibility, accessible via the context menu or by clicking the column limit indicator on the toolbar.
- New experimental setting to override rendering behavior per serialized property type.
- New setting to specify an escape option for wrapper characters within wrapped cells.
- Added a progress bar during Object scanning, with an option to disable it.
- Added support for finding assets under the Packages folder.
- Added support for creating ScriptableObjects under mutable Packages.
- Added support for deleting assets under mutable Packages.
- New scan path option to scan for Objects under both Assets and Packages.

### Fixes
- Auto select now triggers when changing types.
- Fixed auto select sometimes showing the wrong Object in the Inspector.
- Fixed an issue where sorting sometimes appeared out of sync for sub assets.
- Fixed an error caused by scrolling horizontally beyond the visible column limit.
- Improved handling of ScriptableObjects with different file extensions.
- Google Sheets Importers now properly handle double quotes that are escaped with repetition during import.

## [1.4.3] - 2025-03-10
### Fixes
- Fixed an issue where importing wrapped multiline content would fail.
- Fixed an issue where wrapped empty column data was being removed when using Google Sheets Importers.

## [1.4.2] - 2025-03-03
### Fixes
- Column headers now remain visible while scrolling.
- Row and column highlighting no longer disappear when scrolling.
- Missing Google Sheets Importers are now removed when rescanning for new ones.
- Google Sheets Importers now support optional Main Asset linking for Sub Assets.
- Prefabs and Materials can now be set as the default Main Asset for Sub Assets.
- Fixed a crash caused by importing a filename with invalid characters.
- Fixed issues with certain wrap options when exporting and importing AnimationCurve and Gradient values.
- Fixed an issue where the header row wasn't being detected when importing data.
- Improved flat file parsing to handle additional edge cases with wrapped values and Google Sheets Importers.

## [1.4.1] - 2025-02-26
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
