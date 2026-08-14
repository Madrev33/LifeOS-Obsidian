# Documentação Completa

**URL Original**: /
**Data**: 28/05/2025 20:48:50
**Estratégia**: BFS
**Extraído com**: Crawl4AI - Madrev Edition

---


# Meta Bind Docs
Tip
**New** : Meta Bind Buttons, a spiritual successor to the discontinued Buttons Plugin.
Meta Bind is a plugin for Obsidian to make your notes interactive!
Meta Bind allows you to create **input fields** , **metadata displays (view fields)** , and **buttons**. Input and view fields can bind to frontmatter properties, which keeps them in sync those frontmatter properties, allowing you to view and edit your frontmatter properties inside your notes.
For example, you can create a toggle inside your note, that is bound to a frontmatter property named `done`, with this simple inline code block `INPUT[toggle:done]`. When you click the toggle, the `done` property will switch between `true` and `false`.
## Features
Section titled “Features”
  * **Input Fields** - Input and edit frontmatter properties from anywhere inside your notes. Properties will update in real time.
  * **View Fields** - Display frontmatter properties inside your notes. The displayed value will update in real time when the properties displayed change.
  * **Buttons** - Create buttons inside your notes that can trigger actions on click. A spiritual successor to the discontinued Buttons Plugin.
  * **Meta Bind Embed** - Seamlessly embed a note inside another note. The embedded note will be rendered as if it was part of the note it is embedded in.


## Getting Started
Section titled “Getting Started”
First you will need to install the plugin from the Community Plugins tab in Obsidian’s settings. You can find various guides on how to use the plugin under the Guides section in the sidebar.
If you want to see all possible input fields in actions, you can run the `Open Meta Bind Playground` command inside Obsidian. If you are looking for examples, you can explore the example vault which I use for testing.
## Bugs, Errors or Unexpected Behavior?
Section titled “Bugs, Errors or Unexpected Behavior?”
Please open a bug report on the plugins GitHub repository.
## Have an Idea for a new Feature?
Section titled “Have an Idea for a new Feature?”
Feature requests and contributions are always welcome. If you have an idea, feel free to open a feature request under the issues tab on GitHub or even create a pull request.
## Check out my Other Work
Section titled “Check out my Other Work”
Check out my website.
Here is a list of my Obsidian related projects.
  * Meta Bind Plugin (You are here)
  * JS Engine Plugin
  * Shiki Highlighter Plugin
  * Media DB Plugin
  * Lemons Theme
  * Focus Theme
  * Obsidian Stats
  * Obsidian Collection


================================================================================

## 3. /api/enumerations/bindtargetstoragetype

