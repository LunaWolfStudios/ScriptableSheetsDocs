# Scriptable Sheets

## Table of Contents
- [Overview](#overview)
- [Core Features](#core-features)
- [User Interface](#user-interface)
- [Why Scriptable Sheets?](#why-scriptable-sheets)
- [Technical details](#technical-details)
- [Setup](#setup)
- [Toolbar Buttons](#toolbar-buttons)
- [Context Menu](#context-menu)
- [Column Context Menu](#column-context-menu)
- [Scriptable Sheets Settings](#scriptable-sheets-settings)
  - [Data Transfer Settings](#data-transfer-settings)
  - [Object Management Settings](#object-management-settings)
  - [User Interface Settings](#user-interface-settings)
  - [Workload Settings](#workload-settings)
  - [Experimental Settings](#experimental-settings)
  - [Google Sheets Importers](#google-sheets-importers)
- [Paste Pad](#paste-pad)
  - [Paste Pad Toolbar](#paste-pad-toolbar)
  - [Paste Pad Context Menu](#paste-pad-context-menu)
  - [Paste Pad Settings](#paste-pad-settings)
- [Tips](#tips)
  - [Additional Controls](#additional-controls)
  - [Advanced Search Filtering](#advanced-search-filtering)
  - [Data Serialization and Transfer](#data-serialization-and-transfer)
  - [External Tools](#external-tools)
  - [Performance](#performance)
  - [Unit Tests](#unit-tests)
  - [Unity](#unity)
- [Limitations / FAQ](#limitations--faq)
  - [Known Unity Bugs](#known-unity-bugs)
- [Samples](#samples)

## Overview
View your Unity assets in a whole new way. Scriptable Sheets revolutionizes Unity by integrating spreadsheet-like views for all your assets, boosting productivity and simplifying data management.

Inspect your assets in a table list asset explorer, where you can easily manage everything in one window. View and edit your ScriptableObjects, Prefabs, Components, and more. No need for endless searching through folders and Objects.

[Video Tutorials](https://www.youtube.com/playlist?list=PL6G9X1zrT3BLwLA7pbgM5Aam9RrLsrBZp)

Questions? Email us at [support@lunawolfstudios.com](mailto:support@lunawolfstudios.com)

## Core Features
- **Seamless Integration**: Instantly explore all your new and existing assets, including ScriptableObjects, in a spreadsheet-like view—no coding required.
- **Asset Management**: Select, read, update, and delete Unity Objects within Scriptable Sheets table list view.
- **Batch Create**: Quickly create multiple instances of any ScriptableObject type with a single click.
- **Import/Export**: Easily import CSV, TSV, and other flat file formats. Export to your preferred format, including Json, with options for headers, wrap settings, custom delimiters, and string-to-enum conversions.
- **Copy/Paste**: Copy entire tables, single columns, rows, or cells into any flat file format. Paste data seamlessly back into Scriptable Sheets, simplifying complex data transfers across serialized fields.
- **Serialization**: Visualize serializable classes, complex data, and serialized property types within a multi-column view.
- **Complex Data**: Handles complex Objects with inherited, nested, and generic fields.
- **Managed References**: Edit serialize reference fields with a per-row type dropdown and a column for every concrete subtype's fields.
- **Object References**: Supports Unity Object types such as AudioClips, Materials, Prefabs, ScriptableObjects, and more!
- **Collections**: View and edit serializable arrays and lists in the grid, or flip a single array or list into its own Table (not recommended for very large or deeply nested collections).
- **Read-only fields**: View Asset Paths, GUIDs, and read-only fields for any Unity Object.
- **Sub Assets**: Manage and filter Sub Assets for ScriptableObject types.
- **Addressable Assets**: Compatible with Addressable Asset References and their Sub Assets.
- **Prefab Components**: Filter, view, and edit Components attached to your Prefabs, including Transforms, Colliders, Rigidbodies, and more.

## User Interface
- **Keyboard Navigation**: Familiar spreadsheet-like navigation using tab, enter, shift, and arrow keys.
- **Search Filtering**: Search and filter Objects by directory, name, and even [advanced property-based filters](https://github.com/LunaWolfStudios/ScriptableSheetsDocs/blob/main/DOCUMENTATION.md#advanced-search-filtering). Includes additional search settings for case sensitivity and prefixes.
- **Pagination**: Navigate large amounts of Objects with intuitive controls for changing between pages.
- **Hide/Show Columns**: Hide or show specific columns to focus on the data that matters most to you.
- **Resizable Columns**: Adjust column widths to fit your data for a customized view. Includes preset buttons for stretching, compacting, and expanding columns.
- **Adjustable Row Height**: Change the row height to fit your content, including multiline text and asset previews like textures, materials, and models.
- **Sorting**: Sort Unity Objects by any column and property type in the table view, even colors, gradients, animation curves, and read-only fields.
- **Multiple Windows**: Open multiple Scriptable Sheet windows simultaneously, enabling efficient context switching between Unity Object types.
- **Recent Pins**: Recently viewed Unity Object types can be auto pinned for quick access.
- **Session Cache**: Retains the configuration of each Scriptable Sheet across sessions and code changes when possible, but user script modifications may alter results.
- **Lightweight Text Editor**: Includes 'Paste Pad', a lightweight text editor for a quick text editing within Unity.
- **Inspector Compatibility**: Automatically selects Objects in Unity's Inspector and Project windows as you navigate across table cells.
- **Theme Compatibility**: Compatible with both Unity light and dark themes.

## Why Scriptable Sheets?
- **Boost Productivity**: Streamline your workflow with a familiar spreadsheet-like interface tailored for Unity.
- **Powerful Data Editor**: Easily manage, edit, and transfer large amounts of data both in and out of Unity.
- **Advanced Customization**: Tailor Scriptable Sheets to your specific needs with an extensive list of settings and options to choose from.
- **No Coding Required**: Start using Scriptable Sheets right away without any coding and minimal setup. Scriptable Sheets automatically categorizes and organizes all your Unity Asset Types and serializable ScriptableObject types. To fully leverage all features of Scriptable Sheets, you will want to use Unity's ScriptableObjects. To learn more about ScriptableObjects in Unity, you can visit the official [Unity documentation](https://docs.unity3d.com/Manual/class-ScriptableObject.html).

Elevate your Unity development experience with Scriptable Sheets. Say goodbye to tedious data management and hello to a new level of efficiency and organization.

## Technical details
- **Full Source Code**: Power-users can customize Scriptable Sheets to fit their specific needs.
- **Samples**: Select from a variety of sample projects to see Scriptable Sheets in action and accelerate your learning curve with ScriptableObjects.
- **Unit Tests**: Ensure reliability and robustness with a comprehensive suite of unit tests.
- **User Settings**: Leverages the "UserSettings" folder for user-specific preferences.
- **Immediate Mode GUI**: Uses Unity's IMGUI system for specific features not yet available in UI Toolkit.
- **Editor Only:** Functions only in the Editor and is completely stripped in builds, except for the provided Samples.
- **Unity LTS Support**: Supports Unity LTS versions 2020.3 and up.

Get Scriptable Sheets today and transform the way you work with Unity assets!

## Setup
1. **Pre-requisites**:
   - Ensure you have imported these Unity packages:
     - `com.unity.nuget.newtonsoft-json`
     - `com.unity.test-framework`
2. **Source Control**:
   - If you are using source control, it is recommended to ignore the `UserSettings` folder under the root Unity project directory.
3. **Opening Scriptable Sheets**:
   - Navigate to `Window -> Scriptable Sheets` to open your first Scriptable Sheets window.
4. **Different Unity Asset Types**:
   - In the top left corner of the window, you can select the Unity asset types you'd like to explore in Scriptable Sheets. By default it'll be set to ScriptableObjects.
5. **Select Object Type**:
   - Use the next dropdown to select a serializable Object type that is of the Unity asset type you chose.
   - The available ScriptableObject types will be based on your selected Scan Option setting.
6. **Accessing Settings**:
   - To open settings, navigate to `Edit -> Project Settings -> Preferences -> Scriptable Sheets` or right-click the title of any Scriptable Sheets window and select "Open Settings Window".

## Toolbar Buttons
- **Edit New Asset Path**: Specify the folder where new assets are created.
- **Rescan**: Trigger a rescan operation to look for new assets created outside of Scriptable Sheets.
- **Pin**: Pins the Object Type to the toolbar.
- **Unpin**: Unpins the Object Type from the toolbar.
- **Unpin All**: Unpins all Object Types from the toolbar.
- **Show Columns**: Show all columns for the active Scriptable Sheet.
- **Hide Columns**: Hide all columns for the active Scriptable Sheet.
- **Stretch**: Stretch the cells to fit the view area.
- **Compact**: Compact the cells to minimum width.
- **Expand**: Expand the cells to fit headers.
- **Import File**: Import a file and apply the content across the entire table using the expected Data Transfer settings. Scriptable Sheets will attempt to auto-detect the format based on the file extension e.g. a '.csv' file will change the column delimiter to comma. You can also import json files by using the '.json' file extension. This will overwrite your Objects existing properties.
- **Copy to Clipboard**: Copy the entire table to the clipboard using the Data Transfer settings requested.
- **Copy Row to Clipboard**: Copy the selected row to the clipboard.
- **Copy Column to Clipboard**: Copy the selected column to the clipboard.
- **Smart Paste**: Perform a smart paste operation starting from the selected cell. This will go across pages if "Page Rows Only" is disabled, and into invisible columns if "Visible Columns Only" is disabled.
- **Import CSV from Google Sheets**: Import data directly from Google Sheets. This requires setting up [Google Sheets Importers](#google-sheets-importers).
- **Save to Disk**: Save the entire table using the expected Data Transfer settings. It will attempt to auto-detect the column delimiter based on the file format type, similar to importing. You can also save json files using the '.json' file extension.
- **New Paste Pad**: Open a new Paste Pad window.
- **First Page**: Navigate to the first page of Objects.
- **Previous Page**: Navigate to the previous page of Objects. Shortcut: Ctrl/Cmd + Left Arrow.
- **Next Page**: Navigate to the next page of Objects. Shortcut: Ctrl/Cmd + Right Arrow.
- **Last Page**: Navigate to the last page of Objects.
- **Select**: Select an Object in the Inspector and Project windows.
- **Delete**: Delete an Object from the editor.

## Context Menu
- **Open Recent Sheet**: Opens a recently closed Scriptable Sheets window. If none are available use 'New Sheet' instead.
- **New Sheet**: Opens a fresh Scriptable Sheets window. To open a recently closed Sheet use 'Open Recent Sheet' or navgiate to `Window -> Scriptable Sheets`.
- **Rename Sheet**: Opens a popup to rename the Scriptable Sheets window. A unique name is recommended, but not required.
- **Open Sheet**: Open a Scriptable Sheets window by name. Sheets with the same name are differentiated by their instance IDs. Cannot open a Sheet already opened.
- **Delete Sheet**: Delete a Scriptable Sheets window by name. Sheets with the same name are differentiated by their instance IDs. Cannot delete a Sheet that is opened.
- **Clone Sheet**: Creates and opens a copy of the selected Scriptable Sheets window by name. Sheets with the same name are differentiated by their instance IDs.
- **New Paste Pad Window**: Open a new Paste Pad window.
- **Open Settings Window**: Open the Scriptable Sheets Settings window.
- **Edit Column Visibility**: Opens a popup with toggles that enable or disable individual columns in the Scriptable Sheets editor window. Can also be opened by clicking the column limit indicator on the toolbar.
- **Copy**: Copies the Scriptable Sheet content this is identical to the 'Copy' button.
- **Copy Json**: Copy content as Json.

## Column Context Menu
- **Dock Column**: Docks the column so it remains visible while horizontally scrolling. Only the Actions and Name columns can be docked.
- **Hide Column**: Hides the column that was right-clicked.
- **Copy Column**: Copies the contents of the column to the clipboard. This behaves the same as focusing the column and using the Copy Column button.
- **Copy Property Path**: Copies the full serialized property path associated with the column. Disabled for the Collection Table Group Name, Index, and Value columns, which have no serialized property path.
- **Filter by property**: Clears the search bar and inserts a property filter for the selected column's property path, allowing you to quickly filter results based on that property. For the Collection Table Group Name, Index, and Value columns it inserts a column reference (such as `p:$B`) instead, since those columns have no property path.
- **Header Color**: Opens a color picker to tint the selected column's header label, updating in realtime as you adjust it. Available on every column, including the Actions column, and takes priority over the docked column color when set. Saved per column, type, and sheet.
- **Reset Header Color**: Clears the custom header color for the selected column, restoring the default. Only shown when a custom color is set.
- **Managed Type Columns**: Only shown on a `[SerializeReference]` column. Hover to reveal a toggle for every concrete subtype of the managed reference, all enabled by default. Toggling a subtype off hides the columns contributed by that subtype's fields and triggers a column refresh. This filters columns only, it does not hide any rows, so Objects assigned a disabled subtype still appear (their disabled fields simply have no columns). Shared fields remain visible as long as another enabled subtype declares them. The disabled subtypes are saved per column, type, and sheet.
- **Map Asset Preview**: Shown on any column for types with object reference properties, including Addressable Asset References. Hover to reveal those properties plus a Default option, and select one to replace that column's asset preview with the chosen reference's preview. Referenced ScriptableObjects expand into submenus so you can map a preview from a child Object's property, such as a Unit using its referenced Weapon's icon. How many levels of child ScriptableObjects are explored is controlled by the "Asset Preview Depth" under [Workload](#workload-settings). This gives each Object a distinct preview pulled from a reachable reference, such as a texture, material, or addressable. Only one source can be selected per column, Default restores the column's own preview, and rows whose reference is unassigned fall back to that default. Requires "Show Asset Previews" enabled with an increased "Row Line Height" to be visible. The selected sources are saved per type and sheet. The menu does not look into array or list elements, and it does not recurse through Addressable Asset References, so an Addressable can be used as a preview source but its own properties are not explored. The option is hidden while a Collection Table is active, since its mappings apply to owner level fields rather than the flattened element rows.

# Scriptable Sheets Settings

## Data Transfer Settings
Settings for handling data import and export.

- **Smart Paste**: Enhance pasting by distributing flat file data across table cells using the specified delimiters.
- **Headers**: Include header names when transferring flat file data. When enabled, the first row is discarded on import if it matches the header names (ignoring whitespace and letter casing).
- **Page Rows Only**: Restrict data transfer to the rows on the current page only.
- **Visible Columns Only**: Restrict data transfer to visible columns only.
- **Remove Empty Rows**: Remove empty rows when parsing flat file data.
- **Use String Enums**: Serialize enum values as their string names. For flat files and flat JSON only.
- **Ignore Case**: Ignore case when deserializing enum values from their string names.
- **Row Delim**: Delimiter to use when splitting rows.
- **Column Delim**: Delimiter to use when splitting columns.
- **Wrap Option**: Controls how cell values and headers are wrapped when transferring flat file data.
- **Escape Option**: Controls how characters inside a wrapped cell that match the wrapper are escaped.
  - **Backslash**: Adds a backslash before matching characters. Example: `"Hello\"World!"`
  - **Repeat**: Duplicates the matching character. Select this if working with Google Sheets. Example: `"Hello""World!"`
  - **Custom**: Custom sequence to add before matching characters.
- **Json Format**: Serialization format for importing and exporting Json.
  - **Flat**: Serializes the table elements as property paths and string values. Recommended for interchangeability between flat file formats. 
  - **Hierarchy**: Serializes the table elements using the Object type and utilizes a layered structure. Recommended for runtime processing.

## Object Management Settings
Settings for scanning, creating, and filtering Objects.

- **Auto Generate**: Automatically create new ScriptableObjects when importing or pasting more rows than there are existing Objects. Enough Objects are generated to match the row count, using the new Object naming and path settings above, before the data is parsed. This removes the need to manually count rows and create Objects beforehand. Only applies to creatable ScriptableObject types and only adds Objects, it never deletes existing Objects when there are fewer rows. When "Page Rows Only" is enabled only enough Objects are generated to fill the remaining room on the current page up to the "Rows Per Page" limit, since the parse is restricted to that page. For a single pass over an entire data set, disable "Page Rows Only" so generation and parsing span every row.
  - **Confirm Generation**: Display a confirmation message showing how many new Objects will be created before generating them.
- **Use Expansion**: Use variable expansion when naming newly created Objects.
  - **{i}**: Becomes the index value. The index value always starts at the specified "Starting Index" each time you create new Objects.
  - **{t}**: Becomes the type value. This is the default name used when creating a new Object.
- **Starting Index**: Starting index when using `{i}` for the index value.
- **Index Padding**: Ensures the index value has a minimum number of digits by adding leading zeros as needed when using `{i}`. For example setting this to `3` would ensure an index value with `3` digits like `001`.
- **New Object Name**: The name for newly created Objects. Defaults to the type name if left empty.
- **New Object Prefix**: Prefix for newly created Objects.
- **New Object Suffix**: Suffix for newly created Objects.
- **Default Main Asset**: New ScriptableObjects will be created as a Sub Asset of the specified default Main Asset.
- **Scanning**: Settings for Scanning Objects.
  - **Scan Option**: The method used when scanning or rescanning for ScriptableObject types and instances of those types.
    - **Default**: Scans for types based on existing instances of the selected Object type.
    - **Assembly**: Scans all assemblies for serializable ScriptableObject types. Use this to find ScriptableObject types that have not been created yet.
  - **Scan Path Option**: Controls how the "Scan Path" is selected.
    - **Default**: Lets you select any folder in Assets or Packages, with the root Assets folder selected by default.
    - **Assets**: Selects the Assets folder.
    - **Packages**: Selects the Packages folder.
    - **All**: Selects both the Assets and Packages folders.
  - **Scan Path**: The folder path to scan for Object instances. Use this to narrow your search and improve scan times.
  - **Show Progress Bar**: Display a progress bar during Object scanning.
  - **Root Prefabs Only**: Scan only for Components that are directly attached to root Prefab assets. When enabled nested Objects and their Components will be ignored. If disabled it's recommended to enable "Show Asset Path" to provide insight on which root asset you're changing.
  - **Hidden Sub Assets**: Scan hidden sub-assets that aren't shown under their main asset in the Project window. When disabled only visible sub-assets are scanned. When enabled hidden sub-assets are included, but any with a missing script will log a Unity warning that can't be suppressed (for example a URP Volume Profile's Volume Components).
  - **Excluded Paths**: Folders to exclude from asset scanning. Paths are case-insensitive and recursive. Must start from the root of the Unity project. Example: `Assets/MyFolder` or `Packages/MyPackage/`. Types discovered via Assembly "Scan Option" are included even if all their instances are in excluded folders. Rescan after changing exclusions.
  - **Excluded Full Type Names**: Full type names and namespaces to exclude from scanning. Types are case-insensitive and recursive. Example: `MyNamespace.MyScriptableObject`. Rescan after changing exclusions.
- **Searching**: Settings for searching Objects.
  - **Case Sensitive**: Search for Objects using exact letter casing.
  - **Starts With**: Search for Objects that start with the search text entered.

## User Interface Settings
Settings for the user interface, table layout, and table navigation.

- **Default Sheet Assets**: The default sheet asset types to display.
- **Auto Pin**: Auto pin Object types to the toolbar as they are selected.
- **Confirm Delete**: Display a warning message before deleting Objects.
- **Header Format**: The text format for the table header row.
  - **Default**: Uses Unity's default display names.
  - **Friendly**: Uses the display name and property path to generate quasi-identifiers that are easy-to-read.
  - **Advanced**: Uses the full property path as-is.
- **Lock Names**: Prevents directly editing the Object name field in the table view. Does NOT apply when pasting content or importing files. Does not apply to Collection Tables, which always lock their Group Name column.
- **Row Line Height**: The number of vertical lines each row will use in the table. Increase to allow more room for multiline content and larger asset previews.
- **Show Asset Previews**: Display asset previews and thumbnails in the table layout, including Addressable Asset References. Increase "Row Line Height" to scale the preview size.
- **Asset Preview Scale Mode**:
  - **Stretch To Fill**: Scales the texture to completely fill the preview.
  - **Scale And Crop**: Scales the texture to fit the target preview while preserving the aspect ratio. Parts of the texture may be cropped.
  - **Scale To Fit**: Scales the texture to fit entirely within the target preview while preserving the aspect ratio. Letterboxing may appear.
- **Show Row Index**: Display the row index next to each row.
- **Row Index Format**: When "Show Row Index" is enabled, choose how the row index is labeled.
  - **Alpha**: Spreadsheet style letters (A, B, C, ... AA, AB).
  - **Numeric**: The zero based row number.
- **Show Column Index**: Display the column index next to each column.
- **Column Index Format**: When "Show Column Index" is enabled, choose how the column index is labeled.
  - **Alpha**: Spreadsheet style letters (A, B, C, ... AA, AB).
  - **Numeric**: The zero based column number.
- **Show Children**: Display child Object fields. This includes deeply nested child Objects.
- **Show Arrays**: Display the elements of arrays and other collections as individual columns. Requires the "Show Children" setting to be enabled.
- **Override Array Size**: Enable to override the minimum number of columns displayed for each array. When disabled it will use the first non-sorted Objects array sizes. Disable to improve performance with arrays.
- **Best Fit Array Size**: Enable to use the largest array size found within all Objects for each array. Disable to improve performance with arrays. The maximum size is still capped by "Max Iterations" under Workload Settings.
- **Array Min Size**: Specify the minimum number of columns to display for arrays and other collections. Supports up to 5000 entries per array, with an additional column limit determined by "Max Iterations" under Workload Settings.
- **Show Asset Path**: Display the asset path for each Object.
- **Show GUID**: Display each Objects GUID.
- **Show Read-only**: Display read-only fields for each Object.
- **Collection Tables**: Enable a toolbar dropdown that expands a single array or list field into a table of rows, grouped by their owning Object, instead of displaying its elements as columns. Each element becomes a row and the element's fields become the columns. Top-level collections plus collections one level deep inside a serializable class are selectable. Selecting "None" from the dropdown keeps the default column behavior with no effect on the default view. "Show Children" and "Show Arrays" control whether nested fields and arrays appear within the table.
- **Managed References**: Display columns for the fields of every concrete subtype assigned to a serialize reference field, along with a per-row dropdown to view or change each Object's concrete type. Changing the type requires Unity 2021.2 or newer.
- **Sub Asset Filters**: Display a Sub Asset filter dropdown with all the Main Assets that contain the selected ScriptableObject type.
- **Table Navigation**: Settings for navigating the table view.
  - **Auto Scroll**: Auto updates the scroll view when scrolling with keyboard arrows.
  - **Auto Select**: Auto select the focused Object in the inspector.
  - **Highlight Alpha**: The highlight alpha for selected rows and columns.
  - **Highlight Row**: Highlight the selected row.
  - **Highlight Column**: Highlight the selected column.

## Workload Settings
Settings that affect computational performance. Modify with caution to optimize efficiency and responsiveness.

- **Auto Save**: Auto saves your changes. Recommended to disable for performance.
- **Auto Scan**: Auto scans the project for newly imported Objects. Recommended to disable for performance.
- **Auto Update**: Auto updates values as they are changed in the Inspector window.
- **Debug**: Display debug log messages in the console.
- **Virtualization**: Improves performance by rendering only the cells within the visible scroll area.
- **Asset Preview Depth**: How many levels of child ScriptableObject references the column header's "Map Asset Preview" menu explores when listing object reference properties whose preview can be shown. Higher values build larger menus.
- **Max Iterations**: Max number of properties to iterate over when generating the column layout. Raising this too high can cause hangs on large arrays or deeply nested Objects. This is in increments of 1000.
- **Max Visible Cells**: Total number of cells that can be visible at a time. Capped for performance.
- **Rows Per Page**: Max rows to display per page. Capped for performance.
- **Visible Column Limit**: Max columns to display at a time. Capped for performance.

## Experimental Settings
Settings that may cause unexpected behavior. Use at your own risk.

- **Rendering Overrides**: Serialized property types added here will override Scriptable Sheets' default rendering behavior, allowing the use of custom property drawers and attributes. This may disrupt the table layout or cause unexpected behavior. Use at your own risk.

## Google Sheets Importers

Google Sheets Importers allow you to import data with a single click from any Google Sheet that is accessible via a shared link.

### Creating Importers

1. **Create a new importer**
   - Right-click in the Project window and navigate to:
     `Create -> Scriptable Sheets -> Google Sheets Importer`
   - Alternatively, use Scriptable Sheets to create new importers.
   - Ensure each Google Sheets Importer is in an Editor only folder.

2. **Assign an Object type**
   - Assign the `MonoScript` associated with the desired Scriptable Object.
   - For non-ScriptableObject types you can enter the full type name such as `UnityEngine.GameObject` for Prefabs.
   - For Sub Assets you can assign an optional Main Asset, which is only needed if you want to group your Sheets by Main Asset.
   - This links the importer to the correct Object type.

3. **Enter the Google Sheet details**
   - Enter the "Sheet ID" found in your Google Sheets URL: `https://docs.google.com/spreadsheets/d/SHEET_ID`
   - Enter the "Sheet Name" found in your Google Sheet. This is **case-sensitive**, so ensure accuracy.
   - Ensure your Google Sheet's share settings are set to **"Anyone with the link"**.

4. **Repeat** for each Google Sheet you want to import, updating the "Sheet ID" and "Sheet Name" as necessary.

### Assigning Importers

1. Open **Scriptable Sheets Settings**.
2. Scroll down to **Google Sheets Importers**.
3. Click **Scan** to automatically detect and assign the importers.

### Importing Data

1. Ensure you have enough Scriptable Objects to match the rows in your Google Sheet.
   - By default Scriptable Sheets will **not** create new Scriptable Objects during import, so pre-create the correct number to match the rows.
   - Alternatively, enable "Auto Generate" under [Object Management](#object-management-settings) to create the missing Scriptable Objects automatically during import.

2. Select a Scriptable Object type in Scriptable Sheets that has an importer assigned.

3. Under Settings review your [Data Transfer Settings](#data-transfer-settings).
   - If the Google Sheet has headers ensure you enabled "Headers".
   - If you have multiple pages of Objects disable "Page Rows Only".
   - If you have exceeded the visible column limit disable "Visible Columns Only".

4. Click the `Import CSV from Google Sheets` button on the toolbar.
   - CSV import settings will be used with double quotes as the wrap option.
   
### Importer Properties

Each Google Sheets Importer must define how it maps Google Sheet data to Unity objects. The following fields are available when configuring an importer:

- **Full Type Name**: The fully qualified type name that this importer targets. Required for non-ScriptableObject types like `UnityEngine.GameObject` for prefabs.
- **Mono Script**: The `MonoScript` that defines the object type this importer targets. Required if the full type name is not set.
- **Main Asset**: Optional main asset to group this importer under. Useful for organizing Sub Assets when importing multiple types into one parent asset.
- **Collection Table Path**: Optional full property path of the collection field this importer targets, such as `m_Items` or `m_Items.m_Weapons`. When set, the importer is only used while that array or list field is expanded as a Collection Table under [User Interface](#user-interface-settings). Leave empty for importers that target the default whole-Object table.
- **Window Name**: Optional Scriptable Sheets window name that this importer targets. If set, this importer is only used when the window name matches the open Scriptable Sheets window name. If multiple importers target the same type, the importer without a window name will be used by default unless an importer with a matching window name is set.
- **Sheet ID**: The Sheet ID from the Google Sheets URL. The Google Sheets URL must be accessible via a shared link.
- **Sheet Name**: The name of the sheet tab inside the Google Sheet. This is case-sensitive and must match the tab name exactly.

# Paste Pad

Paste Pad is a lightweight text editor for Unity and included as part of Scriptable Sheets. You can open a new Paste Pad directly from the Scriptable Sheets Toolbar. You can have as many Paste Pad windows open as you'd like. Paste Pads do NOT persist across sessions. Use Paste Pad to hold various strings either copied from Scriptable Sheets or elsewhere. This text can be edited and pasted into a Scriptable Sheets table, row, column, or cell. All data in Scriptable Sheets can be exported as a string, making Paste Pad a powerful tool for quick edits.

## Paste Pad Toolbar
The toolbar provides quick access to the same actions as the context menu along with rich text formatting. Clearing and formatting are recorded with Unity's Undo system, so you can undo and redo them.

The rich text buttons wrap the selected text in Unity rich text tags supported by TextMesh Pro. The wrapped text stays selected so you can apply multiple tags in a row.
- **New**: Opens another Paste Pad window to start a new text.
- **Copy**: Copies the text to the clipboard.
- **Save**: Saves the text to a file.
- **Word Wrap**: Toggles word wrap for the text on or off.
- **Line Numbers**: Toggles line numbers on or off. The line numbers appear in a gutter on the left and are not part of the text.
- **B**: Wraps the selected text in bold tags.
- **I**: Wraps the selected text in italic tags.
- **Color**: Wraps the selected text in a color tag using the color from the adjacent color field.
- **Size**: Wraps the selected text in a size tag using the value from the adjacent size field.
- **Find**: Reports how many times the find text occurs in the text.
- **Replace**: Replaces every occurrence of the find text with the replace text.
- **Aa**: Toggles case sensitivity for find and replace. Find and replace always match exactly.
- **Clear**: Clears the text.

The find and replace fields expand as you type up to a maximum width.

## Paste Pad Context Menu
- **Clear**: Clears the text of the Paste Pad.
- **Copy**: Copies the text of the Paste Pad to the clipboard.
- **New**: Opens another Paste Pad window to start a new text.
- **Save**: Saves the text of the Paste Pad to a file.
- **Word Wrap**: Toggles word wrap for the text in the Paste Pad.
- **Open Settings Window**: Opens the Paste Pad Settings in a separate window.

## Paste Pad Settings
Paste Pad has its own settings, separate from the Scriptable Sheets settings, that define the defaults applied to each new Paste Pad window. Changing a setting in a Paste Pad window only affects that window. The defaults are stored per project under `UserSettings/PastePadSettings.asset`.

You can access the Paste Pad Settings in two ways:
- Select **Open Settings Window** from the Paste Pad context menu.
- Open `Edit -> Preferences -> Paste Pad` (or `Unity -> Settings -> Paste Pad` on macOS).

The following settings are available:
- **Word Wrap**: The default word wrap state for new Paste Pad windows.
- **Line Numbers**: The default line numbers state for new Paste Pad windows.
- **Default Color**: The default color used by the Paste Pad color button.
- **Default Size**: The default value used by the Paste Pad size button.
- **Case Sensitive**: The default case sensitivity for find and replace in new Paste Pad windows.

The settings page also includes the following actions:
- **Save Changes to Disk**: Flushes setting changes to disk.
- **Open File**: Opens the settings file directly with your preferred text editor.
- **Open Folder**: Opens the UserSettings folder for this project.
- **Reset Defaults**: Resets all Paste Pad settings to their default values. You cannot undo this action.
- **Open Window**: Opens the Paste Pad Settings in a separate window.

# Tips

## Additional Controls
- **Column Headers**: Right-click the column headers to hide/show them individually. Right-clicking a specific column header will also bring up additional [Column Context Menu](#column-context-menu) controls.
- **Context Menu**: Right-click the Window name to access the context menu in Unity. The context menu for the Scriptable Sheets window contains a number of shortcuts and features as outlined under the [Context Menu](#context-menu) section.
- **Editing Text**: Press 'ENTER' when editing an input field to get full control over the text position within the input field. Press 'ENTER' again to apply your changes. Press 'ESC' to cancel.
- **Multiline Text**: To add newlines in text fieds press 'ENTER' to select the text field then hold 'CTRL' or 'CMD' and press 'ENTER' again to add a newline.
- **Navigating Cells**: When a cell is focused you can navigate to the next cell with arrow keys, tab, or pressing enter twice (if you're in an input field). Hold shift to go in the opposite direction. The scroll view should automatically update as you scroll, but occassionally it can get stuck, especially in cases where the next cell is a null array element.
- **Play AudioClips**: AudioClip references and the AudioClip Sheet Asset Type display an inline play button to preview the clip. The button stays highlighted while playing; click it again to stop. Only one clip plays at a time, so playing another clip or letting the clip finish unhighlights the button.

## Advanced Search Filtering

By default, the search bar filters Objects by name. Scriptable Sheets also supports advanced expressions to filter Objects by GUID, asset path, and any Object properties.

- **GUID**: `g:` or `guid:` followed by a GUID will filter Objects where their GUID starts with or contains the specified string. Example `guid:f1a42`.
- **Asset Path**: `ap:`, `path:`, or `assetpath:` followed by an asset path will filter Objects with a matching asset path. Generally, you should start from the `Assets/` directory. Example `path:Assets/Samples/`.
- **Property**: `p:`, `prop:`, or `property:` followed by a full property path, a filter operation, and a value will perform an advanced property search. Examples include `p:health>30` or `prop:myColor==FF0000`.
  - **Filter Operations**:
    - `=` or `==` (equals)
    - `!=` (not equals)
    - `>` (greater than)
    - `<` (less than)
    - `>=` (greater than or equal to)
    - `<=` (less than or equal to)
	- `~=` or `=~` (contains)
	- `!~` or `~!` (does not contain)

Property searches can be performed on any column within Scriptable Sheets. Ensure you use the full property path, with exact casing, and avoid extra whitespace.

The contains filter operations will adhere to your "Search Settings". This allows you to filter for properties that match partial values.

When performing property searches on enums you can enable "Use String Enums" to filter enum values by string. Partial value searches do not work with string enum values.

To search for null Object references use a question mark character `?` as the filter value. Example `p:myObject=?`.

### Chaining Property Filters

Property filters can be chained together to match multiple conditions at once. Chain operators must be surrounded by spaces so they aren't confused with a literal `&` or `|` inside a value.

- `&` (and): all conditions must match. Example `p:damage>200 & health<10`.
- `|` (or): any condition can match. Example `p:rarity=Legendary | rarity=Epic`.

Only the first condition needs the `p:` (or `prop:`/`property:`) prefix; the rest are written as bare `propertyPath`, operation, and value. The `&` operator binds tighter than `|`, so `a & b | c & d` is evaluated as `(a & b) | (c & d)`.

Because chain operators require surrounding spaces, a value can still contain a literal `&` or `|` as long as it isn't space-padded. For example `p:name=this&that` matches the value `this&that` rather than chaining.

### Referencing Columns by Index

Instead of typing a full property path you can reference a column by its index using a `$` prefix. The reference resolves to that column's property path, so it can be used anywhere a property path is expected, including chained filters. Example `p:$E>0 | $B=hi`.

- **Alpha**: Spreadsheet style letters such as `$A`, `$B`, `$AA`. Letters are not case sensitive.
- **Numeric**: Zero based numbers such as `$0`, `$1`, `$5`.

Both forms are always accepted regardless of your "Column Index Format" setting. Enable "Show Column Index" to display each column's index in its header.

In a Collection Table the Group Name, Index, and Value columns have no serialized property path, so they can only be filtered through their column reference. For example `p:$B~=Boss` filters rows by their owning Object's name, `p:$C>=1` filters by element index, and on a leaf collection `p:$D~=fire` filters by element value.

## Data Serialization and Transfer
- **Double Quotes**: Google Sheets may not handle double quotes within cells correctly, leading to import/export issues. It's best to set "Escape Mode" to "Repeat" to ensure proper handling when using Google Sheets.
- **Export to Json**: You can export to Json using the context menu of the window menu 'Copy Json' option or by using the save button and changing the extension to '.json'.
- **Flat File Export/Import**: When exporting or importing a flat file, it will attempt to auto-detect the delimiter.
- **Newlines in Flat Files**: When importing flat files, ensure you're using the correct newlines. Typical default newlines are `\r\n` for Windows, `\n` for Linux, and `\r` for Mac. This is especially important when copy-pasting content directly.
- **New ScriptableObjects**: For a new ScriptableObject, you can use the 'Assembly' Scan Option to find all ScriptableObject types, even those that haven't been created.
- **Null Object References**: Object references that are null will appear as "null" when serialized to a flat file format. If they are part of an array and that index does not exist, they will appear as an empty string.
- **Serializable Attribute**: For Object types to be picked up by the 'Assembly' scan option, those Object types require the `System.Serializable` attribute.

## External Tools
- **Google Sheets**: Google Sheets uses '\t' delimiter for columns by default. If you are using a different delimiter in Scriptable Sheets, then you'll need to [split data into columns](https://support.google.com/docs/answer/6325535) after pasting into Google Sheets.
- **Line Endings**: Use a text editor like Notepad to change line endings to match your row delimiter setting before pasting content across cells. The Paste Pad Editor Window will default to '\n' for new lines entered directly. It will copy-paste '\r\n' accordingly.

## Performance
- **Complex Objects**: Avoid creating arrays of complex types within your ScriptableObject directly. Instead turn those complex types into their own ScriptableObjects. This not only improves performance within Scriptable Sheets, but also gives you another layer of organization. Under the provided RPG sample see how the Unit ScriptableObject references the Weapon ScriptableObject.
- **Large Arrays**: Large arrays will slow down performance. Consider moving larger arrays into a separate ScriptableObject and referencing that in your parent Object to improve performance. Under the Collections sample see how a StringCollection is created from a base ScriptableCollection.
- **Pagination**: Leverage row pagination to improve performance when working with a large number of Objects. You can still copy/paste and import/save across all rows and columns by disabling the "Page Rows only" and "Visible Columns Only" settings.
- **Show Arrays**: Disabling "Show Arrays" setting can improve performance when Objects have large arrays.
- **Show Children**: Disabling "Show Children" setting can improve performance when Objects have deeply nested fields. Note that "Show Children" must be enabled to show arrays.
- **Visible Columns**: You can right-click the column header to hide/show any column. There are also buttons on the left side to hide/show all columns at once. If the visible columns counter turns yellow that means the visible columns limit has been reached, but there are more columns to be displayed. You can increase this under `Settings -> Workload -> Visible Column Limit`.
- **Window Size and Virutalization**: If you have a lot of rows and columns, and hiding them is not an option. Then try shrinking the Window size so they aren't all rendered on every Repaint. The "Virtualization" setting will only render the cells in the Scroll View.

## Unit Tests
Scriptable Sheets includes several hundred Unit Tests that cover key parts of the tool. These tests ensure that everything is working as expected and can serve as helpful references if you're making your own modifications or extending functionality.

All tests are grouped under the "Scriptable Sheets" category in Unity’s Test Runner. If you prefer not to see them during testing, simply disable this category from the Test Runner UI.

To completely remove the Unit Tests from your project, you can delete the `Tests` folder located at `Packages/com.lunawolfstudios.scriptablesheets/Tests`.

## Unity
- **Additional Unity Types**: Additional Unity types like GUISkins and TimelineAssets can be found under the 'Assembly' Scan Option setting. If an instance of those types already exists then 'Default' Scan Option should pick them up as well. If you can't find a specific Unity Type it could be that it's nested under another type (e.g. Render Textures will be under Texture).
- **Addressable Asset References**: Under `Settings -> User Interface` you can toggle "Show Read-only" to view the the internal values of Addressable Asset References. To view the standard Object fields disable "Show Read-only".
- **Create Asset Menu Attribute**: You no longer need to include the 'CreateAssetMenu' attribute on your ScriptableObject classes.
- **New Object Detection**: When you select a new Object type, it will automatically detect the first folder any instance of that Object type appears in and set that as the asset path for newly created Objects of that type.
- **Paste Pad Context Menu**: The context menu of the Paste Pad window contains shortcuts for clearing, copying, saving, and toggling word wrap.
- **Recommended Layout**: Set up a layout with the Scriptable Sheets Settings window, the Scriptable Sheets window, and an Inspector window all side-by-side.
- **Unity 6**: All editor windows are created as floating windows at first. You can grab the inner window and drag it to dock it.

# Limitations / FAQ
- **Array Copying**: Does not support copying an entire array from the Inspector window and pasting it across the equivalent array cells in the Scriptable Sheets window. Use the copy row button within the Scriptable Sheets window instead.
- **Array Display**: When "Override Array Size" and "Best Fit" are disabled, the column layout is determined by the first non-sorted Object on the first page. For arrays, only indices up to that Object's array size will be displayed. This avoids performance issues when working with large numbers of Objects, arrays, or nested arrays. If you edit that Object's array size within the table view, the column layout will automatically refresh to reflect the new size. However, if the array size is changed externally (such as in the Inspector), the layout will not automatically update. You can adjust array display behavior under `Settings -> User Interface`.
- **Automatic Object Creation**: By default Scriptable Sheets will not create new Objects on import or paste, so any rows beyond the existing Objects are discarded. Enable "Auto Generate" under [Object Management](#object-management-settings) to automatically create enough ScriptableObjects to match the row count before parsing. It only applies to creatable ScriptableObject types and only adds Objects, never deletes them. With Auto Generate disabled, create the Objects ahead of time before importing.
- **Base64 Encoding**: Animation curves and gradients will be serialized as base64 strings when using wrap options that are unsupported with Json like double quotes.
- **Collection Tables**: Expand one array or list field into a table of rows, grouped by their owning Object. Top-level collections and collections one level deep inside a serializable class field are offered (not strings). Collections of records show a column per element field. Serialize reference elements show their subtype dropdown in the Value column alongside a column for every subtype's fields. The Group Name and Index columns are read-only, and the Group Name is always locked regardless of "Lock Names". On import, copy, and paste those two columns are still expected in the data (for example exported from column B) but are skipped, so they can never rename an owner, reindex an element, or add a new row. Nested element arrays are sized using "Best Fit" across every owner's elements. The Group Name column sorts the groups by name, while the Index and field columns sort the element rows within each group; like the rest of the table, sorting only reapplies when you change it, not while you edit fields. Adding an element gives the new serialize reference its own reference id, but serialize reference values nested inside that element still share their reference id with the element it was copied from. Property filters evaluate each element, so element rows can be filtered by element fields such as `p:m_Quantity>50`. Name, GUID, and asset path filters match the owning Object. Auto Generate and the global create button do not apply in this mode. Select "None" from the dropdown to return to the default column behavior.
- **Column Widths**: Column widths are persisted per column in Unity 2021.2 and newer. Older versions of Unity do not support this due to API limitations.
- **Copying Cells**: Copying a single cell will not include headers.
- **Formulas**: There are no formulas for filling cells.
- **Ignored Elements**: Custom property drawers, and property attributes are ignored within Scriptable Sheets, but should continue to work in Unity's Inspector windows. You can override this behavior using the "Rendering Overrides" setting under [Experimental Settings](#experimental-settings). Overriding the rendering behavior may disrupt the table layout, use with caution.
- **Inspector Fields**: Copying certain property fields from the Scriptable Sheets window does not always allow you to paste directly into the Inspector window. It is recommended to paste the value within the Scriptable Sheets window for it to work as expected.
- **Json Flat File Import**: When importing a Json flat file where you modified the number of array elements, ensure you update the size property both in Scriptable Sheets and in the file prior to import. Otherwise, the array values will be null.
- **Json Hierarchy Serialization**: The visible columns setting is ignored when using hierarchy Json serialization because it serializes the entire structure of each Object.
- **Json Import**: You cannot paste Json directly across the table, rows, or columns. You can paste Json into single cells for certain Object fields, Animation Curves, and Gradients with the caveat being that the Json was copied from the Inspector or Scriptable Sheets window. You can copy to Json, save to a Json file, or import from a Json file you exported.
- **JsonDotNet Converters**: JsonDotNet converters do not apply, such as `JsonConverter(typeof(StringEnumConverter))`. For String to Enum conversion, enable the "Use String Enums" setting.
- **Mixed Value Fields**: Certain mixed value fields on default UnityEngine Components will not render as a flagged enum within Scriptable Sheets. Due to the underlying backing field being inaccessible.
- **Multiline Text Fields**: When working with multiline strings you can adjust the "Row Line Height" under `Settings -> User Interface`.
- **Numeric Fields**: `uint` and `ulong` numeric fields are only supported on Unity versions 2022.1 and later.
- **Session Persistence**: The state of each Scriptable Sheets window has several values that are preserved, including selectable asset types, selected asset type, selected Object type, pinned Object types, and other fields. If you exit Unity or close a window, it will attempt to preserve the states of each window. The saved session will try to persist when the assembly recompiles, but cannot handle every possible change given the reflective nature of the tool. Especially if you added/removed a type, it might reset the window or swap an index within the UI.
- **Settings Persistence**: Settings between sessions are not persisted in Unity versions prior to 2020.1. For this reason, we recommend Unity 2020.3 and up.
- **Use String Enums**: Use String Enums does not apply to flagged enums unless it's a single value and you prefix the name with 'Enum:'. They also do not apply to various default UnityEngine Components.

## Known Unity Bugs
- **Inspector Layer Masks**: When trying to copy layer masks in the Inspector window of Unity, you may get an index out of range exception. It is recommended to copy/paste layer masks within Scriptable Sheets windows only.
- **Multiple Windows**: If you have multiple windows docked at the same position, the tab order or active windows themselves might get swapped when the states are reloaded. This occurs if their instance IDs have changed internally. This can happen when maximizing editor windows or restarting Unity. In some cases you'll need to re-open a docked tab that might have been replaced with a new one.
- **Paste Pad Text Editor**: The text editor caret in the Paste Pad window will go invisible when editing large amounts of text, making it hard to select certain areas of the text.
- **Preview Rendering**: When a gradient field uses a header attribute or a custom property drawer, the asset preview for the root name column may fail to display.

# Samples
You can import samples under `Window -> Package Manager` find 'LWS Scriptable Sheets' go to Samples, select which Sample you'd like to import and click 'Import'.

Each Sample folder contains demo assets for testing various use cases within the Scriptable Sheets window. Use these Samples to determine the functionality limits and performance within Scriptable Sheets for your specific use cases.

- **All Samples**
  - **Description**: Imports every sample listed below. If you select this, then do NOT import the other samples separately.
  - **Path**: `Samples~`

- **Collections**
  - **Description**: Shows how to manage arrays and lists as separate ScriptableObjects in order to maximize performance within the Scriptable Sheets Window. Also includes a CollectionTableSample with string, int, float, and custom record collections to demo Collection Tables.
  - **Path**: `Samples~/Collections`
  
- **Component Explorer**
  - **Description**: Includes sample Prefabs with nearly every Unity Component to see how various Components work with Scriptable Sheets.
  - **Path**: `Samples~/ComponentExplorer`

- **Component Presets**
  - **Description**: Shows how you can create backing ScriptableObject classes to drive data in MonoBehaviour components like Rigidbodies and Transforms.
  - **Path**: `Samples~/ComponentPresets`

- **Deep Inheritance**
  - **Description**: Includes sample ScriptableObjects to demo how Scriptable Sheets is able to flatten an Object hierarchy and show deeply nested fields, classes, interfaces, and generics. It also shows that property attributes like 'Header', 'Range', and 'TextArea' are ignored within the Scriptable Sheets window itself.
  - **Path**: `Samples~/DeepInheritance`

- **Localization**
  - **Description**: Shows how you can use the Scriptable Sheets window as a spreadsheet for your localized text. Demos how to display that text back in game by referencing the localized text ScriptableObjects.
  - **Path**: `Samples~/Localization`

- **RPG**
  - **Description**: Includes data driven ScriptableObjects you might see in an RPG game that include various Unity Object references and serialized property types.
  - **Path**: `Samples~/RPG`

- **Sampler**
  - **Description**: Includes a sampler ScriptableObject and Component that have nearly every serialized property type that is supported by Scriptable Sheets.
  - **Path**: `Samples~/Sampler`

- **Serialize Reference**
  - **Description**: Includes sample ScriptableObjects with polymorphic fields to show how Scriptable Sheets displays a per-row type dropdown and a column for every concrete subtype's fields.
  - **Path**: `Samples~/SerializeReference`

- **Sub Assets**
  - **Description**: Provides sample ScriptableObjects with Sub Assets to show how Sub Assets interact with Scriptable Sheets.
  - **Path**: `Samples~/SubAssets`
