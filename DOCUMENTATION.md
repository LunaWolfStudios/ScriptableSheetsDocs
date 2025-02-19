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
- [Scriptable Sheets Settings](#scriptable-sheets-settings)
  - [Data Transfer Settings](#data-transfer-settings)
  - [Object Management Settings](#object-management-settings)
  - [User Interface Settings](#user-interface-settings)
  - [Workload Settings](#workload-settings)
  - [Google Sheets Importers](#google-sheets-importers)
- [Paste Pad](#paste-pad)
  - [Context Menu](#context-menu-1)
- [Tips](#tips)
  - [Additional Controls](#additional-controls)
  - [Advanced Search Filtering](#advanced-search-filtering)
  - [Data Serialization and Transfer](#data-serialization-and-transfer)
  - [External Tools](#external-tools)
  - [Performance](#performance)
  - [Unity](#unity)
- [Limitations / FAQ](#limitations--faq)
  - [Known Unity Bugs](#known-unity-bugs)
- [Samples](#samples)

## Overview
View your Unity assets in a whole new way. Scriptable Sheets revolutionizes Unity by integrating spreadsheet-like views for all your assets, boosting productivity and simplifying data management.

[Video Tutorials](https://www.youtube.com/playlist?list=PL6G9X1zrT3BLwLA7pbgM5Aam9RrLsrBZp)

Questions? Email us at [support@lunawolfstudios.com](mailto:support@lunawolfstudios.com)

## Core Features
- **Seamless Integration**: Directly integrates with existing ScriptableObjects and other Unity asset types, providing a cohesive experience inside the Unity Editor.
- **Asset Management**: Select, read, update, and delete Unity Objects within Scriptable Sheets table list view.
- **Batch Create**: Quickly create multiple instances of any ScriptableObject type with a single click.
- **Import/Export**: Easily import CSV, TSV, and other flat file formats. Export to your preferred format, including Json, with options for headers, wrap settings, custom delimiters, and string-to-enum conversions.
- **Copy/Paste**: Copy entire tables, single columns, rows, or cells into any flat file format. Paste data seamlessly back into Scriptable Sheets, simplifying complex data transfers across serialized fields.
- **Serialization**: Visualize serializable classes, complex data, and serialized property types within a multi-column view.
- **Complex Data**: Handles complex Objects with inherited, nested, and generic fields.
- **Object References**: Supports Unity Object types such as AudioClips, Materials, Prefabs, ScriptableObjects, and more!
- **Collections**: Basic support for serializable arrays and lists (not recommended for very large or deeply nested collections).
- **Read-only fields**: View Asset Paths, GUIDs, and read-only fields for any Unity Object.

## User Interface
- **Keyboard Navigation**: Familiar spreadsheet-like navigation using tab, enter, shift, and arrow keys.
- **Search Filtering**: Search and filter Objects by directory, name, or other property values. Includes additional search settings for case sensitivity and prefixes.
- **Pagination**: Navigate large amounts of Objects with intuitive controls for changing between pages.
- **Hide/Show Columns**: Hide or show specific columns to focus on the data that matters most to you.
- **Resizable Columns**: Adjust column widths to fit your data for a customized view. Includes preset buttons for stretching, compacting, and expanding columns.
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
   - Navigate to `Window -> Scriptable Sheets` to open your first Scriptable Sheets Window.
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
- **Previous Page**: Navigate to the previous page of Objects.
- **Next Page**: Navigate to the next page of Objects.
- **Last Page**: Navigate to the last page of Objects.
- **Select**: Select an Object in the Inspector and Project windows.
- **Delete**: Delete an Object from the editor.

## Context Menu
- **New Sheets Window**: Open a new Scriptable Sheets window.
- **New Paste Pad Window**: Open a new Paste Pad window.
- **Open Settings Window**: Open the Scriptable Sheets Settings window.
- **Copy**: Copies the Scriptable Sheet content this is identical to the 'Copy' button.
- **Copy Json**: Copy content as Json.

# Scriptable Sheets Settings

## Data Transfer Settings
- **Smart Paste**: Enhance pasting by distributing flat file data across table cells using the specified delimiters.
- **Headers**: Include header names when transferring flat file data.
- **Page Rows Only**: Restrict data transfer to the rows on the current page only.
- **Visible Columns Only**: Restrict data transfer to visible columns only.
- **Remove Empty Rows**: Remove empty rows when parsing flat file data.
- **Use String Enums**: Serialize enum values as their string names. For flat files and flat JSON only.
- **Ignore Case**: Ignore case when deserializing enum values from their string names.
- **Row Delim**: Delimiter to use when splitting rows.
- **Column Delim**: Delimiter to use when splitting columns.
- **Wrap Option**: Controls how cell values and headers are wrapped when transferring flat file data.
- **Json Format**: Serialization format for importing and exporting Json.
  - **Flat**: Serializes the table elements as property paths and string values. Recommended for interchangeability between flat file formats. 
  - **Hierarchy**: Serializes the table elements using the Object type and utilizes a layered structure.

## Object Management Settings
- **Use Expansion**: Use variable expansion when naming newly created Objects.
  - **{i}**: Becomes the index value. The index value always starts at the specified `Starting Index` each time you create new Objects.
  - **{t}**: Becomes the type value. This is the default name used when creating a new Object.
- **Starting Index**: Starting index when using `{i}` for the index value.
- **Index Padding**: Ensures the index value has a minimum number of digits by adding leading zeros as needed when using `{i}`. For example setting this to `3` would ensure an index value with `3` digits like `001`.
- **New Object Name**: The name for newly created Objects. Defaults to the type name if left empty.
- **New Object Prefix**: Prefix for newly created Objects.
- **New Object Suffix**: Suffix for newly created Objects.
- **Scan Option**: The method used when scanning or rescanning for ScriptableObject types and instances of those types.
  - **Default**: Scans for types based on existing instances of the selected Object type.
  - **Assembly**: Scans all assemblies for serializable ScriptableObject types. Use this to find ScriptableObject types that have not been created yet.
- **Scan Path**: The folder path to scan for Object instances. Use this to narrow your search and improve scan times.
- **Search**: Settings for searching Objects.
  - **Case Sensitive**: Search for Objects using exact letter casing.
  - **Starts With**: Search for Objects that start with the search text entered.

## User Interface Settings
- **Default Sheet Assets**: The default sheet asset types to display.
- **Auto Pin**: Auto pin Object types to the toolbar as they are selected.
- **Confirm Delete**: Display a warning message before deleting Objects.
- **Header Format**: The text format for the table header row.
  - **Default**: Uses Unity's default display names.
  - **Friendly**: Uses the display name and property path to generate quasi-identifiers that are easy-to-read.
  - **Advanced**: Uses the full property path as-is.
- **Lock Names**: Prevents directly editing the Object name field in the table view. Does NOT apply when pasting content or importing files.
- **Show Row Index**: Display the row index next to each row.
- **Show Column Index**: Display the column index next to each column.
- **Show Children**: Display child Object fields. This includes deeply nested child Objects.
- **Show Arrays**: Display the elements of arrays and other collections as individual columns. Requires the "Show Children" setting to be enabled.
- **Override Array Size**: Enable to override the number of columns displayed for each array.
- **Array Size**: Specify how many columns to display for arrays and other collections.
- **Show Asset Path**: Display the asset path for each Object.
- **Show GUID**: Display each Objects GUID.
- **Show Read-only**: Display read-only fields for each Object.
- **Table Navigation**: Settings for navigating the table view.
  - **Auto Scroll**: Auto updates the scroll view when scrolling with keyboard arrows.
  - **Auto Select**: Auto select the focused Object in the inspector.
  - **Highlight Alpha**: The highlight alpha for selected rows and columns.
  - **Highlight Row**: Highlight the selected row.
  - **Highlight Column**: Highlight the selected column.

## Workload Settings
- **Auto Save**: Auto saves your changes. Recommended to disable for performance.
- **Auto Scan**: Auto scans the project for newly imported Objects. Recommended to disable for performance.
- **Auto Update**: Auto updates values as they are changed in the Inspector window.
- **Debug**: Display debug log messages in the console.
- **Virtualization**: Improves performance by rendering only the cells within the visible scroll area.
- **Max Visible Cells**: Total number of cells that can be visible at a time. Capped for performance.
- **Rows Per Page**: Max rows to display per page. Capped for performance.
- **Visible Column Limit**: Max columns to display at a time. Capped for performance.

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

1. Ensure you have pre-created enough Scriptable Objects
   - Scriptable Sheets will **not** create new Scriptable Objects during import.
   - Make sure you have the correct number of Scriptable Objects to match the rows in your Google Sheet.

2. Select a Scriptable Object type in Scriptable Sheets that has an importer assigned.

3. If the Google Sheet has headers ensure you enabled "Headers" under [Data Transfer Settings](#data-transfer-settings).

4. Click the `Import CSV from Google Sheets` button on the toolbar.
   - CSV import settings will be used with double quotes as the wrap option.

# Paste Pad

Paste Pad is a lightweight text editor for Unity and included as part of Scriptable Sheets. You can open a new Paste Pad directly from the Scriptable Sheets Toolbar. You can have as many Paste Pad windows open as you'd like. Paste Pads do NOT persist across sessions. Use Paste Pad to hold various strings either copied from Scriptable Sheets or elsewhere. This text can be edited and pasted into a Scriptable Sheets table, row, column, or cell. All data in Scriptable Sheets can be exported as a string, making Paste Pad a powerful tool for quick edits.

## Context Menu
- **Clear**: Clears the text of the Paste Pad.
- **Copy**: Copies the text of the Paste Pad to the clipboard.
- **New**: Opens another Paste Pad window to start a new text.
- **Save**: Saves the text of the Paste Pad to a file.
- **Word Wrap**: Toggles word wrap for the text in the Paste Pad.

# Tips

## Additional Controls
- **Column Headers**: Right-click the column headers to hide/show them individually.
- **Context Menu**: Right-click the Window name to access the context menu in Unity. The context menu for the Scriptable Sheets Window contains shortcuts to copy as a flat file, copy directly as Json, open new windows, settings, and Paste Pads.
- **Editing Text**: Press 'ENTER' when editing an input field to get full control over the text position within the input field. Press 'ENTER' again to apply your changes. Press 'ESC' to cancel.
- **Navigating Cells**: When a cell is focused you can navigate to the next cell with arrow keys, tab, or pressing enter twice (if you're in an input field). Hold shift to go in the opposite direction. The scroll view should automatically update as you scroll, but occassionally it can get stuck, especially in cases where the next cell is a null array element.

## Advanced Search Filtering

By default, the search bar filters Objects by name. Scriptable Sheets also supports advanced expressions to filter Objects by GUID, asset path, and any Object properties.

- **GUID**: `g:` or `guid:` followed by a GUID will filter Objects where their GUID starts with the specified string. Example `guid:f1a42`.
- **Asset Path**: `ap:`, `path:`, or `assetpath:` followed by an asset path will filter Objects with a matching asset path. Generally, you should start from the `Assets/` directory. Example `path:Assets/Samples/`.
- **Property**: `p:`, `prop:`, or `property:` followed by a full property path, a filter operation, and a value will perform an advanced property search. Examples include `p:health>30` or `prop:myColor==FF0000`.
  - **Filter Operations**:
    - `=` or `==` (equals)
    - `!=` (not equals)
    - `>` (greater than)
    - `<` (less than)
    - `>=` (greater than or equal to)
    - `<=` (less than or equal to)

Property searches can be performed on any column within Scriptable Sheets. Ensure you use the full property path, with exact casing, and avoid extra whitespace.

When performing property searches on enums you can enable `Use String Enums` to filter enum values by string.

To search for null Object references use a question mark character `?` as the filter value. Example `p:myObject=?`.

## Data Serialization and Transfer
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

## Unity
- **Additional Unity Types**: Additional Unity types like GUISkins and TimelineAssets can be found under the 'Assembly' Scan Option setting. If an instance of those types already exists then 'Default' Scan Option should pick them up as well. If you can't find a specific Unity Type it could be that it's nested under another type (e.g. Render Textures will be under Texture).
- **Create Asset Menu Attribute**: You no longer need to include the 'CreateAssetMenu' attribute on your ScriptableObject classes.
- **New Object Detection**: When you select a new Object type, it will automatically detect the first folder any instance of that Object type appears in and set that as the asset path for newly created Objects of that type.
- **Paste Pad Context Menu**: The context menu of the Paste Pad window contains shortcuts for clearing, copying, saving, and toggling word wrap.
- **Recommended Layout**: Set up a layout with the Scriptable Sheets Settings window, the Scriptable Sheets window, and an Inspector window all side-by-side.
- **Unity 6**: All editor windows are created as floating windows at first. You can grab the inner window and drag it to dock it.

# Limitations / FAQ
- **Array Copying**: Does not support copying an entire array from the Inspector window and pasting it across the equivalent array cells in the Scriptable Sheets window. Use the copy row button within the Scriptable Sheets window instead.
- **Array Display**: The first non-sorted Object on the first page drives the column layout. When showing arrays, this means only up to that Object's array sizes will be displayed. This avoids performance issues with a large number of Objects, arrays, and nested arrays. If you edit any of this Objects array sizes in the table view it will auto-refresh the column layout with the new array sizes, but if you edit it externally like in the Inspector window it will not update the column layout. Under `Settings -> User Interface` you can toggle "Show Arrays" followed by "Override Size", and then set a specific number of indices to display for each array.
- **Arrow Key Navigation**: Cannot navigate with arrow keys across missing cells when array sizes differ.
- **Automatic Object Creation**: Scriptable Sheets will not automatically create new Objects on import. Create Objects ahead of time before importing.
- **Copying Cells**: Copying a single cell will not include headers.
- **Formulas**: There are no formulas for filling cells.
- **Ignored Elements**: Managed references, custom property drawers, and property attributes are ignored within Scriptable Sheets, but should continue to work in Unity's Inspector windows.
- **Inspector Fields**: Copying certain property fields from the Scriptable Sheets window does not always allow you to paste directly into the Inspector window. It is recommended to paste the value within the Scriptable Sheets window for it to work as expected.
- **Json Flat File Import**: When importing a Json flat file where you modified the number of array elements, ensure you update the size property both in Scriptable Sheets and in the file prior to import. Otherwise, the array values will be null.
- **Json Hierarchy Serialization**: The visible columns setting is ignored when using hierarchy Json serialization because it serializes the entire structure of each Object.
- **Json Import**: You cannot paste Json directly across the table, rows, or columns. You can paste Json into single cells for certain Object fields, Animation Curves, and Gradients with the caveat being that the Json was copied from the Inspector or Scriptable Sheets Window. You can copy to Json, save to a Json file, or import from a Json file you exported.
- **JsonDotNet Converters**: JsonDotNet converters do not apply, such as `JsonConverter(typeof(StringEnumConverter))`. For String to Enum conversion, enable the "Use String Enums" setting.
- **Multiline Strings**: The recommended best practice for multiline strings would be to encode/decode them manually using `\n` or `<br>`. If that is not possible your next option is to ensure Smart Paste is enabled and Row Delimiter is not set to a newline, carriage return, or any other string that is used in your content. You can then use Paste Pad to edit multiline content and paste it back into the cell. You could even split your multiline strings with the unique Row Delimiter to bulk import content across cells that each contain multilines.
- **Numeric Fields**: `uint` and `ulong` numeric fields are only supported on Unity versions 2022.1 and later.
- **Session Persistence**: The state of each Scriptable Sheets window has several values that are preserved, including selectable asset types, selected asset type, selected Object type, pinned Object types, and other fields. If you exit Unity or close a window, it will attempt to preserve the states of each window. The saved session will try to persist when the assembly recompiles, but cannot handle every possible change given the reflective nature of the tool. Especially if you added/removed a type, it might reset the window or swap an index within the UI.
- **Settings Persistence**: Settings between sessions are not persisted in Unity versions prior to 2020.1. For this reason, we recommend Unity 2020.3 and up.
- **Use String Enums**: Use String Enums does not apply to flagged enums unless it's a single value and you prefix the name with 'Enum:'.

## Known Unity Bugs
- **Inspector Layer Masks**: When trying to copy layer masks in the Inspector window of Unity, you may get an index out of range exception. It is recommended to copy/paste layer masks within Scriptable Sheets windows only.
- **Multiple Windows**: If you have multiple windows docked at the same position, their tab order might get swapped when the states are reloaded if their instance IDs have changed internally. This can happen when maximizing editor windows or restarting Unity.
- **Paste Pad Text Editor**: The text editor caret in the Paste Pad window will go invisible when editing large amounts of text, making it hard to select certain areas of the text.

# Samples
You can import samples under `Window -> Package Manager` find 'LWS Scriptable Sheets' go to Samples, select which Sample you'd like to import and click 'Import'.

Each Sample folder contains demo assets for testing various use cases within the Scriptable Sheets window. Use these Samples to determine the functionality limits and performance within Scriptable Sheets for your specific use cases.

- **All Samples**
  - **Description**: Imports every sample listed below. If you select this, then do NOT import the other samples separately.
  - **Path**: `Samples~`

- **Collections**
  - **Description**: Shows how to manage arrays and lists as separate ScriptableObjects in order to maximize performance within the Scriptable Sheets Window.
  - **Path**: `Samples~/Collections`

- **Component Presets**
  - **Description**: Shows how you can create backing ScriptableObject classes to drive data in MonoBehaviour components like Rigidbodies and Transforms.
  - **Path**: `Samples~/ComponentPresets`

- **Deep Inheritance**
  - **Description**: Includes sample ScriptableObjects to demo how Scriptable Sheets is able to flatten an Object hierarchy and show deeply nested fields, classes, interfaces, and generics. It also shows that property attributes like 'Header', 'Range', and 'TextArea' are ignored within the Scriptable Sheets Window itself.
  - **Path**: `Samples~/DeepInheritance`

- **Localization**
  - **Description**: Shows how you can use the Scriptable Sheets Window as a spreadsheet for your localized text. Demos how to display that text back in game by referencing the localized text ScriptableObjects.
  - **Path**: `Samples~/Localization`

- **RPG**
  - **Description**: Includes data driven ScriptableObjects you might see in an RPG game that include various Unity Object references and serialized property types.
  - **Path**: `Samples~/RPG`

- **Sampler**
  - **Description**: Includes a sampler ScriptableObject that has nearly every serialized property type that is supported by Scriptable Sheets.
  - **Path**: `Samples~/Sampler`