(/api/enumerations/bindtargetstoragetype/#_top)  
# BindTargetStorageType
Defined in: packages/core/src/parsers/bindTargetParser/BindTargetDeclaration.ts:29
## Enumeration Members
Section titled “Enumeration Members”
Enumeration Member | Value | Defined in  
---|---|---  
`FRONTMATTER` |  `"frontmatter"` |  packages/core/src/parsers/bindTargetParser/BindTargetDeclaration.ts:30  
`GLOBAL_MEMORY` |  `"globalMemory"` |  packages/core/src/parsers/bindTargetParser/BindTargetDeclaration.ts:32  
`MEMORY` |  `"memory"` |  packages/core/src/parsers/bindTargetParser/BindTargetDeclaration.ts:31  
`SCOPE` |  `"scope"` |  packages/core/src/parsers/bindTargetParser/BindTargetDeclaration.ts:33


================================================================================

## 4. /api/enumerations/buttonstyletype

(/api/enumerations/buttonstyletype/#_top)  
# ButtonStyleType
Defined in: packages/core/src/config/ButtonConfig.ts:3
## Enumeration Members
Section titled “Enumeration Members”
Enumeration Member | Value | Description | Defined in  
---|---|---|---  
`DEFAULT` |  `"default"` |  Default grey button |  packages/core/src/config/ButtonConfig.ts:7  
`DESTRUCTIVE` |  `"destructive"` |  Red button for destructive actions |  packages/core/src/config/ButtonConfig.ts:15  
`PLAIN` |  `"plain"` |  Plain button with no background |  packages/core/src/config/ButtonConfig.ts:19  
`PRIMARY` |  `"primary"` |  Primary button in the accent color |  packages/core/src/config/ButtonConfig.ts:11


================================================================================

## 5. /api/enumerations/renderchildtype

(/api/enumerations/renderchildtype/#_top)  
# RenderChildType
Defined in: packages/core/src/config/APIConfigs.ts:12
## Enumeration Members
Section titled “Enumeration Members”
Enumeration Member | Value | Defined in  
---|---|---  
`BLOCK` |  `"block"` |  packages/core/src/config/APIConfigs.ts:14  
`INLINE` |  `"inline"` |  packages/core/src/config/APIConfigs.ts:13


================================================================================

## 6. /api/enumerations/inputfieldtype

(/api/enumerations/inputfieldtype/#_top)  
# InputFieldType
Defined in: packages/core/src/config/FieldConfigs.ts:23
## Enumeration Members
Section titled “Enumeration Members”
Enumeration Member | Value | Defined in  
---|---|---  
`DATE` |  `"date"` |  packages/core/src/config/FieldConfigs.ts:30  
`DATE_PICKER` |  `"datePicker"` |  packages/core/src/config/FieldConfigs.ts:32  
`DATE_TIME` |  `"dateTime"` |  packages/core/src/config/FieldConfigs.ts:44  
`EDITOR` |  `"editor"` |  packages/core/src/config/FieldConfigs.ts:35  
`IMAGE_LIST_SUGGESTER` |  `"imageListSuggester"` |  packages/core/src/config/FieldConfigs.ts:43  
`IMAGE_SUGGESTER` |  `"imageSuggester"` |  packages/core/src/config/FieldConfigs.ts:36  
`INLINE_LIST` |  `"inlineList"` |  packages/core/src/config/FieldConfigs.ts:42  
`INLINE_LIST_SUGGESTER` |  `"inlineListSuggester"` |  packages/core/src/config/FieldConfigs.ts:41  
`INLINE_SELECT` |  `"inlineSelect"` |  packages/core/src/config/FieldConfigs.ts:38  
`INVALID` |  `"invalid"` |  packages/core/src/config/FieldConfigs.ts:46  
`LIST` |  `"list"` |  packages/core/src/config/FieldConfigs.ts:39  
`LIST_SUGGESTER` |  `"listSuggester"` |  packages/core/src/config/FieldConfigs.ts:40  
`MULTI_SELECT` |  `"multiSelect"` |  packages/core/src/config/FieldConfigs.ts:29  
`NUMBER` |  `"number"` |  packages/core/src/config/FieldConfigs.ts:33  
`PROGRESS_BAR` |  `"progressBar"` |  packages/core/src/config/FieldConfigs.ts:37  
`SELECT` |  `"select"` |  packages/core/src/config/FieldConfigs.ts:28  
`SLIDER` |  `"slider"` |  packages/core/src/config/FieldConfigs.ts:25  
`SUGGESTER` |  `"suggester"` |  packages/core/src/config/FieldConfigs.ts:34  
`TEXT` |  `"text"` |  packages/core/src/config/FieldConfigs.ts:26  
`TEXT_AREA` |  `"textArea"` |  packages/core/src/config/FieldConfigs.ts:27  
`TIME` |  `"time"` |  packages/core/src/config/FieldConfigs.ts:31  
`TOGGLE` |  `"toggle"` |  packages/core/src/config/FieldConfigs.ts:24


================================================================================

## 7. /api/classes/noteposition

(/api/classes/noteposition/#_top)
# NotePosition
Defined in: packages/core/src/config/APIConfigs.ts:62
## Constructors
Section titled “Constructors”
### Constructor
Section titled “Constructor”
> **new NotePosition**(`linePosition`): `NotePosition`
Defined in: packages/core/src/config/APIConfigs.ts:65
#### Parameters
Section titled “Parameters”
Parameter | Type  
---|---  
`linePosition` |  `undefined` | `LinePosition`  
#### Returns
Section titled “Returns”
`NotePosition`
## Properties
Section titled “Properties”
### linePosition
Section titled “linePosition”
> **linePosition** : `undefined` | `LinePosition`
Defined in: packages/core/src/config/APIConfigs.ts:63
## Methods
Section titled “Methods”
### getPosition()
Section titled “getPosition()”
> **getPosition**(): `undefined` | `LinePosition`
Defined in: packages/core/src/config/APIConfigs.ts:69
#### Returns
Section titled “Returns”
`undefined` | `LinePosition`


================================================================================

## 8. /api/enumerations/fieldtype

(/api/enumerations/fieldtype/#_top)  
# FieldType
Defined in: packages/core/src/config/APIConfigs.ts:17
## Enumeration Members
Section titled “Enumeration Members”
Enumeration Member | Value | Defined in  
---|---|---  
`BUTTON` |  `"BUTTON"` |  packages/core/src/config/APIConfigs.ts:23  
`BUTTON_GROUP` |  `"BUTTON_GROUP"` |  packages/core/src/config/APIConfigs.ts:22  
`EMBED` |  `"EMBED"` |  packages/core/src/config/APIConfigs.ts:24  
`EXCLUDED` |  `"EXCLUDED"` |  packages/core/src/config/APIConfigs.ts:25  
`INPUT` |  `"INPUT"` |  packages/core/src/config/APIConfigs.ts:18  
`JS_VIEW` |  `"JS_VIEW"` |  packages/core/src/config/APIConfigs.ts:20  
`TABLE` |  `"TABLE"` |  packages/core/src/config/APIConfigs.ts:21  
`VIEW` |  `"VIEW"` |  packages/core/src/config/APIConfigs.ts:19


================================================================================

## 9. /api/classes/fieldmountable

(/api/classes/fieldmountable/#_top)
# FieldMountable
Defined in: packages/core/src/fields/FieldMountable.ts:4
## Extends
Section titled “Extends”


## Constructors
Section titled “Constructors”
### Constructor
Section titled “Constructor”
> **new FieldMountable**(`mb`, `uuid`, `filePath`): `FieldMountable`
Defined in: packages/core/src/fields/FieldMountable.ts:9
#### Parameters
Section titled “Parameters”
Parameter | Type  
---|---  
`mb` |  `MetaBind`  
`uuid` |  `string`  
`filePath` |  `string`  
#### Returns
Section titled “Returns”
`FieldMountable`
#### Overrides
Section titled “Overrides”
`Mountable`.`constructor`
## Properties
Section titled “Properties”
### mb
Section titled “mb”
> `readonly` **mb** : `MetaBind`
Defined in: packages/core/src/fields/FieldMountable.ts:5
## Methods
Section titled “Methods”
### getFilePath()
Section titled “getFilePath()”
> **getFilePath**(): `string`
Defined in: packages/core/src/fields/FieldMountable.ts:21
#### Returns
Section titled “Returns”
`string`
### getTargetEl()
Section titled “getTargetEl()”
> **getTargetEl**(): `undefined` | `HTMLElement`
Defined in: packages/core/src/utils/Mountable.ts:22
Get the element that the mountable is currently mounted to.
#### Returns
Section titled “Returns”
`undefined` | `HTMLElement`
#### Inherited from
Section titled “Inherited from”
`Mountable`.`getTargetEl`
### getUuid()
Section titled “getUuid()”
> **getUuid**(): `string`
Defined in: packages/core/src/fields/FieldMountable.ts:17
#### Returns
Section titled “Returns”
`string`
### isMounted()
Section titled “isMounted()”
> **isMounted**(): `boolean`
Defined in: packages/core/src/utils/Mountable.ts:15
Check if the mountable is currently mounted.
#### Returns
Section titled “Returns”
`boolean`
#### Inherited from
Section titled “Inherited from”
`Mountable`.`isMounted`
### mount()
Section titled “mount()”
> **mount**(`targetEl`): `void`
Defined in: packages/core/src/utils/Mountable.ts:50
Mount the mountable to the given element. Will throw an error if the mountable is already mounted.
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`targetEl` |  `HTMLElement`  
#### Returns
Section titled “Returns”
`void`
#### Inherited from
Section titled “Inherited from”
`Mountable`.`mount`
### registerUnmountCb()
Section titled “registerUnmountCb()”
> **registerUnmountCb**(`cb`): `void`
Defined in: packages/core/src/utils/Mountable.ts:91
Register a callback that will be called when the mountable is unmounted.
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`cb` |  () => `void`  
#### Returns
Section titled “Returns”
`void`
#### Inherited from
Section titled “Inherited from”
`Mountable`.`registerUnmountCb`
### unmount()
Section titled “unmount()”
> **unmount**(): `void`
Defined in: packages/core/src/utils/Mountable.ts:70
Unmount the mountable from the current element.
#### Returns
Section titled “Returns”
`void`
#### Inherited from
Section titled “Inherited from”
`Mountable`.`unmount`


================================================================================

## 10. /api/classes/buttonclickcontext

(/api/classes/buttonclickcontext/#_top)
# ButtonClickContext
Defined in: packages/core/src/config/ButtonConfig.ts:210
Provides information about the button click event.
## Constructors
Section titled “Constructors”
### Constructor
Section titled “Constructor”
> **new ButtonClickContext**(`type`, `shiftKey`, `ctrlKey`, `altKey`): `ButtonClickContext`
Defined in: packages/core/src/config/ButtonConfig.ts:216
#### Parameters
Section titled “Parameters”
Parameter | Type  
---|---  
`type` |  `ButtonClickType`  
`shiftKey` |  `boolean`  
`ctrlKey` |  `boolean`  
`altKey` |  `boolean`  
#### Returns
Section titled “Returns”
`ButtonClickContext`
## Properties
Section titled “Properties”
### altKey
Section titled “altKey”
> **altKey** : `boolean`
Defined in: packages/core/src/config/ButtonConfig.ts:214
### ctrlKey
Section titled “ctrlKey”
> **ctrlKey** : `boolean`
Defined in: packages/core/src/config/ButtonConfig.ts:213
### shiftKey
Section titled “shiftKey”
> **shiftKey** : `boolean`
Defined in: packages/core/src/config/ButtonConfig.ts:212
### type
Section titled “type”
> **type** : `ButtonClickType`
Defined in: packages/core/src/config/ButtonConfig.ts:211
## Methods
Section titled “Methods”
### openInNewTab()
Section titled “openInNewTab()”
> **openInNewTab**(): `boolean`
Defined in: packages/core/src/config/ButtonConfig.ts:233
Whether the click should cause a link to open in a new tab. Only applicable when the click is on a link.
#### Returns
Section titled “Returns”
`boolean`
### fromMouseEvent()
Section titled “fromMouseEvent()”
> `static` **fromMouseEvent**(`event`, `type`): `ButtonClickContext`
Defined in: packages/core/src/config/ButtonConfig.ts:223
#### Parameters
Section titled “Parameters”
Parameter | Type  
---|---  
`event` |  `MouseEvent`  
`type` |  `ButtonClickType`  
#### Returns
Section titled “Returns”
`ButtonClickContext`


================================================================================

## 11. /api/enumerations/buttonclicktype

(/api/enumerations/buttonclicktype/#_top)  
# ButtonClickType
Defined in: packages/core/src/config/ButtonConfig.ts:238
## Enumeration Members
Section titled “Enumeration Members”
Enumeration Member | Value | Description | Defined in  
---|---|---|---  
`LEFT` |  `"left"` |  The user used the left mouse button to click the button |  packages/core/src/config/ButtonConfig.ts:242  
`MIDDLE` |  `"middle"` |  The user used the middle mouse button (also known as scroll wheel click) to click the button |  packages/core/src/config/ButtonConfig.ts:246


================================================================================

## 12. /api/enumerations/inputfieldargumenttype

(/api/enumerations/inputfieldargumenttype/#_top)  
# InputFieldArgumentType
Defined in: packages/core/src/config/FieldConfigs.ts:49
## Enumeration Members
Section titled “Enumeration Members”
Enumeration Member | Value | Defined in  
---|---|---  
`ADD_LABELS` |  `"addLabels"` |  packages/core/src/config/FieldConfigs.ts:51  
`ALLOW_OTHER` |  `"allowOther"` |  packages/core/src/config/FieldConfigs.ts:66  
`CLASS` |  `"class"` |  packages/core/src/config/FieldConfigs.ts:50  
`DEFAULT_VALUE` |  `"defaultValue"` |  packages/core/src/config/FieldConfigs.ts:61  
`INVALID` |  `"invalid"` |  packages/core/src/config/FieldConfigs.ts:68  
`LIMIT` |  `"limit"` |  packages/core/src/config/FieldConfigs.ts:64  
`MAX_VALUE` |  `"maxValue"` |  packages/core/src/config/FieldConfigs.ts:53  
`MIN_VALUE` |  `"minValue"` |  packages/core/src/config/FieldConfigs.ts:52  
`MULTI_LINE` |  `"multiLine"` |  packages/core/src/config/FieldConfigs.ts:65  
`OFF_VALUE` |  `"offValue"` |  packages/core/src/config/FieldConfigs.ts:60  
`ON_VALUE` |  `"onValue"` |  packages/core/src/config/FieldConfigs.ts:59  
`OPTION` |  `"option"` |  packages/core/src/config/FieldConfigs.ts:55  
`OPTION_QUERY` |  `"optionQuery"` |  packages/core/src/config/FieldConfigs.ts:57  
`PLACEHOLDER` |  `"placeholder"` |  packages/core/src/config/FieldConfigs.ts:62  
`SHOWCASE` |  `"showcase"` |  packages/core/src/config/FieldConfigs.ts:58  
`STEP_SIZE` |  `"stepSize"` |  packages/core/src/config/FieldConfigs.ts:54  
`TITLE` |  `"title"` |  packages/core/src/config/FieldConfigs.ts:56  
`USE_LINKS` |  `"useLinks"` |  packages/core/src/config/FieldConfigs.ts:63


================================================================================

## 13. /api/classes/mountable

(/api/classes/mountable/#_top)
# Mountable
Defined in: packages/core/src/utils/Mountable.ts:1
## Extended by
Section titled “Extended by”
  * `FieldMountable`


## Constructors
Section titled “Constructors”
### Constructor
Section titled “Constructor”
> **new Mountable**(): `Mountable`
Defined in: packages/core/src/utils/Mountable.ts:6
#### Returns
Section titled “Returns”
`Mountable`
## Methods
Section titled “Methods”
### getTargetEl()
Section titled “getTargetEl()”
> **getTargetEl**(): `undefined` | `HTMLElement`
Defined in: packages/core/src/utils/Mountable.ts:22
Get the element that the mountable is currently mounted to.
#### Returns
Section titled “Returns”
`undefined` | `HTMLElement`
### isMounted()
Section titled “isMounted()”
> **isMounted**(): `boolean`
Defined in: packages/core/src/utils/Mountable.ts:15
Check if the mountable is currently mounted.
#### Returns
Section titled “Returns”
`boolean`
### mount()
Section titled “mount()”
> **mount**(`targetEl`): `void`
Defined in: packages/core/src/utils/Mountable.ts:50
Mount the mountable to the given element. Will throw an error if the mountable is already mounted.
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`targetEl` |  `HTMLElement`  
#### Returns
Section titled “Returns”
`void`
### registerUnmountCb()
Section titled “registerUnmountCb()”
> **registerUnmountCb**(`cb`): `void`
Defined in: packages/core/src/utils/Mountable.ts:91
Register a callback that will be called when the mountable is unmounted.
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`cb` |  () => `void`  
#### Returns
Section titled “Returns”
`void`
### unmount()
Section titled “unmount()”
> **unmount**(): `void`
Defined in: packages/core/src/utils/Mountable.ts:70
Unmount the mountable from the current element.
#### Returns
Section titled “Returns”
`void`


================================================================================

## 14. /api/enumerations/buttonactiontype

(/api/enumerations/buttonactiontype/#_top)  
# ButtonActionType
Defined in: packages/core/src/config/ButtonConfig.ts:22
## Enumeration Members
Section titled “Enumeration Members”
Enumeration Member | Value | Defined in  
---|---|---  
`COMMAND` |  `"command"` |  packages/core/src/config/ButtonConfig.ts:23  
`CREATE_NOTE` |  `"createNote"` |  packages/core/src/config/ButtonConfig.ts:31  
`INLINE_JS` |  `"inlineJS"` |  packages/core/src/config/ButtonConfig.ts:36  
`INPUT` |  `"input"` |  packages/core/src/config/ButtonConfig.ts:26  
`INSERT_INTO_NOTE` |  `"insertIntoNote"` |  packages/core/src/config/ButtonConfig.ts:35  
`JS` |  `"js"` |  packages/core/src/config/ButtonConfig.ts:24  
`OPEN` |  `"open"` |  packages/core/src/config/ButtonConfig.ts:25  
`REGEXP_REPLACE_IN_NOTE` |  `"regexpReplaceInNote"` |  packages/core/src/config/ButtonConfig.ts:33  
`REPLACE_IN_NOTE` |  `"replaceInNote"` |  packages/core/src/config/ButtonConfig.ts:32  
`REPLACE_SELF` |  `"replaceSelf"` |  packages/core/src/config/ButtonConfig.ts:34  
`RUN_TEMPLATER_FILE` |  `"runTemplaterFile"` |  packages/core/src/config/ButtonConfig.ts:29  
`SLEEP` |  `"sleep"` |  packages/core/src/config/ButtonConfig.ts:27  
`TEMPLATER_CREATE_NOTE` |  `"templaterCreateNote"` |  packages/core/src/config/ButtonConfig.ts:28  
`UPDATE_METADATA` |  `"updateMetadata"` |  packages/core/src/config/ButtonConfig.ts:30


================================================================================

## 15. /api/classes/obsapi

(/api/classes/obsapi/#_top)
# ObsAPI
Defined in: packages/obsidian/src/ObsAPI.ts:38
Meta Bind API for Obsidian.
## Extends
Section titled “Extends”
  * `API`<`ObsComponents`>


## Constructors
Section titled “Constructors”
### Constructor
Section titled “Constructor”
> **new ObsAPI**(`mb`): `ObsAPI`
Defined in: packages/obsidian/src/ObsAPI.ts:42
#### Parameters
Section titled “Parameters”
Parameter | Type  
---|---  
`mb` |  `ObsMetaBind`  
#### Returns
Section titled “Returns”
`ObsAPI`
#### Overrides
Section titled “Overrides”
`API<ObsComponents>.constructor`
## Properties
Section titled “Properties”
### mb
Section titled “mb”
> `readonly` **mb** : `MetaBind`<`ObsComponents`>
Defined in: packages/core/src/api/API.ts:63
#### Inherited from
Section titled “Inherited from”
`API.mb`
## Methods
Section titled “Methods”
### constructMDRCWidget()
Section titled “constructMDRCWidget()”
> **constructMDRCWidget**(`inlineFieldType`, `content`, `filePath`, `component`): `MarkdownRenderChildWidget`
Defined in: packages/obsidian/src/ObsAPI.ts:88
Creates a CM6 widget from a given widget type.
This is only useful for use in a CodeMirror plugin.
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`inlineFieldType` |  `InlineFieldType`  
`content` |  `string`  
`filePath` |  `string`  
`component` |  `Component`  
#### Returns
Section titled “Returns”
`MarkdownRenderChildWidget`
### createBindTarget()
Section titled “createBindTarget()”
> **createBindTarget**(`storageType`, `storagePath`, `property`, `listenToChildren`): `BindTargetDeclaration`
Defined in: packages/core/src/api/API.ts:591
Creates a bind target declaration.
#### Parameters
Section titled “Parameters”
Parameter | Type | Default value | Description  
---|---|---|---  
`storageType` |  `string` |  `undefined` |  the storage type (also named metadata source sometimes)  
`storagePath` |  `string` |  `undefined` |  the storage path (usually the file path)  
`property` |  `string`[] |  `undefined` |  the property access path as an array. E.g. for the path `cache.a.b.c`, the array would be `['a', 'b', 'c']`.  
`listenToChildren` |  `boolean` |  `false` |  whether to listen to children, only relevant for arrays and objects  
#### Returns
Section titled “Returns”
`BindTargetDeclaration`
#### Inherited from
Section titled “Inherited from”
`API.createBindTarget`
### createButtonGroupMountable()
Section titled “createButtonGroupMountable()”
> **createButtonGroupMountable**(`filePath`, `options`): `ButtonGroupMountable`
Defined in: packages/core/src/api/API.ts:386
Creates a button group from an options object.
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`filePath` |  `string` |  the file path that the field is located in or an empty string  
`options` |  `ButtonGroupOptions`  
#### Returns
Section titled “Returns”
`ButtonGroupMountable`
#### Inherited from
Section titled “Inherited from”
`API.createButtonGroupMountable`
### createButtonMountable()
Section titled “createButtonMountable()”
> **createButtonMountable**(`filePath`, `options`): `ButtonMountable`
Defined in: packages/core/src/api/API.ts:423
Creates a button from an options object.
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`filePath` |  `string` |  the file path that the field is located in or an empty string  
`options` |  `ButtonOptions`  
#### Returns
Section titled “Returns”
`ButtonMountable`
#### Inherited from
Section titled “Inherited from”
`API.createButtonMountable`
### createEmbedMountable()
Section titled “createEmbedMountable()”
> **createEmbedMountable**(`filePath`, `options`): `EmbedMountable`
Defined in: packages/core/src/api/API.ts:453
Creates a meta bind embed fields from an options object.
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`filePath` |  `string` |  the file path that the field is located in or an empty string  
`options` |  `EmbedOptions`  
#### Returns
Section titled “Returns”
`EmbedMountable`
#### Inherited from
Section titled “Inherited from”
`API.createEmbedMountable`
### createExcludedMountable()
Section titled “createExcludedMountable()”
> **createExcludedMountable**(`filePath`): `ExcludedMountable`
Defined in: packages/core/src/api/API.ts:474
Creates an excluded notification mountable for the excluded folders setting.
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`filePath` |  `string` |  the file path that the field is located in or an empty string  
#### Returns
Section titled “Returns”
`ExcludedMountable`
#### Inherited from
Section titled “Inherited from”
`API.createExcludedMountable`
### createField()
Section titled “createField()”
> **createField** <`Type`>(`type`, `filePath`, `options`, `honorExcludedSetting`): `FieldMountable`
Defined in: packages/core/src/api/API.ts:77
Creates a field of a given type.
#### Type Parameters
Section titled “Type Parameters”
Type Parameter  
---  
`Type` _extends_ `FieldType`  
#### Parameters
Section titled “Parameters”
Parameter | Type | Default value | Description  
---|---|---|---  
`type` |  `Type` |  `undefined` |  the type of the field  
`filePath` |  `string` |  `undefined` |  the file path that the field is located in, or an empty string if it is not in a file  
`options` |  `FieldOptionMap`[`Type`] |  `undefined`  
`honorExcludedSetting` |  `boolean` |  `true` |  whether to honor the excluded folders settings for this field  
#### Returns
Section titled “Returns”
`FieldMountable`
#### Inherited from
Section titled “Inherited from”
`API.createField`
### createInlineFieldFromString()
Section titled “createInlineFieldFromString()”
> **createInlineFieldFromString**(`fieldString`, `filePath`, `scope`, `renderChildType`, `position?`, `honorExcludedSetting?`): `FieldMountable`
Defined in: packages/core/src/api/API.ts:137
Creates an inline field from a string. Will throw an error if the string is not a valid declaration.
#### Parameters
Section titled “Parameters”
Parameter | Type | Default value | Description  
---|---|---|---  
`fieldString` |  `string` |  `undefined` |  the declaration string of the field  
`filePath` |  `string` |  `undefined` |  the file path that the field is located in  
`scope` |  `undefined` | `BindTargetScope` |  `undefined` |  optional bind target scope  
`renderChildType` |  `RenderChildType` |  `RenderChildType.INLINE` |  the render child type, default INLINE  
`position?` |  `NotePosition` |  `undefined` |  an optional note position  
`honorExcludedSetting?` |  `boolean` |  `true` |  whether to honor the excluded folders settings for this field  
#### Returns
Section titled “Returns”
`FieldMountable`
#### Inherited from
Section titled “Inherited from”
`API.createInlineFieldFromString`
### createInlineFieldOfTypeFromString()
Section titled “createInlineFieldOfTypeFromString()”
> **createInlineFieldOfTypeFromString**(`type`, `declaration`, `filePath`, `scope`, `renderChildType`, `position?`, `honorExcludedSetting?`): `FieldMountable`
Defined in: packages/core/src/api/API.ts:194
Creates an inline field of a given type and string. Will throw an error if the string is not a valid inline field type.
#### Parameters
Section titled “Parameters”
Parameter | Type | Default value | Description  
---|---|---|---  
`type` |  `InlineFieldType` |  `undefined` |  the field type  
`declaration` |  `string` |  `undefined` |  the declaration string of the field  
`filePath` |  `string` |  `undefined` |  the file path that the field is located in  
`scope` |  `undefined` | `BindTargetScope` |  `undefined` |  optional bind target scope  
`renderChildType` |  `RenderChildType` |  `RenderChildType.INLINE` |  the render child type, default INLINE  
`position?` |  `NotePosition` |  `undefined` |  an optional note position  
`honorExcludedSetting?` |  `boolean` |  `true` |  whether to honor the excluded folders settings for this field  
#### Returns
Section titled “Returns”
`FieldMountable`
#### Inherited from
Section titled “Inherited from”
`API.createInlineFieldOfTypeFromString`
### createInputFieldMountable()
Section titled “createInputFieldMountable()”
> **createInputFieldMountable**(`filePath`, `options`): `InputFieldMountable`
Defined in: packages/core/src/api/API.ts:265
Creates an input field from an options object.
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`filePath` |  `string` |  the file path that the field is located in or an empty string  
`options` |  `InputFieldOptions`  
#### Returns
Section titled “Returns”
`InputFieldMountable`
#### Inherited from
Section titled “Inherited from”
`API.createInputFieldMountable`
### createJsViewFieldMountable()
Section titled “createJsViewFieldMountable()”
> **createJsViewFieldMountable**(`filePath`, `options`): `JsViewFieldMountable`
Defined in: packages/core/src/api/API.ts:333
Creates a JS view field from an options object.
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`filePath` |  `string` |  the file path that the field is located in or an empty string  
`options` |  `JsViewFieldOptions`  
#### Returns
Section titled “Returns”
`JsViewFieldMountable`
#### Inherited from
Section titled “Inherited from”
`API.createJsViewFieldMountable`
### createNotePosition()
Section titled “createNotePosition()”
> **createNotePosition**(`lineStart`, `lineEnd`): `NotePosition`
Defined in: packages/core/src/api/API.ts:783
Creates a note position from a line start and line end number.
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`lineStart` |  `number`  
`lineEnd` |  `number`  
#### Returns
Section titled “Returns”
`NotePosition`
#### Inherited from
Section titled “Inherited from”
`API.createNotePosition`
### createSignal()
Section titled “createSignal()”
> **createSignal** <`T`>(`value`): `Signal`<`T`>
Defined in: packages/core/src/api/API.ts:579
Creates a signal.
#### Type Parameters
Section titled “Type Parameters”
Type Parameter  
---  
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`value`  
#### Returns
Section titled “Returns”
`Signal`<`T`>
#### Inherited from
Section titled “Inherited from”
`API.createSignal`
### createTableMountable()
Section titled “createTableMountable()”
> **createTableMountable**(`filePath`, `options`): `TableMountable`
Defined in: packages/core/src/api/API.ts:363
Creates a table from an options object.
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`filePath` |  `string` |  the file path that the field is located in or an empty string  
`options` |  `TableOptions`  
#### Returns
Section titled “Returns”
`TableMountable`
#### Inherited from
Section titled “Inherited from”
`API.createTableMountable`
### createViewFieldMountable()
Section titled “createViewFieldMountable()”
> **createViewFieldMountable**(`filePath`, `options`): `ViewFieldMountable`
Defined in: packages/core/src/api/API.ts:299
Creates a view field from an options object.
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`filePath` |  `string` |  the file path that the field is located in or an empty string  
`options` |  `ViewFieldOptions`  
#### Returns
Section titled “Returns”
`ViewFieldMountable`
#### Inherited from
Section titled “Inherited from”
`API.createViewFieldMountable`
### getInlineFieldDeclarationPrefix()
Section titled “getInlineFieldDeclarationPrefix()”
> **getInlineFieldDeclarationPrefix**(`fieldType`): `string`
Defined in: packages/core/src/api/API.ts:493
Gets the prefix of a given widget type. (e.g. INPUT or VIEW).
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`fieldType` |  `FieldType`  
#### Returns
Section titled “Returns”
`string`
#### Inherited from
Section titled “Inherited from”
`API.getInlineFieldDeclarationPrefix`
### getMetadata()
Section titled “getMetadata()”
> **getMetadata**(`bindTarget`): `unknown`
Defined in: packages/core/src/api/API.ts:685
Reads a property from meta binds metadata cache. If the value is not present in the cache, it will check the underlying source. E.g. Obsidians metadata cache.
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`bindTarget` |  `BindTargetDeclaration`  
#### Returns
Section titled “Returns”
`unknown`
#### Example
Section titled “Example”
```

// Assumes you use the JS Engine plugin to run this.
constmb= engine.getPlugin("obsidian-meta-bind-plugin").api;
constbindTarget= mb.parseBindTarget("property", context.file.path);
constvalue= mb.getMetadata(bindTarget);

```

#### Inherited from
Section titled “Inherited from”
`API.getMetadata`
### isInlineFieldDeclaration()
Section titled “isInlineFieldDeclaration()”
> **isInlineFieldDeclaration**(`fieldType`, `str`): `boolean`
Defined in: packages/core/src/api/API.ts:524
Checks if a string is a declaration of a given widget type.
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`fieldType` |  `FieldType`  
`str` |  `string` |  the declaration string  
#### Returns
Section titled “Returns”
`boolean`
#### Inherited from
Section titled “Inherited from”
`API.isInlineFieldDeclaration`
### isInlineFieldDeclarationAndGetType()
Section titled “isInlineFieldDeclarationAndGetType()”
> **isInlineFieldDeclarationAndGetType**(`str`): `undefined` | `InlineFieldType`
Defined in: packages/core/src/api/API.ts:547
Checks if a string is any declaration. If yes, it returns the widget type, otherwise undefined.
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`str` |  `string` |  the declaration string  
#### Returns
Section titled “Returns”
`undefined` | `InlineFieldType`
#### Inherited from
Section titled “Inherited from”
`API.isInlineFieldDeclarationAndGetType`
### mathJSImport()
Section titled “mathJSImport()”
> **mathJSImport**(`object`, `options?`): `void`
Defined in: packages/core/src/api/API.ts:805
Import new definitions into the internal mathJS instance. For details on how to use, see 
#### Parameters
Section titled “Parameters”
Parameter | Type  
---|---  
`object` |  `ImportObject` | `ImportObject`[]  
`options?` |  `ImportOptions`  
#### Returns
Section titled “Returns”
`void`
#### Inherited from
Section titled “Inherited from”
`API.mathJSImport`
### parseBindTarget()
Section titled “parseBindTarget()”
> **parseBindTarget**(`declarationString`, `filePath`, `scope?`): `BindTargetDeclaration`
Defined in: packages/core/src/api/API.ts:627
Parses a bind target declaration from a string.
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`declarationString` |  `string` |  the string to parse  
`filePath` |  `string` |  the file path that this bind target is relative to  
`scope?` |  `BindTargetScope` |  optional bind target scope  
#### Returns
Section titled “Returns”
`BindTargetDeclaration`
#### Inherited from
Section titled “Inherited from”
`API.parseBindTarget`
### reactiveMetadata()
Section titled “reactiveMetadata()”
> **reactiveMetadata**(`bindTargets`, `lifecycleHook`, `callback`): `ReactiveComponent`
Defined in: packages/obsidian/src/ObsAPI.ts:114
Creates a JS Engine reactive component that will re-render when the given bind targets change.
This requires JS Engine to be installed and enabled!
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`bindTargets` |  `BindTargetDeclaration`[] |  the bind targets to listen to  
`lifecycleHook` |  `LifecycleHook` |  a Component  
`callback` |  (…`values`) => `Promise`<`unknown`> |  the callback to call with all the values of the bind targets when one of them changes. What ever this callback returns will be rendered by the reactive component.  
#### Returns
Section titled “Returns”
`ReactiveComponent`
### setMetadata()
Section titled “setMetadata()”
> **setMetadata**(`bindTarget`, `value`): `void`
Defined in: packages/core/src/api/API.ts:660
Sets a property in meta binds metadata cache.
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`bindTarget` |  `BindTargetDeclaration`  
`value` |  `unknown`  
#### Returns
Section titled “Returns”
`void`
#### Example
Section titled “Example”
```

// Assumes you use the JS Engine plugin to run this.
constmb= engine.getPlugin("obsidian-meta-bind-plugin").api;
constbindTarget= mb.parseBindTarget("property", context.file.path);
mb.setMetadata(bindTarget, "some value");

```

#### Inherited from
Section titled “Inherited from”
`API.setMetadata`
### subscribeToMetadata()
Section titled “subscribeToMetadata()”
> **subscribeToMetadata**(`bindTarget`, `lifecycleHook`, `callback`): `void`
Defined in: packages/core/src/api/API.ts:743
Subscribes to a property in meta binds metadata cache. This expects some sort of lifecycle hook to be passed in. This method will register a callback to the lifecycle hook. To unsubscribe the subscription, the callback registered to the lifecycle hook must be called. In the context of Obsidian, you should pass a `Component` instance as the lifecycle hook and make sure to unload the component when you are done using the metadata subscription.
NOT UNSUBSCRIBING WILL LEAD TO MEMORY LEAKS.
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`bindTarget` |  `BindTargetDeclaration`  
`lifecycleHook` |  `LifecycleHook` |  In Obsidian this is an instance of the Component class. The subscription will be automatically unsubscribed when the component is unloaded.  
`callback` |  (`value`) => `void`  
#### Returns
Section titled “Returns”
`void`
#### Inherited from
Section titled “Inherited from”
`API.subscribeToMetadata`
### updateMetadata()
Section titled “updateMetadata()”
> **updateMetadata**(`bindTarget`, `updateFn`): `void`
Defined in: packages/core/src/api/API.ts:712
Updates a property in meta binds metadata cache.
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`bindTarget` |  `BindTargetDeclaration`  
`updateFn` |  (`value`) => `unknown` |  a function that takes the current value and returns the new value  
#### Returns
Section titled “Returns”
`void`
#### Example
Section titled “Example”
```

// Assumes you use the JS Engine plugin to run this.
constmb= engine.getPlugin("obsidian-meta-bind-plugin").api;
constbindTarget= mb.parseBindTarget("property", context.file.path);
mb.updateMetadata(bindTarget, (value) => {
return value +1;
});

```

#### Inherited from
Section titled “Inherited from”
`API.updateMetadata`
### wrapInMDRC()
Section titled “wrapInMDRC()”
> **wrapInMDRC**(`mountable`, `containerEl`, `component`): `MountableMDRC`
Defined in: packages/obsidian/src/ObsAPI.ts:58
Wraps any mountable in a MarkdownRenderChild and adds it as a child to the passed in ComponentLike.
A ComponentLike is either a Component or a MarkdownPostProcessorContext
#### Parameters
Section titled “Parameters”
Parameter | Type | Description  
---|---|---  
`mountable` |  `Mountable` |  the mountable to wrap in a MarkdownRenderChild  
`containerEl` |  `HTMLElement` |  the element to mount the MarkdownRenderChild to  
`component` |  `ComponentLike` |  the ComponentLike to register the MarkdownRenderChild to  
#### Returns
Section titled “Returns”
`MountableMDRC`


================================================================================

## 16. /api/enumerations/viewfieldargumenttype

(/api/enumerations/viewfieldargumenttype/#_top)  
# ViewFieldArgumentType
Defined in: packages/core/src/config/FieldConfigs.ts:527
## Enumeration Members
Section titled “Enumeration Members”
Enumeration Member | Value | Defined in  
---|---|---  
`CLASS` |  `"class"` |  packages/core/src/config/FieldConfigs.ts:530  
`HIDDEN` |  `"hidden"` |  packages/core/src/config/FieldConfigs.ts:529  
`INVALID` |  `"invalid"` |  packages/core/src/config/FieldConfigs.ts:532  
`RENDER_MARKDOWN` |  `"renderMarkdown"` |  packages/core/src/config/FieldConfigs.ts:528


================================================================================

## 17. /api/interfaces/buttoncontext

(/api/interfaces/buttoncontext/#_top)
# ButtonContext
Defined in: packages/core/src/config/ButtonConfig.ts:201
## Properties
Section titled “Properties”
### isInGroup
Section titled “isInGroup”
> **isInGroup** : `boolean`
Defined in: packages/core/src/config/ButtonConfig.ts:203
### isInline
Section titled “isInline”
> **isInline** : `boolean`
Defined in: packages/core/src/config/ButtonConfig.ts:204
### position
Section titled “position”
> **position** : `undefined` | `LinePosition`
Defined in: packages/core/src/config/ButtonConfig.ts:202


================================================================================

## 18. /api/interfaces/buttonconfig

(/api/interfaces/buttonconfig/#_top)
# ButtonConfig
Defined in: packages/core/src/config/ButtonConfig.ts:151
## Properties
Section titled “Properties”
### action?
Section titled “action?”
> `optional` **action** : `ButtonAction`
Defined in: packages/core/src/config/ButtonConfig.ts:193
A single action to run when the button is clicked Mutually exclusive with `actions`
### actions?
Section titled “actions?”
> `optional` **actions** : `ButtonAction`[]
Defined in: packages/core/src/config/ButtonConfig.ts:198
Multiple actions to run when the button is clicked Mutually exclusive with `action`
### backgroundImage?
Section titled “backgroundImage?”
> `optional` **backgroundImage** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:176
Optional background image to add to the button, needed since you can’t load images from the vault via pure CSS
### class?
Section titled “class?”
> `optional` **class** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:167
Optional CSS class to add to the button
### cssStyle?
Section titled “cssStyle?”
> `optional` **cssStyle** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:171
Optional CSS styles to add to the button
### hidden?
Section titled “hidden?”
> `optional` **hidden** : `boolean`
Defined in: packages/core/src/config/ButtonConfig.ts:188
Whether the button is hidden
### icon?
Section titled “icon?”
> `optional` **icon** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:159
Optional icon to display in front of the label
### id?
Section titled “id?”
> `optional` **id** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:184
Optional ID for use in inline buttons
### label
Section titled “label”
> **label** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:155
The text displayed on the button
### style
Section titled “style”
> **style** : `ButtonStyleType`
Defined in: packages/core/src/config/ButtonConfig.ts:163
The style of the button
### tooltip?
Section titled “tooltip?”
> `optional` **tooltip** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:180
Optional tooltip to display when hovering over the button


================================================================================

## 19. /api/interfaces/buttonactionmap

(/api/interfaces/buttonactionmap/#_top)
# ButtonActionMap
Defined in: packages/core/src/config/ButtonConfig.ts:132
Maps action types to their respective action interfaces.
## Properties
Section titled “Properties”
### command
Section titled “command”
> **command** : `CommandButtonAction`
Defined in: packages/core/src/config/ButtonConfig.ts:133
### createNote
Section titled “createNote”
> **createNote** : `CreateNoteButtonAction`
Defined in: packages/core/src/config/ButtonConfig.ts:140
### inlineJS
Section titled “inlineJS”
> **inlineJS** : `InlineJSButtonAction`
Defined in: packages/core/src/config/ButtonConfig.ts:145
### input
Section titled “input”
> **input** : `InputButtonAction`
Defined in: packages/core/src/config/ButtonConfig.ts:136
### insertIntoNote
Section titled “insertIntoNote”
> **insertIntoNote** : `InsertIntoNoteButtonAction`
Defined in: packages/core/src/config/ButtonConfig.ts:144
### js
Section titled “js”
> **js** : `JSButtonAction`
Defined in: packages/core/src/config/ButtonConfig.ts:134
### open
Section titled “open”
> **open** : `OpenButtonAction`
Defined in: packages/core/src/config/ButtonConfig.ts:135
### regexpReplaceInNote
Section titled “regexpReplaceInNote”
> **regexpReplaceInNote** : `RegexpReplaceInNoteButtonAction`
Defined in: packages/core/src/config/ButtonConfig.ts:143
### replaceInNote
Section titled “replaceInNote”
> **replaceInNote** : `ReplaceInNoteButtonAction`
Defined in: packages/core/src/config/ButtonConfig.ts:141
### replaceSelf
Section titled “replaceSelf”
> **replaceSelf** : `ReplaceSelfButtonAction`
Defined in: packages/core/src/config/ButtonConfig.ts:142
### runTemplaterFile
Section titled “runTemplaterFile”
> **runTemplaterFile** : `RunTemplaterFileButtonAction`
Defined in: packages/core/src/config/ButtonConfig.ts:146
### sleep
Section titled “sleep”
> **sleep** : `SleepButtonAction`
Defined in: packages/core/src/config/ButtonConfig.ts:137
### templaterCreateNote
Section titled “templaterCreateNote”
> **templaterCreateNote** : `TemplaterCreateNoteButtonAction`
Defined in: packages/core/src/config/ButtonConfig.ts:138
### updateMetadata
Section titled “updateMetadata”
> **updateMetadata** : `UpdateMetadataButtonAction`
Defined in: packages/core/src/config/ButtonConfig.ts:139


================================================================================

## 20. /api/enumerations/viewfieldtype

(/api/enumerations/viewfieldtype/#_top)  
# ViewFieldType
Defined in: packages/core/src/config/FieldConfigs.ts:518
## Enumeration Members
Section titled “Enumeration Members”
Enumeration Member | Value | Defined in  
---|---|---  
`IMAGE` |  `"image"` |  packages/core/src/config/FieldConfigs.ts:522  
`INVALID` |  `"invalid"` |  packages/core/src/config/FieldConfigs.ts:524  
`LINK` |  `"link"` |  packages/core/src/config/FieldConfigs.ts:521  
`MATH` |  `"math"` |  packages/core/src/config/FieldConfigs.ts:519  
`TEXT` |  `"text"` |  packages/core/src/config/FieldConfigs.ts:520


================================================================================

## 21. /api/interfaces/buttondeclaration

(/api/interfaces/buttondeclaration/#_top)
# ButtonDeclaration
Defined in: packages/core/src/parsers/ButtonParser.ts:29
## Properties
Section titled “Properties”
### config
Section titled “config”
> **config** : `undefined` | `ButtonConfig`
Defined in: packages/core/src/parsers/ButtonParser.ts:31
### declarationString
Section titled “declarationString”
> **declarationString** : `undefined` | `string`
Defined in: packages/core/src/parsers/ButtonParser.ts:30
### errorCollection
Section titled “errorCollection”
> **errorCollection** : `ErrorCollection`
Defined in: packages/core/src/parsers/ButtonParser.ts:32


================================================================================

## 22. /api/interfaces/bindtargetdeclaration

(/api/interfaces/bindtargetdeclaration/#_top)
# BindTargetDeclaration
Defined in: packages/core/src/parsers/bindTargetParser/BindTargetDeclaration.ts:5
## Properties
Section titled “Properties”
### listenToChildren
Section titled “listenToChildren”
> **listenToChildren** : `boolean`
Defined in: packages/core/src/parsers/bindTargetParser/BindTargetDeclaration.ts:9
### storagePath
Section titled “storagePath”
> **storagePath** : `string`
Defined in: packages/core/src/parsers/bindTargetParser/BindTargetDeclaration.ts:7
### storageProp
Section titled “storageProp”
> **storageProp** : `PropPath`
Defined in: packages/core/src/parsers/bindTargetParser/BindTargetDeclaration.ts:8
### storageType
Section titled “storageType”
> **storageType** : `string`
Defined in: packages/core/src/parsers/bindTargetParser/BindTargetDeclaration.ts:6


================================================================================

## 23. /api/interfaces/buttongroupdeclaration

(/api/interfaces/buttongroupdeclaration/#_top)
# ButtonGroupDeclaration
Defined in: packages/core/src/parsers/ButtonParser.ts:19
## Properties
Section titled “Properties”
### declarationString
Section titled “declarationString”
> **declarationString** : `undefined` | `string`
Defined in: packages/core/src/parsers/ButtonParser.ts:20
### errorCollection
Section titled “errorCollection”
> **errorCollection** : `ErrorCollection`
Defined in: packages/core/src/parsers/ButtonParser.ts:22
### referencedButtonIds
Section titled “referencedButtonIds”
> **referencedButtonIds** : `string`[]
Defined in: packages/core/src/parsers/ButtonParser.ts:21


================================================================================

## 24. /api/interfaces/jsviewfieldbindtargetmapping

(/api/interfaces/jsviewfieldbindtargetmapping/#_top)
# JsViewFieldBindTargetMapping
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:48
## Properties
Section titled “Properties”
### bindTarget
Section titled “bindTarget”
> **bindTarget** : `BindTargetDeclaration`
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:49
### name
Section titled “name”
> **name** : `string`
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:50


================================================================================

## 25. /api/interfaces/lineposition

(/api/interfaces/lineposition/#_top)
# LinePosition
Defined in: packages/core/src/config/APIConfigs.ts:74
## Properties
Section titled “Properties”
### lineEnd
Section titled “lineEnd”
> **lineEnd** : `number`
Defined in: packages/core/src/config/APIConfigs.ts:76
### lineStart
Section titled “lineStart”
> **lineStart** : `number`
Defined in: packages/core/src/config/APIConfigs.ts:75


================================================================================

## 26. /api/interfaces/buttonoptions

(/api/interfaces/buttonoptions/#_top)
# ButtonOptions
Defined in: packages/core/src/config/APIConfigs.ts:56
## Properties
Section titled “Properties”
### declaration
Section titled “declaration”
> **declaration** : `string` | `ButtonConfig`
Defined in: packages/core/src/config/APIConfigs.ts:57
### isPreview
Section titled “isPreview”
> **isPreview** : `boolean`
Defined in: packages/core/src/config/APIConfigs.ts:59
### position?
Section titled “position?”
> `optional` **position** : `NotePosition`
Defined in: packages/core/src/config/APIConfigs.ts:58


================================================================================

## 27. /api/interfaces/inputbuttonaction

(/api/interfaces/inputbuttonaction/#_top)
# InputButtonAction
Defined in: packages/core/src/config/ButtonConfig.ts:56
## Properties
Section titled “Properties”
### str
Section titled “str”
> **str** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:58
### type
Section titled “type”
> **type** : `INPUT`
Defined in: packages/core/src/config/ButtonConfig.ts:57


================================================================================

## 28. /api/interfaces/insertintonotebuttonaction

(/api/interfaces/insertintonotebuttonaction/#_top)
# InsertIntoNoteButtonAction
Defined in: packages/core/src/config/ButtonConfig.ts:116
## Properties
Section titled “Properties”
### line
Section titled “line”
> **line** : `string` | `number`
Defined in: packages/core/src/config/ButtonConfig.ts:118
### templater?
Section titled “templater?”
> `optional` **templater** : `boolean`
Defined in: packages/core/src/config/ButtonConfig.ts:120
### type
Section titled “type”
> **type** : `INSERT_INTO_NOTE`
Defined in: packages/core/src/config/ButtonConfig.ts:117
### value
Section titled “value”
> **value** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:119


================================================================================

## 29. /api/interfaces/createnotebuttonaction

(/api/interfaces/createnotebuttonaction/#_top)
# CreateNoteButtonAction
Defined in: packages/core/src/config/ButtonConfig.ts:87
## Properties
Section titled “Properties”
### fileName
Section titled “fileName”
> **fileName** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:90
### folderPath?
Section titled “folderPath?”
> `optional` **folderPath** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:89
### openIfAlreadyExists?
Section titled “openIfAlreadyExists?”
> `optional` **openIfAlreadyExists** : `boolean`
Defined in: packages/core/src/config/ButtonConfig.ts:92
### openNote?
Section titled “openNote?”
> `optional` **openNote** : `boolean`
Defined in: packages/core/src/config/ButtonConfig.ts:91
### type
Section titled “type”
> **type** : `CREATE_NOTE`
Defined in: packages/core/src/config/ButtonConfig.ts:88


================================================================================

## 30. /api/interfaces/jsbuttonaction

(/api/interfaces/jsbuttonaction/#_top)
# JSButtonAction
Defined in: packages/core/src/config/ButtonConfig.ts:44
## Properties
Section titled “Properties”
### args?
Section titled “args?”
> `optional` **args** : `Record`<`string`, `unknown`>
Defined in: packages/core/src/config/ButtonConfig.ts:47
### file
Section titled “file”
> **file** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:46
### type
Section titled “type”
> **type** : `JS`
Defined in: packages/core/src/config/ButtonConfig.ts:45


================================================================================

## 31. /api/interfaces/inputfieldoptions

(/api/interfaces/inputfieldoptions/#_top)
# InputFieldOptions
Defined in: packages/core/src/config/APIConfigs.ts:28
## Properties
Section titled “Properties”
### declaration
Section titled “declaration”
> **declaration** : `string` | `SimpleInputFieldDeclaration`
Defined in: packages/core/src/config/APIConfigs.ts:30
### renderChildType
Section titled “renderChildType”
> **renderChildType** : `RenderChildType`
Defined in: packages/core/src/config/APIConfigs.ts:29
### scope?
Section titled “scope?”
> `optional` **scope** : `BindTargetScope`
Defined in: packages/core/src/config/APIConfigs.ts:31


================================================================================

## 32. /api/interfaces/componentlike

(/api/interfaces/componentlike/#_top)
# ComponentLike
Defined in: packages/obsidian/src/ObsAPI.ts:23
Either a Component or a MarkdownPostProcessorContext.
## Methods
Section titled “Methods”
### addChild()
Section titled “addChild()”
> **addChild**(`child`): `void`
Defined in: packages/obsidian/src/ObsAPI.ts:24
#### Parameters
Section titled “Parameters”
Parameter | Type  
---|---  
`child` |  `Component`  
#### Returns
Section titled “Returns”
`void`


================================================================================

## 33. /api/interfaces/fielddeclaration

(/api/interfaces/fielddeclaration/#_top)
# FieldDeclaration
Defined in: packages/core/src/parsers/FieldDeclaration.ts:4
## Extended by
Section titled “Extended by”
  * `InputFieldDeclaration`
  * `UnvalidatedInputFieldDeclaration`
  * `ViewFieldDeclaration`
  * `UnvalidatedViewFieldDeclaration`
  * `JsViewFieldDeclaration`
  * `UnvalidatedJsViewFieldDeclaration`


## Properties
Section titled “Properties”
### declarationString?
Section titled “declarationString?”
> `optional` **declarationString** : `string`
Defined in: packages/core/src/parsers/FieldDeclaration.ts:5
### errorCollection
Section titled “errorCollection”
> **errorCollection** : `ErrorCollection`
Defined in: packages/core/src/parsers/FieldDeclaration.ts:6


================================================================================

## 34. /api/interfaces/commandbuttonaction

(/api/interfaces/commandbuttonaction/#_top)
# CommandButtonAction
Defined in: packages/core/src/config/ButtonConfig.ts:39
## Properties
Section titled “Properties”
### command
Section titled “command”
> **command** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:41
### type
Section titled “type”
> **type** : `COMMAND`
Defined in: packages/core/src/config/ButtonConfig.ts:40


================================================================================

## 35. /api/interfaces/buttongroupoptions

(/api/interfaces/buttongroupoptions/#_top)
# ButtonGroupOptions
Defined in: packages/core/src/config/APIConfigs.ts:50
## Properties
Section titled “Properties”
### declaration
Section titled “declaration”
> **declaration** : `string` | `SimpleButtonGroupDeclaration`
Defined in: packages/core/src/config/APIConfigs.ts:52
### position?
Section titled “position?”
> `optional` **position** : `NotePosition`
Defined in: packages/core/src/config/APIConfigs.ts:53
### renderChildType
Section titled “renderChildType”
> **renderChildType** : `RenderChildType`
Defined in: packages/core/src/config/APIConfigs.ts:51


================================================================================

## 36. /api/interfaces/inputfielddeclaration

(/api/interfaces/inputfielddeclaration/#_top)
# InputFieldDeclaration
Defined in: packages/core/src/parsers/inputFieldParser/InputFieldDeclaration.ts:14
## Extends
Section titled “Extends”
  * `FieldDeclaration`


## Properties
Section titled “Properties”
### argumentContainer
Section titled “argumentContainer”
> **argumentContainer** : `InputFieldArgumentContainer`
Defined in: packages/core/src/parsers/inputFieldParser/InputFieldDeclaration.ts:17
### bindTarget
Section titled “bindTarget”
> **bindTarget** : `undefined` | `BindTargetDeclaration`
Defined in: packages/core/src/parsers/inputFieldParser/InputFieldDeclaration.ts:16
### declarationString?
Section titled “declarationString?”
> `optional` **declarationString** : `string`
Defined in: packages/core/src/parsers/FieldDeclaration.ts:5
#### Inherited from
Section titled “Inherited from”
`FieldDeclaration`.`declarationString`
### errorCollection
Section titled “errorCollection”
> **errorCollection** : `ErrorCollection`
Defined in: packages/core/src/parsers/FieldDeclaration.ts:6
#### Inherited from
Section titled “Inherited from”
`FieldDeclaration`.`errorCollection`
### inputFieldType
Section titled “inputFieldType”
> **inputFieldType** : `InputFieldType`
Defined in: packages/core/src/parsers/inputFieldParser/InputFieldDeclaration.ts:15


================================================================================

## 37. /api/interfaces/inlinejsbuttonaction

(/api/interfaces/inlinejsbuttonaction/#_top)
# InlineJSButtonAction
Defined in: packages/core/src/config/ButtonConfig.ts:123
## Properties
Section titled “Properties”
### args?
Section titled “args?”
> `optional` **args** : `Record`<`string`, `unknown`>
Defined in: packages/core/src/config/ButtonConfig.ts:126
### code
Section titled “code”
> **code** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:125
### type
Section titled “type”
> **type** : `INLINE_JS`
Defined in: packages/core/src/config/ButtonConfig.ts:124


================================================================================

## 38. /api/interfaces/jsviewfieldoptions

(/api/interfaces/jsviewfieldoptions/#_top)
# JsViewFieldOptions
Defined in: packages/core/src/config/APIConfigs.ts:40
## Properties
Section titled “Properties”
### declaration
Section titled “declaration”
> **declaration** : `string` | `SimpleJsViewFieldDeclaration`
Defined in: packages/core/src/config/APIConfigs.ts:41


================================================================================

## 39. /api/interfaces/openbuttonaction

(/api/interfaces/openbuttonaction/#_top)
# OpenButtonAction
Defined in: packages/core/src/config/ButtonConfig.ts:50
## Properties
Section titled “Properties”
### link
Section titled “link”
> **link** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:52
### newTab?
Section titled “newTab?”
> `optional` **newTab** : `boolean`
Defined in: packages/core/src/config/ButtonConfig.ts:53
### type
Section titled “type”
> **type** : `OPEN`
Defined in: packages/core/src/config/ButtonConfig.ts:51


================================================================================

## 40. /api/interfaces/embedoptions

(/api/interfaces/embedoptions/#_top)
# EmbedOptions
Defined in: packages/core/src/config/APIConfigs.ts:79
## Properties
Section titled “Properties”
### content
Section titled “content”
> **content** : `string`
Defined in: packages/core/src/config/APIConfigs.ts:81
### depth
Section titled “depth”
> **depth** : `number`
Defined in: packages/core/src/config/APIConfigs.ts:80


================================================================================

## 41. /api/interfaces/partialunvalidatedinputfielddeclaration

(/api/interfaces/partialunvalidatedinputfielddeclaration/#_top)
# PartialUnvalidatedInputFieldDeclaration
Defined in: packages/core/src/parsers/inputFieldParser/InputFieldDeclaration.ts:20
## Extended by
Section titled “Extended by”
  * `UnvalidatedInputFieldDeclaration`


## Properties
Section titled “Properties”
### arguments
Section titled “arguments”
> **arguments** : `UnvalidatedFieldArgument`[]
Defined in: packages/core/src/parsers/inputFieldParser/InputFieldDeclaration.ts:24
### bindTarget?
Section titled “bindTarget?”
> `optional` **bindTarget** : `UnvalidatedBindTargetDeclaration`
Defined in: packages/core/src/parsers/inputFieldParser/InputFieldDeclaration.ts:23
### inputFieldType?
Section titled “inputFieldType?”
> `optional` **inputFieldType** : `ParsingResultNode`
Defined in: packages/core/src/parsers/inputFieldParser/InputFieldDeclaration.ts:21
### templateName?
Section titled “templateName?”
> `optional` **templateName** : `ParsingResultNode`
Defined in: packages/core/src/parsers/inputFieldParser/InputFieldDeclaration.ts:22


================================================================================

## 42. /api/interfaces/jsviewfielddeclaration

(/api/interfaces/jsviewfielddeclaration/#_top)
# JsViewFieldDeclaration
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:41
## Extends
Section titled “Extends”
  * `FieldDeclaration`


## Properties
Section titled “Properties”
### bindTargetMappings
Section titled “bindTargetMappings”
> **bindTargetMappings** : `JsViewFieldBindTargetMapping`[]
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:42
### code
Section titled “code”
> **code** : `string`
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:45
### declarationString?
Section titled “declarationString?”
> `optional` **declarationString** : `string`
Defined in: packages/core/src/parsers/FieldDeclaration.ts:5
#### Inherited from
Section titled “Inherited from”
`FieldDeclaration`.`declarationString`
### errorCollection
Section titled “errorCollection”
> **errorCollection** : `ErrorCollection`
Defined in: packages/core/src/parsers/FieldDeclaration.ts:6
#### Inherited from
Section titled “Inherited from”
`FieldDeclaration`.`errorCollection`
### hidden
Section titled “hidden”
> **hidden** : `boolean`
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:44
### writeToBindTarget?
Section titled “writeToBindTarget?”
> `optional` **writeToBindTarget** : `BindTargetDeclaration`
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:43


================================================================================

## 43. /api/interfaces/partialunvalidatedjsviewfielddeclaration

(/api/interfaces/partialunvalidatedjsviewfielddeclaration/#_top)
# PartialUnvalidatedJsViewFieldDeclaration
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:55
## Extended by
Section titled “Extended by”
  * `UnvalidatedJsViewFieldDeclaration`


## Properties
Section titled “Properties”
### bindTargetMappings
Section titled “bindTargetMappings”
> **bindTargetMappings** : `UnvalidatedJsViewFieldBindTargetMapping`[]
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:56
### code
Section titled “code”
> **code** : `string`
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:59
### hidden
Section titled “hidden”
> **hidden** : `boolean`
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:58
### writeToBindTarget?
Section titled “writeToBindTarget?”
> `optional` **writeToBindTarget** : `UnvalidatedBindTargetDeclaration`
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:57


================================================================================

## 44. /api/interfaces/fieldoptionmap

(/api/interfaces/fieldoptionmap/#_top)
# FieldOptionMap
Defined in: packages/core/src/config/APIConfigs.ts:84
## Properties
Section titled “Properties”
### BUTTON
Section titled “BUTTON”
> **BUTTON** : `ButtonOptions`
Defined in: packages/core/src/config/APIConfigs.ts:90
### BUTTON_GROUP
Section titled “BUTTON_GROUP”
> **BUTTON_GROUP** : `ButtonGroupOptions`
Defined in: packages/core/src/config/APIConfigs.ts:89
### EMBED
Section titled “EMBED”
> **EMBED** : `EmbedOptions`
Defined in: packages/core/src/config/APIConfigs.ts:91
### EXCLUDED
Section titled “EXCLUDED”
> **EXCLUDED** : `undefined`
Defined in: packages/core/src/config/APIConfigs.ts:92
### INPUT
Section titled “INPUT”
> **INPUT** : `InputFieldOptions`
Defined in: packages/core/src/config/APIConfigs.ts:85
### JS_VIEW
Section titled “JS_VIEW”
> **JS_VIEW** : `JsViewFieldOptions`
Defined in: packages/core/src/config/APIConfigs.ts:87
### TABLE
Section titled “TABLE”
> **TABLE** : `TableOptions`
Defined in: packages/core/src/config/APIConfigs.ts:88
### VIEW
Section titled “VIEW”
> **VIEW** : `ViewFieldOptions`
Defined in: packages/core/src/config/APIConfigs.ts:86


================================================================================

## 45. /api/interfaces/partialunvalidatedviewfielddeclaration

(/api/interfaces/partialunvalidatedviewfielddeclaration/#_top)
# PartialUnvalidatedViewFieldDeclaration
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:23
## Extended by
Section titled “Extended by”
  * `UnvalidatedViewFieldDeclaration`


## Properties
Section titled “Properties”
### arguments
Section titled “arguments”
> **arguments** : `UnvalidatedFieldArgument`[]
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:26
### templateDeclaration?
Section titled “templateDeclaration?”
> `optional` **templateDeclaration** : (`string` | `UnvalidatedBindTargetDeclaration`)[]
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:24
### viewFieldType?
Section titled “viewFieldType?”
> `optional` **viewFieldType** : `ParsingResultNode`
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:25
### writeToBindTarget?
Section titled “writeToBindTarget?”
> `optional` **writeToBindTarget** : `UnvalidatedBindTargetDeclaration`
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:27


================================================================================

## 46. /api/interfaces/regexpreplaceinnotebuttonaction

(/api/interfaces/regexpreplaceinnotebuttonaction/#_top)
# RegexpReplaceInNoteButtonAction
Defined in: packages/core/src/config/ButtonConfig.ts:109
## Properties
Section titled “Properties”
### regexp
Section titled “regexp”
> **regexp** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:111
### regexpFlags?
Section titled “regexpFlags?”
> `optional` **regexpFlags** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:112
### replacement
Section titled “replacement”
> **replacement** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:113
### type
Section titled “type”
> **type** : `REGEXP_REPLACE_IN_NOTE`
Defined in: packages/core/src/config/ButtonConfig.ts:110


================================================================================

## 47. /api/interfaces/runtemplaterfilebuttonaction

(/api/interfaces/runtemplaterfilebuttonaction/#_top)
# RunTemplaterFileButtonAction
Defined in: packages/core/src/config/ButtonConfig.ts:75
## Properties
Section titled “Properties”
### templateFile
Section titled “templateFile”
> **templateFile** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:77
### type
Section titled “type”
> **type** : `RUN_TEMPLATER_FILE`
Defined in: packages/core/src/config/ButtonConfig.ts:76


================================================================================

## 48. /api/interfaces/simpleinputfielddeclaration

(/api/interfaces/simpleinputfielddeclaration/#_top)
# SimpleInputFieldDeclaration
Defined in: packages/core/src/parsers/inputFieldParser/InputFieldDeclaration.ts:29
## Properties
Section titled “Properties”
### arguments?
Section titled “arguments?”
> `optional` **arguments** : `SimpleFieldArgument`[]
Defined in: packages/core/src/parsers/inputFieldParser/InputFieldDeclaration.ts:33
### bindTarget?
Section titled “bindTarget?”
> `optional` **bindTarget** : `BindTargetDeclaration`
Defined in: packages/core/src/parsers/inputFieldParser/InputFieldDeclaration.ts:32
### inputFieldType?
Section titled “inputFieldType?”
> `optional` **inputFieldType** : `InputFieldType`
Defined in: packages/core/src/parsers/inputFieldParser/InputFieldDeclaration.ts:30
### templateName?
Section titled “templateName?”
> `optional` **templateName** : `string`
Defined in: packages/core/src/parsers/inputFieldParser/InputFieldDeclaration.ts:31


================================================================================

## 49. /api/interfaces/replaceselfbuttonaction

(/api/interfaces/replaceselfbuttonaction/#_top)
# ReplaceSelfButtonAction
Defined in: packages/core/src/config/ButtonConfig.ts:103
## Properties
Section titled “Properties”
### replacement
Section titled “replacement”
> **replacement** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:105
### templater?
Section titled “templater?”
> `optional` **templater** : `boolean`
Defined in: packages/core/src/config/ButtonConfig.ts:106
### type
Section titled “type”
> **type** : `REPLACE_SELF`
Defined in: packages/core/src/config/ButtonConfig.ts:104


================================================================================

## 50. /api/interfaces/simplebuttongroupdeclaration

(/api/interfaces/simplebuttongroupdeclaration/#_top)
# SimpleButtonGroupDeclaration
Defined in: packages/core/src/parsers/ButtonParser.ts:25
## Properties
Section titled “Properties”
### referencedButtonIds
Section titled “referencedButtonIds”
> **referencedButtonIds** : `string`[]
Defined in: packages/core/src/parsers/ButtonParser.ts:26


================================================================================

## 51. /api/interfaces/replaceinnotebuttonaction

(/api/interfaces/replaceinnotebuttonaction/#_top)
# ReplaceInNoteButtonAction
Defined in: packages/core/src/config/ButtonConfig.ts:95
## Properties
Section titled “Properties”
### fromLine
Section titled “fromLine”
> **fromLine** : `string` | `number`
Defined in: packages/core/src/config/ButtonConfig.ts:97
### replacement
Section titled “replacement”
> **replacement** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:99
### templater?
Section titled “templater?”
> `optional` **templater** : `boolean`
Defined in: packages/core/src/config/ButtonConfig.ts:100
### toLine
Section titled “toLine”
> **toLine** : `string` | `number`
Defined in: packages/core/src/config/ButtonConfig.ts:98
### type
Section titled “type”
> **type** : `REPLACE_IN_NOTE`
Defined in: packages/core/src/config/ButtonConfig.ts:96


================================================================================

## 52. /api/interfaces/simplefieldargument

(/api/interfaces/simplefieldargument/#_top)
# SimpleFieldArgument
Defined in: packages/core/src/parsers/FieldDeclaration.ts:9
## Properties
Section titled “Properties”
### name
Section titled “name”
> **name** : `string`
Defined in: packages/core/src/parsers/FieldDeclaration.ts:10
### value
Section titled “value”
> **value** : `string`[]
Defined in: packages/core/src/parsers/FieldDeclaration.ts:11


================================================================================

## 53. /api/interfaces/simplepropaccess

(/api/interfaces/simplepropaccess/#_top)
# SimplePropAccess
Defined in: packages/core/src/parsers/bindTargetParser/BindTargetDeclaration.ts:24
## Properties
Section titled “Properties”
### prop
Section titled “prop”
> **prop** : `string`
Defined in: packages/core/src/parsers/bindTargetParser/BindTargetDeclaration.ts:26
### type
Section titled “type”
> **type** : `PropAccessType`
Defined in: packages/core/src/parsers/bindTargetParser/BindTargetDeclaration.ts:25


================================================================================

## 54. /api/interfaces/simplejsviewfieldbindtargetmapping

(/api/interfaces/simplejsviewfieldbindtargetmapping/#_top)
# SimpleJsViewFieldBindTargetMapping
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:74
## Properties
Section titled “Properties”
### bindTarget
Section titled “bindTarget”
> **bindTarget** : `BindTargetDeclaration`
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:75
### name
Section titled “name”
> **name** : `string`
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:76


================================================================================

## 55. /api/interfaces/simpleviewfielddeclaration

(/api/interfaces/simpleviewfielddeclaration/#_top)
# SimpleViewFieldDeclaration
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:30
## Properties
Section titled “Properties”
### arguments?
Section titled “arguments?”
> `optional` **arguments** : `SimpleFieldArgument`[]
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:33
### templateDeclaration?
Section titled “templateDeclaration?”
> `optional` **templateDeclaration** : (`string` | `BindTargetDeclaration`)[]
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:32
### viewFieldType?
Section titled “viewFieldType?”
> `optional` **viewFieldType** : `string`
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:31
### writeToBindTarget?
Section titled “writeToBindTarget?”
> `optional` **writeToBindTarget** : `BindTargetDeclaration`
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:34


================================================================================

## 56. /api/interfaces/simplejsviewfielddeclaration

(/api/interfaces/simplejsviewfielddeclaration/#_top)
# SimpleJsViewFieldDeclaration
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:67
## Properties
Section titled “Properties”
### bindTargetMappings
Section titled “bindTargetMappings”
> **bindTargetMappings** : `SimpleJsViewFieldBindTargetMapping`[]
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:68
### code
Section titled “code”
> **code** : `string`
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:71
### hidden?
Section titled “hidden?”
> `optional` **hidden** : `boolean`
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:70
### writeToBindTarget?
Section titled “writeToBindTarget?”
> `optional` **writeToBindTarget** : `BindTargetDeclaration`
Defined in: packages/core/src/parsers/viewFieldParser/ViewFieldDeclaration.ts:69


================================================================================

## 57. /guides/advancedusecases

(/guides/advancedusecases/#_top)

Search ` `Ctrl``K` `
Cancel 




# Advanced Use-Cases
If you are willing to dip your toes into the world of JavaScript, you can do quite a few interesting things with Meta Bind.
Note
The following examples assume that you have:
  1. JS Engine installed and enabled.
  2. Enabled **JavaScript** in the Meta Bind settings.


Caution
I would recommend that you are familiar with JavaScript before attempting to use these examples. If you are not careful, you can easily create infinite loops or other performance issues.
## Performance Considerations
Section titled “Performance Considerations”
Dynamically creating input or view fields with JavaScript can have a performance impact, especially if you are doing it all over your notes.
## Dynamic Bind Targets with JavaScript
Section titled “Dynamic Bind Targets with JavaScript”
You can use JavaScript to dynamically change a bind target based on another bind targets value.
This example demonstrates how to use a select input to change the bind target of a number input. The select input is bound to the `index` variable, and the number input is constructed to be bound to the `list[index]` variable.
```

---
list:
-1
-2
-3
index:0
---
Index: `INPUT[inlineSelect(option(0),option(1),option(2)):index]`
```meta-bind-js-view
{index} asindex
---
conststr=`\`INPUT[number:list[${context.bound.index}]]\``;
return engine.markdown.create(str)
```

```

## Dynamic Options for Select Inputs
Section titled “Dynamic Options for Select Inputs”
You can also use JavaScript to dynamically change the options of a select input.
```

---
options:
-"1"
-"2"
-"3"
selected:1
---
Options: `INPUT[inlineList:options]`
```meta-bind-js-view
{options} asoptions
---
constoptions= context.bound.options.map(x=>`option(${x})`).join(", ");
conststr=`\`INPUT[inlineSelect(${options}):selected]\``;
return engine.markdown.create(str);
```

```

## Additional Examples
Section titled “Additional Examples”
There are additional advanced examples available in the GitHub Repository here. Have another one? Please submit a pull request.
 Previous API   Next Customizing MathJS 


================================================================================

## 58. /guides/buttons

(/guides/buttons/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Buttons
Button are well… Buttons, inside your notes. They can be configured to do a variety of things, like opening a file, running a command, or even running a JavaScript file.
Note
A list of button actions, their required properties, and examples can be found in the sidebar under `Reference -> Button Actions`.
## Creating a button
Section titled “Creating a button”
Tip
Buttons can be easily created using the `Open Button Builder` command.
To create a button, you need to create a code block with the language set to `meta-bind-button`. The inside of the code block belongs the configuration in YAML format for the button.
The following example button displays `Meta Bind Help` and opens the meta bind FAQ page.
```

```meta-bind-button
style:primary
label:Meta Bind Help
action:
type:command
command:obsidian-meta-bind-plugin:mb-open-faq
```

```

## Inline Buttons
Section titled “Inline Buttons”
Inline buttons are buttons that are displayed inline with the text. They are created using inline code blocks starting with `BUTTON`. Inline buttons must reference a button code block defined elsewhere in the **same note** via matching ids.
Buttons declared in the plugin’s settings under `Button Templates` can be referenced by inline buttons in every note.
The following example button inline button references the code block button with the `help-button` id below it. By referencing the button code block, the inline button will have the same configuration as the code block button. The code block button can be hidden by setting the `hidden` YAML property to `true`.
```

Meta Bind has an in plugin help page. `BUTTON[help-button]` Isn't that cool?
```meta-bind-button
style:primary
label:Meta Bind Help
id:help-button
action:
type:command
command:obsidian-meta-bind-plugin:open-faq
```

```

## Button Groups
Section titled “Button Groups”
Inline buttons can display multiple buttons in a row. For this, multiple button ids separated by commas need to be passed to the `BUTTON` inline code block.
The following example displays a button group of two buttons.
```

Theme Switcher: `BUTTON[light-mode, dark-mode]`
```meta-bind-button
style:destructive
label:Light Mode
id:light-mode
hidden:true
actions:
-type:command
command:theme:use-light
```
```meta-bind-button
style:primary
label:Dark Mode
id:dark-mode
hidden:true
actions:
-type:command
command:theme:use-dark
```

```

## Button Configuration
Section titled “Button Configuration”
### Button Properties
Section titled “Button Properties”
The YAML configuration of a button must adhere to the following TypeScript interface.
```

interfaceButtonConfig {
// Required fields:
// The text displayed on the button.
label:string;
// The style of the button.
style:'default'|'primary'|'destructive'|'plain';
// Optional fields:
// An optional lucide icon to display on the button.
icon?:string;
// Optional CSS classes to add to the button. Multiple classes can be separated by spaces.
class?:string;
// Optional CSS inline stiles to apply to the button.
cssStyle?:string;
// Optional path to a background image for the button.
backgroundImage?:string;
// Optional tooltip to display when hovering over the button. If not set, the label is used.
tooltip?:string;
// The optional id of the button, used for referencing the button in inline buttons.
id?:string;
// Whether this button should be hidden, useful when only using the button in inline buttons.
hidden?:boolean;
// Button Actions:
// The action to perform when the button is clicked.
action?:ButtonAction;
// Optionally multiple actions can be performed when the button is clicked.
actions?:ButtonAction[];
}

```

`action` and `actions` are mutually exclusive, meaning that only one of them can be used.
For examples of how to style buttons with CSS classes, see the `Styling and CSS` page.
## Button Actions
Section titled “Button Actions”
Button actions can require multiple properties depending on the type of action, but every action has a `type` property, by which it is identified.
A list of button actions and their required properties can be found in the sidebar under `Reference -> Button Actions`.
 Previous View Fields   Next Meta Bind Embeds 


================================================================================

## 59. /guides/examples

(/guides/examples/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Examples
There are two places where you can look for examples.
## Playground
Section titled “Playground”
The first place to look for examples is the playground that is build into the plugin. It can be opened from the plugins settings, or with the `Meta Bind: Open playground` command. There you will find an interactive list of all input and view fields to play around with.
## Example Vault
Section titled “Example Vault”
The GitHub repository of the plugin contains an example vault. The example vault is used for testing and is always up-to-date with the **latest development version** of the plugin, but you will need to install the plugin yourself or build it via the `bun run dev` command, run from the root of the repo. This means that **not everything in the example vault necessarily works in the current release version of the plugin**. If you want to view the example vault for a specific release, you can find it by looking at the release on GitHub. There you will find a link that takes you to the corresponding tag for that release. From there you can download the example vault for that release.
 Previous Installation   Next Styling and CSS 


================================================================================

## 60. /api/interfaces/tableoptions

(/api/interfaces/tableoptions/#_top)
# TableOptions
Defined in: packages/core/src/config/APIConfigs.ts:44
## Properties
Section titled “Properties”
### bindTarget
Section titled “bindTarget”
> **bindTarget** : `BindTargetDeclaration`
Defined in: packages/core/src/config/APIConfigs.ts:45
### columns
Section titled “columns”
> **columns** : `MetaBindColumnDeclaration`[]
Defined in: packages/core/src/config/APIConfigs.ts:47
### tableHead
Section titled “tableHead”
> **tableHead** : `string`[]
Defined in: packages/core/src/config/APIConfigs.ts:46


================================================================================

## 61. /api/interfaces/sleepbuttonaction

(/api/interfaces/sleepbuttonaction/#_top)
# SleepButtonAction
Defined in: packages/core/src/config/ButtonConfig.ts:61
## Properties
Section titled “Properties”
### ms
Section titled “ms”
> **ms** : `number`
Defined in: packages/core/src/config/ButtonConfig.ts:63
### type
Section titled “type”
> **type** : `SLEEP`
Defined in: packages/core/src/config/ButtonConfig.ts:62


================================================================================

## 62. /guides/bindtargets

(/guides/bindtargets/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Bind Targets
Bind Targets are a core concept of Meta Bind. They are a text based way to point the plugin at a specific frontmatter property. This tutorial will teach you how to use them.
Limitations
Bind targets are **static** , meaning that they can not be changed after they have been created.
This means that you can **not** have a property that controls where a bind target points to, without using JavaScript. See Advanced Examples.
## Syntax
Section titled “Syntax”
Bind Targets consist of three parts.
```

storageType^storagePath#property

```

The `storageType` and `storagePath` can be omitted, causing them to default to their default values.
The following bind target will always use the default storage type `frontmatter`, meaning it points to a frontmatter property.
```

storagePath#property

```

The following bind targets will always use the containing file as the storage path. Containing file means the file the bind target or field, that the bind target is part of, is in.
```

property
storageType^property

```

### Default Values Example
Section titled “Default Values Example”
This means that the following bind targets are **equivalent** , assuming the current file is `Test Note`.
```

property
frontmatter^Test Note#property

```

### 1. The Storage Type
Section titled “1. The Storage Type”
The storage type tells the plugin where the storage path is pointing to. There are four different storage types. The default is `frontmatter` and will be used if you don’t specify a storage type.
Storage Type| Description  
---|---  
`frontmatter` (default)| The storage path points to a file and the property to a frontmatter field.  
`memory`| The storage path points to a file and the property to an in-memory field.  
`globalMemory`| The storage path is not allowed and the property points to an in-memory field.  
`scope`| The storage path is not allowed and the property extends another bind target.  
#### `frontmatter`
Section titled “frontmatter”
This refers the Obsidian’s frontmatter which is a YAML block at the top of a file.
#### `memory`
Section titled “memory”
Memory is an in-memory storage that is **scoped** but not saved to any file. This means that values you write to a file path in the cache **will be lost** when nothing uses said file path for a while, or you restart Obsidian.
#### `globalMemory`
Section titled “globalMemory”
Global Memory is an in-memory storage that is **not scoped** and not saved to any file. Global Memory is shared between all notes and **will be lost** when you restart Obsidian.
### 2. The Storage Path
Section titled “2. The Storage Path”
The storage path usually points to a file. If omitted, it defaults to the containing file. Containing file means the file the bind target or field, that the bind target is part of, is in.
#### Example
Section titled “Example”
Let’s imagine we are in a note called `Overview` and we want our toggle not to change this note’s completion status, but the status of our task note called `Task A`. This is also possible. We just need to tell the plugin to change `completed` in note `Task A`. We do this by binding to `Task A#completed` (`file_name#frontmatter_field`).
The input field declaration now looks like this.
```

INPUT[toggle:Task A#completed]

```

If you have multiple notes with the same name, simply specifying the name will not be enough, as the plugin can’t figure out which one you are referring to. In that case you need to specify the full path relative to the vault root.
```

INPUT[toggle:path/to/Task A#completed]

```

### 3. The Property
Section titled “3. The Property”
The property is the name of the field you want to bind to. For the default storage type `frontmatter`, this is the name of the frontmatter property.
#### Properties with Spaces and Nested Properties
Section titled “Properties with Spaces and Nested Properties”
The plugin uses JavaScript-like syntax to access the frontmatter. This means that in order to bind to a frontmatter field with special characters such as spaces, you need to use JavaScript’s bracket syntax.
This will **not** work.
```

INPUT[toggle:is completed]

```

But this will.
```

INPUT[toggle:["is completed"]]

```

To access nested frontmatter fields, you can use a simple `.` or bracket syntax. The following two examples are **equivalent**.
```

INPUT[toggle:this.is.nested]

```

```

INPUT[toggle:this["is"].nested]

```

 Previous Meta Bind Embeds   Next API 


================================================================================

## 63. /guides/inputfields

(/guides/inputfields/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Input Fields
Input fields allow you to create input fields for your notes metadata and interact with them in live preview and reading mode. A bit like Obsidians properties UI, but not just at the top of your note.
### Creating Input Fields
Section titled “Creating Input Fields”
There are two ways of creating an input field in your note.
The first is using an **inline** code block, like this `INPUT[inputType]`. The second one is using a **code block** with meta-bind as the language, something like this.
```

```meta-bind
INPUT[inputType]
```

```

Where `inputType` is a valid input field type, like `toggle`.
## Binding to Metadata
Section titled “Binding to Metadata”
Tip
You can find an in depth guide on bind targets and what is possible here.
Input fields can and should be bound to metadata fields, so properties in your frontmatter. This is achieved by adding the bind target behind the input type, separated by a colon.
In this example we will build a toggle that toggles the notes completion status by switching the `completed` front-mater field between `true` and `false`.
First, we create a toggle.
```

INPUT[toggle]

```

Then we tell it to bind to the `completed` frontmatter field using a Bind Target.
```

INPUT[toggle:completed]

```

And our input field is working. The toggle will change the frontmatter and when the frontmatter changes, the toggle changes.
Of course you can utilize the full functionality of Bind Targets with input field. E.g. the following is possible.
```

INPUT[toggle:memory^completed]

```

Note
Specifying a bind target is optional, but recommended.
If you don’t specify a bind target, the input field will not preserve its state when you reopen the note or restart Obsidian, since the input field has nowhere to store its data.
An input field will only write to it’s bound value when it’s interacted with. This means for example, that an input field does not automatically, on load, create it’s bound property when that property does not yet exist.
## Arguments
Section titled “Arguments”
Some input types support arguments to further customize them. Arguments are specified in parentheses behind the input type.
Let’s say we want to create a dropdown select where you can choose between different ratings. For this we will use the `inlineSelect` input field. To add options to the dropdown select we will use the `option(name)` argument.
```

INPUT[inlineSelect(
option(bad),
option(meh),
option(ok),
option(good),
option(great)
):rating]

```

Now we can see four options in the dropdown.
If we want numeric values to represent the rating in our frontmatter, we can pass two values to `option(value, name)`.`value` will be the value written to the frontmatter and `name` will be the value displayed in the dropdown select.
```

INPUT[inlineSelect(
option(1, bad),
option(2, meh),
option(3, ok),
option(4, good),
option(5, great)
):rating]

```

We can also include commas in our value names by surrounding them with single quotes. Note that only single quotes are supported, double quotes will not work.
```

INPUT[inlineSelect(
option(1,'if you value your time, do not watch'),
...
):rating]

```

Such strings also support escaping using a backslash. To have a single backslash in the name you can use a double backslash `\\`.
```

INPUT[inlineSelect(
option(1,'if you value your time, don\'t watch'),
...
):rating]

```

 Previous Obsidian Publish   Next Input Field Templates 


================================================================================

## 64. /guides/stylingandcss

(/guides/stylingandcss/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Styling and CSS
To style various Meta Bind elements you need to write custom CSS. The easiest way to load custom CSS into Obsidian is with a CSS snippet.
### Input Field Styling Example
Section titled “Input Field Styling Example”
Let’s say we want to color specific progress bars red. For this we can utilize the `class` argument.
First we create our progress bar with the class argument. In this case we name our special class `red-progress-bar`.
```

INPUT[progressBar(class(red-progress-bar)):someProperty]

```

Then we create our CSS snippet with a selector for a progress bar with the class `red-progress-bar`. Then we target the progress bar progress element and set the background color to red.
snippet.css```

.mb-input-type-progressBar.red-progress-bar.mb-progress-bar-progress {
background:var(--color-red);
}

```

In some cases you might need higher specificity to override existing styles. In this case you can use the `!important` flag.
snippet.css```

.mb-input-type-progressBar.red-progress-bar.mb-progress-bar-progress {
background:var(--color-red) !important;
}

```

### Button Styling Example
Section titled “Button Styling Example”
If you want to change the style of a specific button, you can specify a CSS class for the button and then target it with a CSS snippet.
First we create a button and specify a custom class, in this case `green-button`.
```

style:primary
label:Open Meta Bind FAQ
class:green-button
action:
type:command
command:obsidian-meta-bind-plugin:open-faq

```

Then we create our CSS snippet with a selector for a Meta Bind button with the class `green-button`. Then we target the button element itself and set it’s color to green.
snippet.css```

.mb-button.green-button>button {
color:var(--color-green);
}

```

In some cases you might need higher specificity to override existing styles. In this case you can use the `!important` flag.
snippet.css```

.mb-button.green-button>button {
color:var(--color-green) !important;
}

```

 Previous Examples   Next Obsidian Publish 


================================================================================

## 65. /guides/custommathjs

(/guides/custommathjs/#_top)

Search ` `Ctrl``K` `
Cancel 




# Customizing MathJS
You may find yourself wanting to add functionality to the math view fields. And as they use mathjs internally, you actually can!
## Importing new options into mathJS
Section titled “Importing new options into mathJS”
The mathjs library allows the user to define his own functions and constants, as described in their documentation.
To leverage that, Meta Bind exposed its mathjs instance for you to modify. The most sensible place to do this, is inside a JS Engine startup script. This ensures the modifications are loaded early and will be immediately available when the first documents gets rendered.
Caution
Modifying mathJS via a `js-engine` codeblock inside a document may cause timing problems and is not recommended!
### Adding a custom function `clamp`
Section titled “Adding a custom function clamp”
As an example, we will define a `clamp()` function, which is not part of default mathJS, but can be very helpful. The function should take in three parameters, the current value, a minimum, and a maximum. It returns the current value as long as its inside the range otherwise the boundary-value.
```

clamp: (val, min, max) => Math.min(Math.max(min, val), max);

```

Add this definitions inside a JavaScrypt file stored in you Vault and enable that file to be run as a startup script. Inside the file you can use the `mathJSImport(dict, options)` function from the API to import you definitions into mathjs.
```

constmb= engine.getPlugin('obsidian-meta-bind-plugin').api;
mb.mathJSImport({
// definition of the clamp function
clamp: (val, min, max) => Math.min(Math.max(min, val), max),
// we can also define useful constants here
foo:42,
});

```

Now you can use this newly defined function in a view field. This example will always display values between 0 and 10, even if `num` gets outside that range.
```

VIEW[clamp({num}, 0, 10)]

```

You can also use the new constant `foo`. The following example will display `52`.
```

VIEW[foo + 10]

```

 Previous Advanced Use-Cases   Next Date 


================================================================================

## 66. /guides/installation

(/guides/installation/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Installation
The easiest way to install the plugin is through Obsidian’s plugin browser.
Here is a quick link to it.
## Canary Builds
Section titled “Canary Builds”
Caution
Canary builds are not intended for the normal user. They are intended for testing and previewing new features.
If you are not sure if you should use canary builds, you probably shouldn’t.
Canary builds are builds containing under development features. They are not guaranteed to be stable. Canary build might contain new features that are **not yet ready** and therefore might not work as expected or break. These feature previews may introduce **breaking changes without warning**. There is no changelog for canary builds.
If you don’t know if you are using a canary build, you can look at the version number in the Obsidian settings. Canary builds have a version number ending in `-canary` plus a timestamp, e.g. `0.9.0-canary.20231129T131457`.
Canary builds can be installed using BRAT by following the steps outlined below.
  1. Install and enable the BRAT plugin
  2. Run the BRAT: Plugins: Add a beta plugin for testing command
  3. Enter  into the text field
  4. Click on Add Plugin


 Next Examples 


================================================================================

## 67. /guides/api

(/guides/api/#_top)

Search ` `Ctrl``K` `
Cancel 




# Meta Bind API
Meta Bind offers a JavaScript API that allows you to interact with the Meta Bind internals via JavaScript.
Documentation for the API can be found here.
## Usage
Section titled “Usage”
To use the API you need some way to execute JavaScript. This can be done with another plugin like JS Engine or Dataview.
Before you can use the API, you need to get a reference to it. This can be done via first getting an instance to the loaded Meta Bind plugin and then getting the API from it.
  *  With JS Engine 
  *  Plain JavaScript 


```

// First we get an instance of the Meta Bind plugin, then we access the API.
// If the plugin is not loaded, this will return `undefined`.
constmb= engine.getPlugin('obsidian-meta-bind-plugin')?.api;
// Optional: Handle the case where the plugin is not loaded.
if (!mb) {
// ...
}
// Now we can use the API!

```

```

// `app` refers to the Obsidian App object, depending on how you execute JavaScript you might need to get it from somewhere.
// First we get an instance of the Meta Bind plugin, then we access the API.
// If the plugin is not loaded, this will return `null`.
constmb= app.plugins.getPlugin('obsidian-meta-bind-plugin')?.api;
// Optional: Handle the case where the plugin is not loaded.
if (!mb) {
// ...
}
// Now we can use the API!

```

Caution
Do not try to use API methods as standalone functions. This will lead to errors, as the class method looses it’s reference to itself via `this`.
```

// DON'T DO THIS
const { someAPIMethod } = app.plugins.getPlugin('obsidian-meta-bind-plugin')?.api;
someAPIMethod(); // will most likely error
// OR
constsomeAPIMethod= app.plugins.getPlugin('obsidian-meta-bind-plugin')?.api.someAPIMethod;
someAPIMethod(); // will most likely error
// DO THIS
constmb= app.plugins.getPlugin('obsidian-meta-bind-plugin')?.api;
mb.someAPIMethod(); // works

```

This is a general issue with JavaScript classes.
```

classFoo {
constructor() {
this.bar =5;
}
baz() {
console.log(this.bar);
}
}
constfoo=newFoo();
foo.baz(); // will log 5
const { baz } = foo;
// `baz` became a standalone function and thus `this` is now `undefined`.
baz(); // error: can't access property `bar`, `this` is `undefined`
constbaz2= foo.baz;
// `baz2` became a standalone function and thus `this` is now `undefined`.
baz2(); // error: can't access property `bar`, `this` is `undefined`

```

## Lifecycle Management
Section titled “Lifecycle Management”
Danger
Not handling the lifecycle of mountable objects can lead to memory leaks and other bugs. Make sure to read this section carefully and remember always clean up after yourself.
Lifecycle management is very important when working with the Meta Bind API. You need to make sure that you clean up after yourself to prevent memory leaks and other bugs.
Most things that need lifecycle managment inherit from `Mountable`, which has a `mount` and `unmount` method. If you call `mount`, you need to call `unmount` at some point.
The API provides a helper function called `wrapInMDRC` that can be used to handle the lifecycle of a mountable object for you.
```

// Create a mountable object.
constmountable=...;
// Mount the mountable via the helper function.
// `container` is the parent HTMLElement that the mountable should be mounted to.
// `component` is an Obsidian `Component` object.
mb.wrapInMDRC(mountable, container, component);

```

In the background this will create a `MarkdownRenderChild` which mounts and unmounts the mountable on load and unload respectivly and then registers that `MarkdownRenderChild` as a child of the component.
You can also handle the lifecycle yourself by mounting the mountable to the DOM and then registering a callback to unmount it when the component is destroyed.
```

// Create a mountable object.
constmountable=...;
// Mount the mountable to the DOM.
mountable.mount(container);
// Register a callback to unmount the mountable when the component is destroyed.
component.register(() => mountable.unmount());

```

## Examples
Section titled “Examples”
Note
The following examples use `js-engine` code blocks from the JS Engine plugin. To use the examples as they are, make sure you have the JS Engine plugin installed and enabled. Though the API is usable without it, the examples might not work without JS Engine.
The used globals that are exclusive to JS Engine are as follows. For more information on them refer to the JS Engine documentation.
  * `engine` - Refers to the JS Engine API.
  * `context.file` - The `TFile` object for file containing the `js-engine` code block. This is only available in the context of a note.
  * `container` - The container for the rendered content. This is of type `HTMLElement`.
  * `component` - An Obsidian `Component` for lifecycle management.


### Buttons
Section titled “Buttons”
Creating a button via the API.
```

// First we get an instance of the Meta Bind plugin, then we access the API.
constmb= app.plugins.getPlugin('obsidian-meta-bind-plugin')?.api;
// We create a button configuration object.
constbuttonConfig= {
label:'Greet the World',
style:'primary',
action: {
type:'inlineJS',
code:"console.log('Hello World!');",
},
};
// We specify the button options.
constbuttonOptions= {
declaration: buttonConfig,
isPreview:false,
};
// We create the button. This will return something that inherits from `Mountable` and can be mounted to the DOM.
constbutton= mb.createButtonMountable(context.file.path, buttonOptions);
// Mount the button to the DOM and make sure it gets unmounted when the component is destroyed.
mb.wrapInMDRC(button, container, component);

```

If you are daring you can skip the intermediate objects.
```

// First we get an instance of the Meta Bind plugin, then we access the API.
constmb= app.plugins.getPlugin('obsidian-meta-bind-plugin')?.api;
// We create the button. This will return something that inherits from `Mountable` and can be mounted to the DOM.
constbutton= mb.createButtonMountable(context.file.path, {
// the button options
declaration: {
// the button config
label:'Greet the World',
style:'primary',
action: {
type:'inlineJS',
code:"console.log('Hello World!');",
},
},
isPreview:false,
});
// Mount the button to the DOM and make sure it gets unmounted when the component is destroyed.
mb.wrapInMDRC(button, container, component);

```

### Input Fields
Section titled “Input Fields”
Creating an input field via the API.
```

constmb= engine.getPlugin('obsidian-meta-bind-plugin').api;
constprimeNumberBound=200;
/*
* A function to calculate prime numbers up to a given bound.
*/
functioncalculatePrimeNumbers(bound) {
constprimeNumbers= [2];
for (let i =3; i <= bound; i++) {
let halfI = i /2;
for (constpof primeNumbers) {
if (p > halfI) {
primeNumbers.push(i);
break;
}
if (i % p ===0) {
break;
}
}
}
return primeNumbers;
}
// Create the input field declaration with the bind target and arguments.
constdeclaration= {
inputFieldType:'suggester',
bindTarget: mb.createBindTarget('frontmatter', context.file.path, ['favoritePrime']),
arguments:calculatePrimeNumbers(primeNumberBound).map(x=> {
return {
name:'option',
value: [x.toString()],
};
}),
};
// Create the input field options.
constoptions= {
declaration: declaration,
renderChildType:'block',
};
// Create the input field.
constinputField= mb.createInputFieldMountable(context.file.path, options);
// Mount the input field to the DOM and make sure it gets unmounted when the component is destroyed.
mb.wrapInMDRC(inputField, container, component);

```

 Previous Bind Targets   Next Advanced Use-Cases 


================================================================================

## 68. /guides/templates

(/guides/templates/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Input Field Templates
Templates allow you to reuse input fields across your vault. You can specify them in the plugins settings.
## Using Templates
Section titled “Using Templates”
First, we need to create a template in the plugin settings. Let’s create a template for a slider as follows.
Template Name| Template String  
---|---  
`sliderTemplate`| `INPUT[slider(addLabels, minValue(0), maxValue(10))]`  
Notice that the template is **not** bound to any metadata.
To use the template, we open a note and write the following.
```

INPUT[templateName][overrides]

```

Here, `overrides` may consist of an input field type, arguments and a bind target. It can also be empty if you don’t want to override anything from the template.
For example, if we want to use the `sliderTemplate` for some `rating` we have in frontmatter, we would write:
```

INPUT[sliderTemplate][:rating]

```

We have set `templateName` to `sliderTemplate` (telling meta-bind to use the template we created earlier), and in the `overrides` we bind the input field to the frontmatter property `rating`.
 Previous Input Fields   Next View Fields 


================================================================================

## 69. /guides/obsidianpublish

(/guides/obsidianpublish/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Obsidian Publish Support
Danger
I am currently waiting for the Obsidian Team to deliver on promised improvements to the Obsidian Publish API. Until then, Meta Binds publish support will be broken.
Use at your own risk. I do not accept issues and feature requests for publish specific issues at this point in time.
This guide assumes that you already have Obsidian Publish set up with a custom domain, so that you can use a `publish.js` file.
To get meta bind working in Obsidian Publish, you need to copy the contents of this file into your `publish.js` file. For the correct appearance, you need to copy this file into your `publish.css` file.
 Previous Styling and CSS   Next Input Fields 


================================================================================

## 70. /api/interfaces/templatercreatenotebuttonaction

(/api/interfaces/templatercreatenotebuttonaction/#_top)
# TemplaterCreateNoteButtonAction
Defined in: packages/core/src/config/ButtonConfig.ts:66
## Properties
Section titled “Properties”
### fileName?
Section titled “fileName?”
> `optional` **fileName** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:70
### folderPath?
Section titled “folderPath?”
> `optional` **folderPath** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:69
### openIfAlreadyExists?
Section titled “openIfAlreadyExists?”
> `optional` **openIfAlreadyExists** : `boolean`
Defined in: packages/core/src/config/ButtonConfig.ts:72
### openNote?
Section titled “openNote?”
> `optional` **openNote** : `boolean`
Defined in: packages/core/src/config/ButtonConfig.ts:71
### templateFile
Section titled “templateFile”
> **templateFile** : `string`
Defined in: packages/core/src/config/ButtonConfig.ts:68
### type
Section titled “type”
> **type** : `TEMPLATER_CREATE_NOTE`
Defined in: packages/core/src/config/ButtonConfig.ts:67


================================================================================

## 71. /guides/metabindembed

(/guides/metabindembed/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Meta Bind Embed
Meta Bind Embeds are a way to embed a note inside another note, which works a bit differently than the normal Obsidian embeds.
Together with Meta Binds other features, they allow you to build dynamic templates. The major disadvantage with a traditional template based approach is that modifications to the templates don’t automatically apply to all notes created using that template. Meta Bind Embeds on the other hand propagate changes to the “template” to all notes embedding it instantly, since the “template” file is read every time the note renders and not just once when the note is created.
## Differences to Obsidian Embeds
Section titled “Differences to Obsidian Embeds”
Let’s say you have a note called `Note A` that you want to embed in `Note B`.
Using the normal Obsidian embeds, you would write `![[Note A]]` in `Note B`. This embeds the note, but it’s not seamless. The content of `Note A` still thinks it’s part of `Note A` and not `NoteB`. This means any widgets like Input Fields in the embed will bind to and change the frontmatter of `Note A` instead of `Note B`.
This is where Meta Bind Embeds come in. They seamlessly embed `Note A` and make it think it is a part of `Note B`. Meaning any Input Fields in the embed will bind to `Note B` and not `Note A`. And this even extends to markdown decorations added by other plugins.
## Syntax
Section titled “Syntax”
Meta Bind Embeds are created using a code block with the language `meta-bind-embed`. The content of the code block is a single link to the note you want to embed.
The following example embeds `Note A` in `Note B`.
```

This is Note B.
```meta-bind-embed
[[Note A]]
```

```

 Previous Buttons   Next Bind Targets 


================================================================================

## 72. /guides/viewfields

(/guides/viewfields/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# View Fields
View Fields are a powerful way to reactively display your metadata in your notes. They can bind to multiple frontmatter fields and the view field update as soon as the value of the frontmatter fields change, much like dataview inline queries, but with instant updates. View fields can even do computations and save their computed value back to the frontmatter.
## Creating View Fields
Section titled “Creating View Fields”
Imagine we have a note which we use to plan an upcoming hiking trip. In the frontmatter we already created a field that tracks the distance in kilometers of the trip. And we created an input field to change the distance from within our note. It looks something like this.
```

Distance: `INPUT[number:distance]` km

```

But now we want to, for our american friends, know how long that is in freedom units. This is where view fields come in.
```

Distance: `INPUT[number:distance]` km
Distance in freedom units: `VIEW[{distance}]` miles

```

This will display the distance and change when we change the value using the input field above, but we are still missing the conversion. At this point mathjs becomes useful. With it, we can simply convert the km into miles.
```

Distance: `INPUT[number:distance]` km
Distance in freedom units: `VIEW[number({distance} km, miles)]` miles

```

To make it a bit nicer to view, we can also round the number to two decimal places. And the displayed value still changes instantly when we change the distance using the input field.
```

Distance: `INPUT[number:distance]` km
Distance in freedom units: `VIEW[round(number({distance} km, miles), 2)]` miles

```

The references to the frontmatter in the curly brackets follow the same Bind Target rules as the bind target for input fields. So if for some reason you don’t want to persist the value to the frontmatter, you can use the `memory` storage type.
```

Distance: `INPUT[number:memory^distance]` km
Distance in freedom units: `VIEW[round(number({memory^distance} km, miles), 2)]` miles

```

## View Field Types
Section titled “View Field Types”
You can also specify a view field type. The default (if you don’t specify any) is `math`.
Specifying a view field type is done like so.
```

VIEW[content][viewFieldType]

```

This means the following two examples are equivalent. Both calculate `a` times `b`.
```

VIEW[{a} * {b}]
VIEW[{a} * {b}][math]

```

## Arguments
Section titled “Arguments”
View fields, like input fields, support arguments to further customize them. The syntax for them is also the same, meaning they are specified in parentheses behind the view field type.
If for example you want your `text` view field to render markdown instead of plain text, you can add the `renderMarkdown` argument like this.
```

VIEW[**{someText}**][text(renderMarkdown)]

```

This will render the text stored in the `someText` frontmatter property as markdown.
## Saving the Value
Section titled “Saving the Value”
You can save the value computed by a view field back to a frontmatter property by specifying a “write-to” bind target. See Bind Targets.
Let’s say you want to compute a value `c` that has the value of `a * b`, in other words you want to compute `a * b` and save the result to `c`. This can be done by specifying `c` as the “write-to” bind target of the view field like so.
```

VIEW[{a} * {b}][math:c]

```

### Circular Dependencies
Section titled “Circular Dependencies”
Of course you can abuse this and create circular dependencies that cause Obsidian to crash by doing something like the following example.
```

VIEW[{a}][math:b]
VIEW[{b} + 1][math:a]

```

Or like this.
```

VIEW[{a} + 1][math:a]

```

Meta Bind **will detect** these dependency loops and **will prevent** you accidentally locking yourself out of Obsidian and your notes.
### Limitations
Section titled “Limitations”
View fields will only work if you have the note, in which they are located, open.
Let’s say you have two notes, `NoteA` and `NoteB`.
`NoteA` looks like this.
NoteA.md```

---
someInputValue:1
someComputedValue:2
---
Input: `INPUT[number:someComputedValue]`
Computed Value: `VIEW[{someInputValue} * 2][math:someComputedValue]`

```

And let’s say you want to also change and read the values of `NoteA` in `NoteB`.
So `NoteB` looks like this.
NoteB.md```

Input: `INPUT[number:NoteA#someComputedValue]`
Computed Value: `VIEW[{NoteA#someComputedValue}]`

```

If you have both notes open the view field in `NoteB` will update as expected, when you change the input value using the input field. But if you close `NoteA` (so that only `NoteB` is open), then the view field will no longer update, since the view field that does the computation is in `NoteA` and that note is no longer loaded.
## JS View Fields
Section titled “JS View Fields”
You can create View Fields powered by JavaScript as well. Those can only be created as code blocks and **not inline**. By default, JS View Fields are disabled, as they can pose a security risk.
Note
This feature requires the that you have the following:
  1. JS Engine installed and enabled.
  2. Enabled **JavaScript** in the Meta Bind settings.


JS View Fields consist of two sections, separated by `---`. The first section contains Bind Targets and other configuration. The second section contains the JavaScript code.
When rendered, the JS view field displays the value returned in the JavaScript section just as JS Engine would. This means you can do things like rendering markdown.
The same variables and APIs that are available in JS Engine code blocks are also available in JS view fields. The bound variables are available in the `context.bound` object.
The JS View Field will automatically update when one of the bound variables of the bind target sections changes.
### Examples
Section titled “Examples”
```

```meta-bind-js-view
{bind_target} asvar1
{other_note#bind_target} asvar2
---
return`${context.bound.var1*context.bound.var2} km`;
```

```

The following example will save it’s value to another Bind Targets.
```

```meta-bind-js-view
{bind_target} asvar1
{other_note#bind_target} asvar2
save to {other_bind_target}
---
return`${context.bound.var1*context.bound.var2} km`;
```

```

The following JS View Field will additionally be hidden.
```

```meta-bind-js-view
{bind_target} asvar1
{other_note#bind_target} asvar2
save to {other_bind_target}
hidden
---
return`${context.bound.var1*context.bound.var2} km`;
```

```

 Previous Input Field Templates   Next Buttons 


================================================================================

## 73. /buttonactions/command

!
**We're having a really bad day.**
The Unicorns have taken over. We're doing our best to get them under control and get GitHub back up and running.
Contact Support — GitHub Status — @githubstatus
 ![ ](https://www.moritzjung.dev/)  ![ ](https://www.moritzjung.dev/)


================================================================================

## 74. /inputfieldarguments/addlabels

(/inputfieldarguments/addlabels/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Add Labels
Identifier | `addLabels`  
---|---  
Allows Multiple | `false`  
### Description
Section titled “Description”
The `addLabels` argument lets you add a labels to a `slider` or `progressBar`. The value passed to this argument must either be `true` or `false`. If no value is provided, `true` will be used for the value.
### Values
Section titled “Values”
The input field argument `addLabels` accepts the following value configurations.
  * `addLabels`
  * `addLabels(value: true | false)`


### Allowed Input Fields
Section titled “Allowed Input Fields”
The input field argument `addLabels` can be used on the following input fields. 
  * `slider`
  * `progressBar`


### Examples
Section titled “Examples”
```

INPUT[slider(addLabels):bind_target]

```

```

INPUT[slider(addLabels(true)):bind_target]

```

 Previous Toggle   Next Allow Other 


================================================================================

## 75. /buttonactions/insertintonote

(/buttonactions/insertintonote/#_top)
# Insert Into Note
This action inserts plain text or a Templater template at a specified line number into the note of the button.
```

interfaceInsertIntoNoteButtonAction {
type:'insertIntoNote';
line:number; // the line number to insert the text at
value:string; // the text to insert or the path to the Templater template
templater?:boolean; // if true, the value is a path to a Templater template

```

If `templater` is `true`, the `value` field is treated as a path to a Templater template. If `templater` is `false` or not specified, the `value` field is treated as plain text.
### Example
Section titled “Example”
This button inserts the text “Hello, world!” at line 3 of the note.
```

```meta-bind-button
styleprimary
labelInsert Into Note
action:
type:insertIntoNote
line:3
value:"Hello, world!"
templater:false
```

```



================================================================================

## 76. /inputfieldarguments/allowother

(/inputfieldarguments/allowother/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Allow Other
Identifier | `allowOther`  
---|---  
Allows Multiple | `false`  
### Description
Section titled “Description”
The `allowOther` argument lets you set a custom value, which is not specified with the `option` argument, for suggester like input fields.
### Values
Section titled “Values”
The input field argument `allowOther` accepts the following value configurations.
  * `allowOther`
  * `allowOther(value: true | false)`


### Allowed Input Fields
Section titled “Allowed Input Fields”
The input field argument `allowOther` can be used on the following input fields. 
  * `suggester`
  * `listSuggester`
  * `inlineListSuggester`


### Examples
Section titled “Examples”
```

INPUT[suggester(
option(option 1),
option(option 2),
option(option 3),
allowOther
):bind_target]

```

 Previous Add Labels   Next Class 


================================================================================

## 77. /inputfieldarguments/class

(/inputfieldarguments/class/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Class
Identifier | `class`  
---|---  
Allows Multiple | `true`  
### Description
Section titled “Description”
The `class` argument lets you add one or multiple CSS classes to an input field. For more info on styling input fields, see the Styling guide.
### Values
Section titled “Values”
The input field argument `class` accepts the following value configurations.
  * `class(className: any)`
    * `className` is the name of the css class to add 


### Allowed Input Fields
Section titled “Allowed Input Fields”
The input field argument `class` can be used on all input fields. 
 Previous Allow Other   Next Default Value 


================================================================================

## 78. /buttonactions/input

(/buttonactions/input/#_top)
# Input
The input action inserts text at the current cursor position in the focused element.
```

interfaceInputButtonAction {
type:'input';
str:string; // the string to insert

```

### Example
Section titled “Example”
This button opens the command palette and inserts the string `help`. Resulting in the command palette being opened with `help` already typed in the search bar.
```

```meta-bind-button
styleprimary
labelHelp Commands
actions:
-typecommand
commandcommand-palette:open
-type:input
str:help
```

```



================================================================================

## 79. /buttonactions/createnote

(/buttonactions/createnote/#_top)
# Create Note
The _create note_ action creates a new empty note in the specified location.
```

interfaceCreateNoteButtonAction {
type:'createNote';
fileName:string; // the name of the new note
folderPath?:string; // the folder path where the note should be created, if not specified the note will be created in the root of the vault
openNote?:boolean; // if true, the note will be opened after creation
openIfAlreadyExists?:boolean; // whether to open the note if it already exists instead of creating a new one with an incremented name

```

When a note with the same name already exists in the specified location, the note will be created with a running number appended to the name. For example, if a note with the name `Note` already exists, the new note will be named `Note 1`.
### Example
Section titled “Example”
This button will create a new note named `New Note` in the `My Folder` folder. If a note with the same name already exists, the new note will be named `New Note 1`.
```

```meta-bind-button
styleprimary
labelCreate Note
action:
type:createNote
folderPath:"My Folder"
fileName:"New Note"
openNote:false
```

```



================================================================================

## 80. /buttonactions/open

(/buttonactions/open/#_top)
# Open
The open file action opens a file or URL.
```

interfaceOpenButtonAction {
type:'open';
link:string; // the file link ([[file]]) or URL (https://www.example.com) to open
newTab?:boolean; // whether to open the link in a new tab

```

### Example
Section titled “Example”
This button opens the Meta Bind Docs in your default browser.
```

```meta-bind-button
styleprimary
labelOpen Meta Bind Docs
action:
type:open
link:/
```

```



================================================================================

## 81. /inputfieldarguments/defaultvalue

(/inputfieldarguments/defaultvalue/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Default Value
Identifier | `defaultValue`  
---|---  
Allows Multiple | `false`  
### Description
Section titled “Description”
The `defaultValue` argument allows for the specification of a custom default value for the input field. A default value is displayed when the value of the bind target is `null` or invalid. Note that input fields only change the bound value when they are interacted with. This holds true for the `defaultValue` argument as well, meaning the default value will not be automatically written to the bind target. See also the `placeholder` argument.
### Values
Section titled “Values”
The input field argument `defaultValue` accepts the following value configurations.
  * `defaultValue(value: any)`


### Allowed Input Fields
Section titled “Allowed Input Fields”
The input field argument `defaultValue` can be used on all input fields. 
### Examples
Section titled “Examples”
```

INPUT[number(defaultValue(-1)):bind_target]

```

 Previous Class   Next Limit 


================================================================================

## 82. /buttonactions/replaceself

(/buttonactions/replaceself/#_top)
# Replace Self
This button action replaces the button with either plain text or a Templater template.
This only works with buttons in blocks, so this action will not work with inline buttons which are not inside a `meta-bind` block.
```

interfaceReplaceSelfButtonAction {
type:'replaceSelf';
replacement:string; // the string or the path to the Templater template to replace the button with
templater?:boolean; // if true, the replacement is a Templater template

```

### Example
Section titled “Example”
This button will replace itself with the text `i am no longer a button :(` when clicked.
```

```meta-bind-button
styleprimary
labelReplace Self
action:
type:"replaceSelf"
replacement:"i am no longer a button :("
```

```



================================================================================

## 83. /buttonactions/regexpreplaceinnote

(/buttonactions/regexpreplaceinnote/#_top)
# RegExp Replace In Note
This button action allows you to do a search and replace on the entire note where the button is in.
```

interfaceRegexpReplaceInNoteButtonAction {
type:'replaceInNote';
regexp:string; // the regular expression to search for
regexpFlags?:string; // the regexp flags for the regular expression, defaults to `g` if omitted
replacement:string; // the replacement text

```

You can use `$1`, `$2`, etc. in the replacement text to reference the matched groups in the regular expression.
### Example
Section titled “Example”
This example replaces every `TODO: ...` line with `TODO: ... - Done`.
```

```meta-bind-button
styleprimary
labelRexExp Replace In Note
action:
type:"regexpReplaceInNote"
regexp:"^(TODO: .*)$"
regexpFlags:"gm"
replacement"$1 - Done"
```

```



================================================================================

## 84. /buttonactions/runjavascript

(/buttonactions/runjavascript/#_top)
# Run JavaScript File
The run JavaScript file action runs a JavaScript file.
```

interfaceJSButtonAction {
type:'js';
file:string; // the path to the JavaScript file to run, relative to the vault root
args?:Record<string, unknown>; // optional arguments to pass to the script (available in the script as `context.args`)

```

The button configuration is available as a **read only** variable in the script as `context.buttonConfig`. Additional information about the button is available in the `context.buttonContext` object. See Button Context for more information. The args is passed to the script as `context.args`.
### Example
Section titled “Example”
```

```meta-bind-button
styleprimary
labelRun JavaScript File
action:
type:js
file:someScript.js
args:
greeting"Meta Bind User"
```

```

With the following `someScript.js` file in the vault root.
someScript.js```

console.log('Hello ${context.args.greeting}!');

```

You should see the string `Hello Meta Bind User!` printed to the console, when you click the button.


================================================================================

## 85. /buttonactions/templatercreatenote

(/buttonactions/templatercreatenote/#_top)
# Templater Create Note
The templater create note action creates a new note using a Templater template.
```

interfaceTemplaterCreateNoteButtonAction {
type:'templaterCreateNote';
templateFile:string; // the path to the template file, relative to the vault root
folderPath?:string; // the optional path to the folder to create the note in, relative to the vault root
fileName?:string; // the optional name of the file to create
openNote?:boolean; // whether to open the created note
openIfAlreadyExists?:boolean; // whether to open the note if it already exists instead of creating a new one with an incremented name

```

### Example
Section titled “Example”
This button creates a new note titled `New Lecture Note - RENAME ME` in the `Lectures` folder using the `Lecture Template` template from the `templates` folder.
```

```meta-bind-button
styleprimary
labelCreate Lecture Note
actions:
-type:templaterCreateNote
templateFile:"templates/Lecture Template.md"
folderPath:Lectures
fileName:"New Lecture Note - RENAME ME"
```

```



================================================================================

## 86. /buttonactions/updatemetadata

(/buttonactions/updatemetadata/#_top)
# Update Metadata
The update metadata action allows you to update a specific property specified via a Bind Target. This property can be any valid Bind Target such as the frontmatter of a file.
```

interfaceUpdateMetadataButtonAction {
type:'updateMetadata';
bindTarget:string; // the bind target of the property to update
evaluate:boolean; // whether to treat the value as a JavaScript expression
value:string; // the value to set the property to or the JavaScript expression to evaluate

```

If `evaluate` is set to `true`, the value is treated as a JavaScript expression and evaluated. The current value of the property is available in the expression as `x`.
Other properties can be reference using `getMetadata(bindTarget)` where `bindTarget` is a Bind Target string.
#### Example
Section titled “Example”
This button group allows you to increment, decrement, and reset a counter stored in the frontmatter of the current file.
```

```meta-bind-button
label"+1"
hiddentrue
id"count-increment"
styledefault
actions:
-type:updateMetadata
bindTarget:count
evaluate:true
value:"x + 1"
```
```meta-bind-button
label"-1"
hiddentrue
id"count-decrement"
styledefault
actions:
-type:updateMetadata
bindTarget:count
evaluate:true
value:"x - 1"
```
```meta-bind-button
label"Reset"
hiddentrue
id"count-reset"
styledefault
actions:
-type:updateMetadata
bindTarget:count
evaluate:false
value:0
```
`BUTTON[count-decrement, count-reset, count-increment]` `VIEW[{count}]`

```

This is a simple health tracker for e.g. a TTRPG.
```

---
health35
max_health50
damage5
---
```meta-bind-button
label"Deal"
styledestructive
hiddentrue
id"deal-damage"
actions:
-typeupdateMetadata
bindTargethealth
evaluatetrue
value"x - getMetadata('damage')"
```
```meta-bind-button
label"Reset"
styleprimary
hiddentrue
id"reset-health"
actions:
-typeupdateMetadata
bindTargethealth
evaluatetrue
value"getMetadata('max_health')"
```
Health: `VIEW[{health}][text]` `BUTTON[reset-health]`
Damage: `INPUT[number:damage]` `BUTTON[deal-damage]`

```



================================================================================

## 87. /buttonactions/inlinejs

(/buttonactions/inlinejs/#_top)
# Run Inline JavaScript
The inline JS action runs the code provided using the JS Engine plugin.
```

interfaceInlineJSButtonAction {
type:'inlineJS';
code:string; // the code to run

```

The button configuration is available as a **read only** variable in the script as `context.buttonConfig`. Additional information about the button is available in the `context.buttonContext` object. See Button Context for more information.
### Example
Section titled “Example”
This button will log `Hello World!` to the console.
```

```meta-bind-button
styleprimary
labelGreet the World
action:
type:inlineJS
code:"console.log('Hello World!');"
```

```



================================================================================

## 88. /buttonactions/runtemplaterfile

(/buttonactions/runtemplaterfile/#_top)
# Run Templater File
Executes all Templater templates within a single file.
```

interfaceRunTemplaterFileButtonAction {
type:'runTemplaterFile';
templateFile:string; // the path to the template file, relative to the vault root

```

### Examples
Section titled “Examples”
#### Banner Notice
Section titled “Banner Notice”
This will display a banner with the title of the file you are in.
##### Button
Section titled “Button”
```

```meta-bind-button
styleprimary
labelSay Filename
actions:
-type:runTemplaterFile
templateFile:"templates/Notice.md"
```

```

##### File (Notice.md)
Section titled “File (Notice.md)”
```

<%*
newNotice(tp.file.title);
%>

```



================================================================================

## 89. /buttonactions/sleep

(/buttonactions/sleep/#_top)
# Sleep
The sleep action waits for a specified amount of time.
```

interfaceSleepButtonAction {
type:'sleep';
ms:number; // the time to wait in milliseconds

```

### Example
Section titled “Example”
This button will open the command palette, wait for 1 second, and then type `help` into the search bar.
```

```meta-bind-button
styleprimary
labelSleep
actions:
-typecommand
commandcommand-palette:open
-type:sleep
ms:1000
-typeinput
strhelp
```

```



================================================================================

## 90. /inputfieldarguments/limit

(/inputfieldarguments/limit/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Limit
Identifier | `limit`  
---|---  
Allows Multiple | `false`  
### Description
Section titled “Description”
The `limit` argument allows you to limit the length of a value that can be entered in the `text`, `textArea`, and `list` input fields. The value passed to this argument must be a number.
### Values
Section titled “Values”
The input field argument `limit` accepts the following value configurations.
  * `limit(value: number)`
    * `value` is a character limit for text fields 


### Allowed Input Fields
Section titled “Allowed Input Fields”
The input field argument `limit` can be used on the following input fields. 
  * `text`
  * `textArea`
  * `list`
  * `inlineList`


### Examples
Section titled “Examples”
```

INPUT[text(limit(10)):bind_target]

```

 Previous Default Value   Next Max Value 


================================================================================

## 91. /inputfieldarguments/maxvalue

(/inputfieldarguments/maxvalue/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Max Value
Identifier | `maxValue`  
---|---  
Allows Multiple | `false`  
### Description
Section titled “Description”
The `maxValue` argument lets specify a maximum value for a `slider` or `progressBar` input. The value passed to this argument must be a number. See also the `minValue` argument.
### Values
Section titled “Values”
The input field argument `maxValue` accepts the following value configurations.
  * `maxValue(value: number)`
    * `value` is the maximally allowed value 


### Allowed Input Fields
Section titled “Allowed Input Fields”
The input field argument `maxValue` can be used on the following input fields. 
  * `slider`
  * `progressBar`


### Examples
Section titled “Examples”
```

INPUT[slider(maxValue(10)):bind_target]

```

```

INPUT[slider(minValue(-10),maxValue(10)):bind_target]

```

 Previous Limit   Next Min Value 


================================================================================

## 92. /buttonactions/replaceinnote

(/buttonactions/replaceinnote/#_top)
# Replace In Note
This button action allows you to replace a specified line range in the current note with new text or a Templater template.
```

interfaceReplaceInNoteButtonAction {
type:'replaceInNote';
fromLine:number; // the line to start replacing from (1-based index)
toLine:number; // the line to stop replacing at (1-based index)
replacement:string; // the replacement text or path to replacement Templater template
templater?:boolean; // whether the replacement is a Templater template

```

If `templater` is `true`, the `replacement` field is treated as a path to a Templater template. If `templater` is `false` or not specified, the `replacement` field is treated as plain text.
### Example
Section titled “Example”
This example replaces lines 3-5 in the current note with the text following text.
```

some
text
wow

```

```

```meta-bind-button
styleprimary
labelReplace in Note
action:
type:"replaceInNote"
fromLine:3
toLine:5
replacement:"some\ntext\nwow"
```

```



================================================================================

## 93. /inputfieldarguments/minvalue

(/inputfieldarguments/minvalue/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Min Value
Identifier | `minValue`  
---|---  
Allows Multiple | `false`  
### Description
Section titled “Description”
The `minValue` argument lets specify a minimum value for a `slider` or `progressBar` input. The value passed to this argument must be a number. See also the `maxValue` argument.
### Values
Section titled “Values”
The input field argument `minValue` accepts the following value configurations.
  * `minValue(value: number)`
    * `value` is the minimally allowed value 


### Allowed Input Fields
Section titled “Allowed Input Fields”
The input field argument `minValue` can be used on the following input fields. 
  * `slider`
  * `progressBar`


### Examples
Section titled “Examples”
```

INPUT[slider(minValue(-10)):bind_target]

```

```

INPUT[slider(minValue(-10),maxValue(10)):bind_target]

```

 Previous Max Value   Next Off Value 


================================================================================

## 94. /inputfieldarguments/offvalue

(/inputfieldarguments/offvalue/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Off Value
Identifier | `offValue`  
---|---  
Allows Multiple | `false`  
### Description
Section titled “Description”
The `offValue` argument lets specify a custom off value for the `toggle` input. See also the `onValue` argument.
### Values
Section titled “Values”
The input field argument `offValue` accepts the following value configurations.
  * `offValue(value: any)`
    * `value` is the value for the off state 


### Allowed Input Fields
Section titled “Allowed Input Fields”
The input field argument `offValue` can be used on the following input fields. 
  * `toggle`


### Examples
Section titled “Examples”
```

INPUT[toggle(onValue(on),offValue(off)):bind_target]

```

 Previous Min Value   Next On Value 


================================================================================

## 95. /inputfieldarguments/option

(/inputfieldarguments/option/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Option
Identifier | `option`  
---|---  
Allows Multiple | `true`  
### Description
Section titled “Description”
The `option` argument lets you add a single option. If you supply only one value (`value`), the `value` will be displayed in the input field and written to the front-matter. If you supply two values (`value`, `name`), the `value` will be written to the front-matter and the `name` will be displayed in the input field. Note that the plugin can not differentiate between two options with the same `value`, even if the `name` is different.
Some specific values are interpreted as types other than strings.
  * `true` and `false` are interpreted as booleans
  * `null` is interpreted as a null value
  * numbers are interpreted as numbers


### Values
Section titled “Values”
The input field argument `option` accepts the following value configurations.
  * `option(value: any)`
    * `value` is the value and display name of the option 
  * `option(value: any, name: any)`
    * `value` is the value of the option 
    * `name` is the display name of the option 


### Allowed Input Fields
Section titled “Allowed Input Fields”
The input field argument `option` can be used on the following input fields. 
  * `select`
  * `multiSelect`
  * `suggester`
  * `imageSuggester`
  * `inlineSelect`
  * `listSuggester`
  * `inlineListSuggester`
  * `imageListSuggester`


### Examples
Section titled “Examples”
```

INPUT[select(option(banana),option(apple)):bind_target]

```

```

INPUT[select(
option(1, 1 Star),
option(2, 2 Stars),
option(3, 3 Stars),
option(4, 4 Stars),
option(5, 5 Stars)
):bind_target]

```

 Previous On Value   Next Option Query 


================================================================================

## 96. /inputfieldarguments/showcase

(/inputfieldarguments/showcase/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Showcase
Identifier | `showcase`  
---|---  
Allows Multiple | `false`  
### Description
Section titled “Description”
The `showcase` argument creates a card around the input field, showing the input field declaration at the bottom. This is used in the Example Vault.
### Values
Section titled “Values”
The input field argument `showcase` accepts the following value configurations.
  * `showcase`
  * `showcase(value: true | false)`


### Allowed Input Fields
Section titled “Allowed Input Fields”
The input field argument `showcase` can be used on all input fields. 
### Examples
Section titled “Examples”
```

INPUT[toggle(showcase):bind_target]

```

 Previous Placeholder   Next Step Size Value 


================================================================================

## 97. /inputfieldarguments/onvalue

(/inputfieldarguments/onvalue/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# On Value
Identifier | `onValue`  
---|---  
Allows Multiple | `false`  
### Description
Section titled “Description”
The `onValue` argument lets specify a custom on value for the `toggle` input. See also the `offValue` argument.
### Values
Section titled “Values”
The input field argument `onValue` accepts the following value configurations.
  * `onValue(value: any)`
    * `value` is the value for the off state 


### Allowed Input Fields
Section titled “Allowed Input Fields”
The input field argument `onValue` can be used on the following input fields. 
  * `toggle`


### Examples
Section titled “Examples”
```

INPUT[toggle(onValue(on),offValue(off)):bind_target]

```

 Previous Off Value   Next Option 


================================================================================

## 98. /inputfieldarguments/optionquery

(/inputfieldarguments/optionquery/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Option Query
Identifier | `optionQuery`  
---|---  
Allows Multiple | `true`  
### Description
Section titled “Description”
The `optionQuery` argument lets you add multiple options to suggesters based on a Dataview data source. Dataview queries are **not** supported.
Note that the `imageSuggester` only supports providing a `"path/to/folder"`, whereas other suggester variations fully support any dataview data source.
### Values
Section titled “Values”
The input field argument `optionQuery` accepts the following value configurations.
  * `optionQuery(value: any)`
    * `value` is the query for options 


### Allowed Input Fields
Section titled “Allowed Input Fields”
The input field argument `optionQuery` can be used on the following input fields. 
  * `suggester`
  * `imageSuggester`
  * `listSuggester`
  * `inlineListSuggester`
  * `imageListSuggester`


### Examples
Section titled “Examples”
```

INPUT[suggester(optionQuery(#tag)):bind_target

```

```

INPUT[suggester(optionQuery("path/to/folder")):bind_target]

```

```

INPUT[imageSuggester(optionQuery("path/to/folder")):bind_target]

```

 Previous Option   Next Placeholder 


================================================================================

## 99. /inputfieldarguments/placeholder

(/inputfieldarguments/placeholder/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Placeholder
Identifier | `placeholder`  
---|---  
Allows Multiple | `false`  
### Description
Section titled “Description”
The `placeholder` argument allows for the specification of a placeholder value, which will be displayed when the input field has no data or is empty. This is very similar to the HTML `placeholder` attribute. See also the `defaultValue` argument.
### Values
Section titled “Values”
The input field argument `placeholder` accepts the following value configurations.
  * `placeholder(value: any)`


### Allowed Input Fields
Section titled “Allowed Input Fields”
The input field argument `placeholder` can be used on the following input fields. 
  * `text`
  * `textArea`
  * `number`
  * `list`
  * `inlineList`


### Examples
Section titled “Examples”
```

INPUT[text(placeholder(Appointment Location)):bind_target]

```

 Previous Option Query   Next Showcase 


================================================================================

## 100. /inputfieldarguments/stepsize

(/inputfieldarguments/stepsize/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Step Size Value
Identifier | `stepSize`  
---|---  
Allows Multiple | `false`  
### Description
Section titled “Description”
The `stepSize` argument lets specify a step size value for a `slider` or `progressBar` input. The value passed to this argument must be a number.
### Values
Section titled “Values”
The input field argument `stepSize` accepts the following value configurations.
  * `stepSize(value: number)`
    * `value` is the step size for sliders 


### Allowed Input Fields
Section titled “Allowed Input Fields”
The input field argument `stepSize` can be used on the following input fields. 
  * `slider`
  * `progressBar`


### Examples
Section titled “Examples”
```

INPUT[slider(stepSize(2)):bind_target]

```

```

INPUT[slider(stepSize(0.1)):bind_target]

```

 Previous Showcase   Next Title 


================================================================================

## 101. /inputfields/datetime

(/inputfields/datetime/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Date Time
Identifier | `dateTime`  
---|---  
Allowed in Code Block | `true`  
Allowed Inline | `true`  
### Description
Section titled “Description”
A _date time_ input combines the `date` and `time` input fields. The date format is dependent on your Obsidian date format setting which is dependent on your system settings.
### Allowed Arguments
Section titled “Allowed Arguments”
The following input field arguments can be used on the `dateTime` input field.
  * `class`
  * `defaultValue`
  * `showcase`
  * `title`


 Previous Date Picker   Next Editor 


================================================================================

## 102. /inputfields/datepicker

(/inputfields/datepicker/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Date Picker
Identifier | `datePicker`  
---|---  
Allowed in Code Block | `true`  
Allowed Inline | `true`  
### Description
Section titled “Description”
A _date picker_ input field is a simple data picker that treats `null` as no set date. The date format can be changed in the plugin settings.
### Allowed Arguments
Section titled “Allowed Arguments”
The following input field arguments can be used on the `datePicker` input field.
  * `class`
  * `defaultValue`
  * `showcase`
  * `title`


 Previous Date   Next Date Time 


================================================================================

## 103. /inputfieldarguments/uselinks

(/inputfieldarguments/uselinks/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Use Links
Identifier | `useLinks`  
---|---  
Allows Multiple | `false`  
### Description
Section titled “Description”
The `useLinks` argument lets you change how certain input fields handle links.
There are three possible values for this argument:
  * `true` - Will use links of the form `[[someFolder/Note.md|Note]]`.
  * `partial` - Will use links of the form `[[Note]]`.
  * `false` - Will **not** use links. The note name will be used instead.


If no value is provided, `true` will be used.
### Values
Section titled “Values”
The input field argument `useLinks` accepts the following value configurations.
  * `useLinks`
  * `useLinks(value: true | partial | false)`


### Allowed Input Fields
Section titled “Allowed Input Fields”
The input field argument `useLinks` can be used on the following input fields. 
  * `suggester`
  * `listSuggester`
  * `inlineListSuggester`


### Examples
Section titled “Examples”
```

---
useLinksTrue:"[[someFolder/Note.md|Note]]"
useLinksPartial:"[[Note]]"
useLinksFalse:"Note"
---
```meta-bind
INPUT[suggester(optionQuery("someFolder")):useLinksTrue]
```
```meta-bind
INPUT[suggester(optionQuery("someFolder"),useLinks(partial)):useLinksPartial]
```
```meta-bind
INPUT[suggester(optionQuery("someFolder"),useLinks(false)):useLinksFalse]
```

```

 Previous Title   Next Image 


================================================================================

## 104. /inputfields/inlineselect

(/inputfields/inlineselect/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Inline Select
Identifier | `inlineSelect`  
---|---  
Allowed in Code Block | `true`  
Allowed Inline | `true`  
### Description
Section titled “Description”
An _inline select_ input field functions like a dropdown menu, and allows you to select a certain value from a list of options. Options can be added using the `option` argument.
### Allowed Arguments
Section titled “Allowed Arguments”
The following input field arguments can be used on the `inlineSelect` input field.
  * `class`
  * `defaultValue`
  * `option`
  * `showcase`
  * `title`


 Previous Inline List Suggester   Next List 


================================================================================

## 105. /inputfields/inlinelistsuggester

(/inputfields/inlinelistsuggester/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Inline List Suggester
Identifier | `inlineListSuggester`  
---|---  
Allowed in Code Block | `true`  
Allowed Inline | `true`  
### Description
Section titled “Description”
A _inlineListSuggester_ input field allows you to add and remove elements to an inline displayed list.
Clicking the plus button at the end of the list will open a suggester modal similar to the `listSuggester` with which you can add a new element to the list. Elements can be moved, edited, and deleted from the list by right-clicking on the element (or long-pressing on mobile) and selecting the appropriate action.
### Allowed Arguments
Section titled “Allowed Arguments”
The following input field arguments can be used on the `inlineListSuggester` input field.
  * `class`
  * `defaultValue`
  * `option`
  * `optionQuery`
  * `showcase`
  * `title`
  * `useLinks`
  * `allowOther`


 Previous Inline List   Next Inline Select 


================================================================================

## 106. /inputfields/inlinelist

(/inputfields/inlinelist/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Inline List
Identifier | `inlineList`  
---|---  
Allowed in Code Block | `true`  
Allowed Inline | `true`  
### Description
Section titled “Description”
A _inlineList_ input field allows you to add and remove elements to an inline displayed list.
Clicking the plus button at the end of the list will open a text input modal with which you can add a new element to the list. Elements can be moved, edited, and deleted from the list by right-clicking on the element (or long-pressing on mobile) and selecting the appropriate action.
### Allowed Arguments
Section titled “Allowed Arguments”
The following input field arguments can be used on the `inlineList` input field.
  * `class`
  * `defaultValue`
  * `placeholder`
  * `showcase`
  * `title`
  * `limit`


 Previous Image Suggester   Next Inline List Suggester 


================================================================================

## 107. /inputfields/editor

(/inputfields/editor/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Editor
Identifier | `editor`  
---|---  
Allowed in Code Block | `true`  
Allowed Inline | `false`  
### Description
Section titled “Description”
An _editor_ input field is similar to a `textArea`, but with full markdown support.
### Allowed Arguments
Section titled “Allowed Arguments”
The following input field arguments can be used on the `editor` input field.
  * `class`
  * `defaultValue`
  * `showcase`
  * `title`


 Previous Date Time   Next Image List Suggester 


================================================================================

## 108. /inputfields/date

(/inputfields/date/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Date
Identifier | `date`  
---|---  
Allowed in Code Block | `true`  
Allowed Inline | `true`  
### Description
Section titled “Description”
A _date_ input field is the Obsidian native date input. The date format is dependent on your Obsidian date format setting which is dependent on your system settings.
### Allowed Arguments
Section titled “Allowed Arguments”
The following input field arguments can be used on the `date` input field.
  * `class`
  * `defaultValue`
  * `showcase`
  * `title`


 Previous Customizing MathJS   Next Date Picker 


================================================================================

## 109. /inputfieldarguments/title

(/inputfieldarguments/title/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Title
Identifier | `title`  
---|---  
Allows Multiple | `false`  
### Description
Section titled “Description”
The `title` argument lets you add a descriptive title to an input field.
### Values
Section titled “Values”
The input field argument `title` accepts the following value configurations.
  * `title(value: any)`


### Allowed Input Fields
Section titled “Allowed Input Fields”
The input field argument `title` can be used on all input fields. 
### Examples
Section titled “Examples”
```

INPUT[toggle(title(this is a cool title)):bind_target]

```

 Previous Step Size Value   Next Use Links 


================================================================================

## 110. /inputfields/list

(/inputfields/list/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# List
Identifier | `list`  
---|---  
Allowed in Code Block | `true`  
Allowed Inline | `false`  
### Description
Section titled “Description”
A _list_ input field allows you to add and remove elements to a list.
Elements can be moved, edited, and deleted from the list by right-clicking on the element (or long-pressing on mobile) and selecting the appropriate action.
### Allowed Arguments
Section titled “Allowed Arguments”
The following input field arguments can be used on the `list` input field.
  * `class`
  * `defaultValue`
  * `placeholder`
  * `showcase`
  * `title`
  * `limit`
  * `multiLine`


 Previous Inline Select   Next List Suggester 


================================================================================

## 111. /inputfields/listsuggester

(/inputfields/listsuggester/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# List Suggester
Identifier | `listSuggester`  
---|---  
Allowed in Code Block | `true`  
Allowed Inline | `false`  
### Description
Section titled “Description”
A _list suggester_ input field allows you to add and remove elements to a list, using a `suggester` input.
Elements can be moved and deleted from the list by right-clicking on the element (or long-pressing on mobile) and selecting the appropriate action.
### Allowed Arguments
Section titled “Allowed Arguments”
The following input field arguments can be used on the `listSuggester` input field.
  * `class`
  * `defaultValue`
  * `option`
  * `optionQuery`
  * `showcase`
  * `title`
  * `useLinks`
  * `allowOther`


 Previous List   Next Multi Select 


================================================================================

## 112. /inputfields/imagesuggester

(/inputfields/imagesuggester/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Image Suggester
Identifier | `imageSuggester`  
---|---  
Allowed in Code Block | `true`  
Allowed Inline | `true`  
### Description
Section titled “Description”
An _image suggester_ input field allows for a selection from a gallery of images.
The image can be changed by clicking the pencil icon on the right side of the input field.
### Allowed Arguments
Section titled “Allowed Arguments”
The following input field arguments can be used on the `imageSuggester` input field.
  * `class`
  * `defaultValue`
  * `option`
  * `optionQuery`
  * `showcase`
  * `title`


 Previous Image List Suggester   Next Inline List 


================================================================================

## 113. /inputfields/imagelistsuggester

(/inputfields/imagelistsuggester/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Image List Suggester
Identifier | `imageListSuggester`  
---|---  
Allowed in Code Block | `true`  
Allowed Inline | `false`  
### Description
Section titled “Description”
An _image list suggester_ input field allows for multiple selections from a gallery of images.
Images can be moved and deleted from the list by right-clicking on the image (or long-pressing on mobile) and selecting the appropriate action.
### Allowed Arguments
Section titled “Allowed Arguments”
The following input field arguments can be used on the `imageListSuggester` input field.
  * `class`
  * `defaultValue`
  * `option`
  * `optionQuery`
  * `showcase`
  * `title`


 Previous Editor   Next Image Suggester 


================================================================================

## 114. /inputfields/multiselect

(/inputfields/multiselect/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Multi Select
Identifier | `multiSelect`  
---|---  
Allowed in Code Block | `true`  
Allowed Inline | `false`  
### Description
Section titled “Description”
A _multi select_ input field allows you to select multiple values from a list of options. Options can be added using the `option` argument.
### Allowed Arguments
Section titled “Allowed Arguments”
The following input field arguments can be used on the `multiSelect` input field.
  * `class`
  * `defaultValue`
  * `option`
  * `showcase`
  * `title`


 Previous List Suggester   Next Number 


================================================================================

## 115. /inputfields/select

(/inputfields/select/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Select
Identifier | `select`  
---|---  
Allowed in Code Block | `true`  
Allowed Inline | `false`  
### Description
Section titled “Description”
A _select_ input field allows you to select a certain value from a list of options. Options can be added using the `option` argument.
### Allowed Arguments
Section titled “Allowed Arguments”
The following input field arguments can be used on the `select` input field.
  * `class`
  * `defaultValue`
  * `option`
  * `showcase`
  * `title`


 Previous Progress Bar   Next Slider 


================================================================================

## 116. /inputfields/slider

(/inputfields/slider/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Slider
Identifier | `slider`  
---|---  
Allowed in Code Block | `true`  
Allowed Inline | `true`  
### Description
Section titled “Description”
A _slider_ input field is a slider that can move within a certain value range. The range can be controlled with the `minValue` and `maxValue` arguments. Optionally, labels can be added using the `addLabels` argument.
### Allowed Arguments
Section titled “Allowed Arguments”
The following input field arguments can be used on the `slider` input field.
  * `addLabels`
  * `class`
  * `defaultValue`
  * `maxValue`
  * `minValue`
  * `stepSize`
  * `showcase`
  * `title`


 Previous Select   Next Suggester 


================================================================================

## 117. /inputfields/progressbar

(/inputfields/progressbar/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Progress Bar
Identifier | `progressBar`  
---|---  
Allowed in Code Block | `true`  
Allowed Inline | `false`  
### Description
Section titled “Description”
A _progress bar_ input field takes the full width of a note and can move within a certain value range. The range can be controlled with the `minValue` and `maxValue` arguments. Optionally, labels can be added using the `addLabels` argument.
### Allowed Arguments
Section titled “Allowed Arguments”
The following input field arguments can be used on the `progressBar` input field.
  * `addLabels`
  * `class`
  * `defaultValue`
  * `maxValue`
  * `minValue`
  * `stepSize`
  * `showcase`
  * `title`


 Previous Number   Next Select 


================================================================================

## 118. /inputfields/number

(/inputfields/number/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Number
Identifier | `number`  
---|---  
Allowed in Code Block | `true`  
Allowed Inline | `true`  
### Description
Section titled “Description”
A _number_ input field is a `text`-like input field that only accepts numbers.
### Allowed Arguments
Section titled “Allowed Arguments”
The following input field arguments can be used on the `number` input field.
  * `class`
  * `defaultValue`
  * `placeholder`
  * `showcase`
  * `title`


 Previous Multi Select   Next Progress Bar 


================================================================================

## 119. /inputfields/suggester

(/inputfields/suggester/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Suggester
Identifier | `suggester`  
---|---  
Allowed in Code Block | `true`  
Allowed Inline | `true`  
### Description
Section titled “Description”
A _suggester_ input fields allows selection from a fuzzy search modal.
### Allowed Arguments
Section titled “Allowed Arguments”
The following input field arguments can be used on the `suggester` input field.
  * `class`
  * `defaultValue`
  * `option`
  * `optionQuery`
  * `showcase`
  * `title`
  * `useLinks`
  * `allowOther`


 Previous Slider   Next Text 


================================================================================

## 120. /inputfields/textarea

(/inputfields/textarea/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Text Area
Identifier | `textArea`  
---|---  
Allowed in Code Block | `true`  
Allowed Inline | `true`  
### Description
Section titled “Description”
A _text area_ input field is a simple text area input field. Markdown is _not_ supported.
### Allowed Arguments
Section titled “Allowed Arguments”
The following input field arguments can be used on the `textArea` input field.
  * `class`
  * `defaultValue`
  * `placeholder`
  * `showcase`
  * `title`
  * `limit`


 Previous Text   Next Time 


================================================================================

## 121. /inputfields/text

(/inputfields/text/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Text
Identifier | `text`  
---|---  
Allowed in Code Block | `true`  
Allowed Inline | `true`  
### Description
Section titled “Description”
A _text_ input field is simple inline text input field. Markdown is _not_ supported.
### Allowed Arguments
Section titled “Allowed Arguments”
The following input field arguments can be used on the `text` input field.
  * `class`
  * `defaultValue`
  * `placeholder`
  * `showcase`
  * `title`
  * `limit`


 Previous Suggester   Next Text Area 


================================================================================

## 122. /inputfields/toggle

(/inputfields/toggle/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Toggle
Identifier | `toggle`  
---|---  
Allowed in Code Block | `true`  
Allowed Inline | `true`  
### Description
Section titled “Description”
A _toggle_ input field acts like a switch that can be toggled between `true` and `false`.
### Allowed Arguments
Section titled “Allowed Arguments”
The following input field arguments can be used on the `toggle` input field.
  * `class`
  * `defaultValue`
  * `offValue`
  * `onValue`
  * `showcase`
  * `title`


### Examples
Section titled “Examples”
A simple toggle that toggles the completed status of a note.
```

INPUT[toggle:completed]

```

A toggle that toggles between `in progress` and `done`.
```

INPUT[toggle(offValue(in progress),onValue(done)):status]

```

 Previous Time   Next Add Labels 


================================================================================

## 123. /inputfields/time

(/inputfields/time/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Time
Identifier | `time`  
---|---  
Allowed in Code Block | `true`  
Allowed Inline | `true`  
### Description
Section titled “Description”
A _time_ input field is the Obsidian native time input. The date format is dependent on your Obsidian date format setting which is dependent on your system settings.
### Allowed Arguments
Section titled “Allowed Arguments”
The following input field arguments can be used on the `time` input field.
  * `class`
  * `defaultValue`
  * `showcase`
  * `title`


 Previous Text Area   Next Toggle 


================================================================================

## 124. /viewfieldarguments/hidden

(/viewfieldarguments/hidden/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Hidden
Identifier | `hidden`  
---|---  
Allows Multiple | `false`  
### Description
Section titled “Description”
The `hidden` argument allows a view field to be hidden and not rendered. This can be useful if you want the view field to compute an intermediate value and write that value to the frontmatter. If no value is provided, `true` will be used for the value.
### Values
Section titled “Values”
The view field argument `hidden` accepts the following value configurations.
  * `hidden`
  * `hidden(value: true | false)`


### Allowed Input Fields
Section titled “Allowed Input Fields”
The view field argument `hidden` can be used on all view fields. 
### Examples
Section titled “Examples”
This view field calculates `a * b` and write it to `c`, but it is not visible in your note.
```

VIEW[{a} * {b}][math(hidden):c]

```

 Previous Class   Next Render Markdown 


================================================================================

## 125. /viewfieldarguments/class

(/viewfieldarguments/class/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Class
Identifier | `class`  
---|---  
Allows Multiple | `true`  
### Description
Section titled “Description”
The `class` argument lets you add one or multiple CSS classes to a view field.
### Values
Section titled “Values”
The view field argument `class` accepts the following value configurations.
  * `class(className: any)`
    * `className` is the name of the css class to add 


### Allowed Input Fields
Section titled “Allowed Input Fields”
The view field argument `class` can be used on all view fields. 
### Examples
Section titled “Examples”
This view field will display red text, as it has Obsidian’s `mod-warning` CSS class.
```

VIEW[{a} * {b}][math(class(mod-warning))]

```

 Previous Text   Next Hidden 


================================================================================

## 126. /viewfieldarguments/rendermarkdown

(/viewfieldarguments/rendermarkdown/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Render Markdown
Identifier | `renderMarkdown`  
---|---  
Allows Multiple | `false`  
### Description
Section titled “Description”
The `renderMarkdown` argument allows a view field to render its content as markdown.
### Values
Section titled “Values”
The view field argument `renderMarkdown` accepts the following value configurations.
  * `renderMarkdown`
  * `renderMarkdown(value: true | false)`


### Allowed Input Fields
Section titled “Allowed Input Fields”
The view field argument `renderMarkdown` can be used on the following view fields. 
  * `text`


### Examples
Section titled “Examples”
This will render the text stored in the `someText` frontmatter property as markdown.
```

VIEW[**{someText}**][text(renderMarkdown)]

```

 Previous Hidden   Next Command 


================================================================================

## 127. /viewfields/image

(/viewfields/image/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Image
Identifier | `image`  
---|---  
### Description
Section titled “Description”
An _image_ view field only accepts a single bind target as it’s content and will automatically display the image if the value is an image path. The following property types are supported:
  * a wiki-link to an image (e.g. `[[link/to/image]]`)
  * a markdown link to an image (e.g. `link`)
  * a bare path to an image (e.g. `link/to/image`)
  * a list of the above (e.g. `[[link/to/image1]], link, link/to/image3`)


### Allowed Arguments
Section titled “Allowed Arguments”
The following view field arguments can be used on the `image` view field.
  * `hidden`
  * `class`


### Examples
Section titled “Examples”
```

VIEW[{property}][image]

```

 Previous Use Links   Next Link 


================================================================================

## 128. /viewfields/text

(/viewfields/text/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Text
Identifier | `text`  
---|---  
### Description
Section titled “Description”
A text view field displays its content as plain text.
Using the `renderMarkdown` argument, the content can be rendered as markdown.
### Allowed Arguments
Section titled “Allowed Arguments”
The following view field arguments can be used on the `text` view field.
  * `renderMarkdown`
  * `hidden`
  * `class`


### Examples
Section titled “Examples”
```

VIEW[Movie Title:{moveTitle}][text]

```

 Previous Math   Next Class 


================================================================================

## 129. /viewfields/math

(/viewfields/math/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Math
Identifier | `math`  
---|---  
### Description
Section titled “Description”
A math view field performs calculations with mathjs expressions. Math view fields are the default view field, meaning that if you don’t specify a view field type, it is going to default to this.
### Allowed Arguments
Section titled “Allowed Arguments”
The following view field arguments can be used on the `math` view field.
  * `hidden`
  * `class`


### Examples
Section titled “Examples”
```

VIEW[{a} * {b}]

```

 Previous Link   Next Text 


================================================================================

## 130. /viewfields/link

(/viewfields/link/#_top)

Search ` `Ctrl``K` `
Cancel 
Clear




# Link
Identifier | `link`  
---|---  
### Description
Section titled “Description”
A _link_ view field only accepts a single bind target as it’s content and will automatically link to the targets value. The following property types are supported:
  * a wiki-link to a note (e.g. `[[note]]`)
  * a markdown link (e.g. `link`)
  * a string will get turned into a wiki-link (e.g. `note` -> `[[note]]`)
  * a URL will get turned into a markdown link (e.g. `https://example.com` -> `https://example.com`)
  * a list of the above (e.g. `[[note]], link, note2`)


### Allowed Arguments
Section titled “Allowed Arguments”
The following view field arguments can be used on the `link` view field.
  * `hidden`
  * `class`


### Examples
Section titled “Examples”
```

VIEW[{property}][link]

```

 Previous Image   Next Math 


================================================================================

