# Documentação Completa - www_moritzjung_dev

**URL Original**: https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/
**Data**: 28/05/2025 22:33:51
**Estratégia**: BFS
**Extraído com**: Crawl4AI - Madrev Edition

---

## 1. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/

Skip to content
# JS Engine Docs
JS Engine is a plugin for Obsidian, that allows you to easily run JavaScript from within your notes.
## Getting Started
First you will need to install the plugin from the Community Plugins tab in Obsidian’s settings. You can find various guides on how to use the plugin under the Guides section in the sidebar.
If you are looking for examples, you can explore the example vault which I use for testing.
## Bugs, Errors or Unexpected Behavior?
Please open a bug report on the plugins GitHub repository.
## Have an Idea for a new Feature?
Feature requests and contributions are always welcome. If you have an idea, feel free to open a feature request under the issues tab on GitHub or even create a pull request.
## Check out my Other Work
Check out my website.
Here is a list of my Obsidian related projects.
  * Meta Bind Plugin
  * JS Engine Plugin (You are here)
  * Media DB Plugin
  * Lemons Theme
  * Obsidian Stats
  * Obsidian Collection




================================================================================

## 2. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/codeblockelement

Skip to content
# CodeBlockElement
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:360
Represents a markdown code block.
## Extends
  * `AbstractMarkdownElementContainer`


## Constructors
### new CodeBlockElement()
> **new CodeBlockElement**(`apiInstance`, `language`, `content`): `CodeBlockElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:363
#### Parameters
Parameter | Type  
---|---  
`apiInstance` |   
`language` |  `string`  
`content` |  `string`  
#### Returns
`CodeBlockElement`
#### Overrides
`AbstractMarkdownElementContainer.constructor`
## Properties
### apiInstance
> `readonly` **apiInstance** : `API`
Defined in: jsEngine/api/markdown/AbstractMarkdownElement.ts:9
#### Inherited from
`AbstractMarkdownElementContainer.apiInstance`
### language
> **language** : `string`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:361
### markdownElements
> **markdownElements** : `AbstractMarkdownElement`[]
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:12
#### Inherited from
`AbstractMarkdownElementContainer.markdownElements`
## Methods
### addBoldText()
> **addBoldText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:53
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addBoldText`
### addCode()
> **addCode**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:85
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addCode`
### addCursiveText()
> **addCursiveText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:61
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addCursiveText`
### addElement()
> **addElement**(`element`): `void`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:35
Adds a child element to the container.
#### Parameters
Parameter | Type | Description  
---|---|---  
`element` |  `AbstractMarkdownElement`  
#### Returns
`void`
#### Throws
Error if the element is not allowed in the container.
#### Inherited from
`AbstractMarkdownElementContainer.addElement`
### addHighlightedText()
> **addHighlightedText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:77
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addHighlightedText`
### addText()
> **addText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:45
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addText`
### addUnderlinedText()
> **addUnderlinedText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:69
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addUnderlinedText`
### createBlockQuote()
> **createBlockQuote**(): `BlockQuoteElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:109
#### Returns
`BlockQuoteElement`
#### Inherited from
`AbstractMarkdownElementContainer.createBlockQuote`
### createCallout()
> **createCallout**(`title`, `type`, `args`): `CalloutElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:115
#### Parameters
Parameter | Type | Default value  
---|---|---  
`title` |  `string` |  `undefined`  
`type` |  `string` |  `undefined`  
`args` |  `string` |  `''`  
#### Returns
`CalloutElement`
#### Inherited from
`AbstractMarkdownElementContainer.createCallout`
### createCodeBlock()
> **createCodeBlock**(`language`, `content`): `CodeBlockElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:131
#### Parameters
Parameter | Type  
---|---  
`language` |  `string`  
`content` |  `string`  
#### Returns
`CodeBlockElement`
#### Inherited from
`AbstractMarkdownElementContainer.createCodeBlock`
### createCollapsibleCallout()
> **createCollapsibleCallout**(`title`, `type`, `args`, `collapsed`): `CalloutElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:123
#### Parameters
Parameter | Type | Default value  
---|---|---  
`title` |  `string` |  `undefined`  
`type` |  `string` |  `undefined`  
`args` |  `string` |  `''`  
`collapsed` |  `boolean` |  `false`  
#### Returns
`CalloutElement`
#### Inherited from
`AbstractMarkdownElementContainer.createCollapsibleCallout`
### createHeading()
> **createHeading**(`level`, `content`): `HeadingElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:101
#### Parameters
Parameter | Type  
---|---  
`level` |  `number`  
`content` |  `string`  
#### Returns
`HeadingElement`
#### Inherited from
`AbstractMarkdownElementContainer.createHeading`
### createList()
> **createList**(`ordered`): `ListElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:147
#### Parameters
Parameter | Type | Default value  
---|---|---  
`ordered` |  `boolean` |  `false`  
#### Returns
`ListElement`
#### Inherited from
`AbstractMarkdownElementContainer.createList`
### createOrderedList()
> **createOrderedList**(): `ListElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:155
#### Returns
`ListElement`
#### Inherited from
`AbstractMarkdownElementContainer.createOrderedList`
### createParagraph()
> **createParagraph**(`content`): `ParagraphElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:93
#### Parameters
Parameter | Type  
---|---  
`content` |  `string`  
#### Returns
`ParagraphElement`
#### Inherited from
`AbstractMarkdownElementContainer.createParagraph`
### createTable()
> **createTable**(`header`, `body`): `TableElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:139
#### Parameters
Parameter | Type  
---|---  
`header` |  `string`[]  
`body` |  `TableElementType`[][]  
#### Returns
`TableElement`
#### Inherited from
`AbstractMarkdownElementContainer.createTable`
### toMarkdown()
> **toMarkdown**(): `MarkdownString`
Defined in: jsEngine/api/markdown/AbstractMarkdownElement.ts:28
Converts the element to a MarkdownString.
#### Returns
`MarkdownString`
#### Inherited from
`AbstractMarkdownElementContainer.toMarkdown`
### toString()
> **toString**(): `string`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:370
Converts the element to a string.
#### Returns
`string`
#### Overrides
`AbstractMarkdownElementContainer.toString`


================================================================================

## 3. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/calloutelement

Skip to content
# CalloutElement
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:395
Represents a markdown callout.
## Extends
  * `AbstractMarkdownElementContainer`


## Constructors
### new CalloutElement()
> **new CalloutElement**(`apiInstance`, `title`, `type`, `args`, `collapsible`, `collapsed`): `CalloutElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:402
#### Parameters
Parameter | Type | Default value  
---|---|---  
`apiInstance` |  |  `undefined`  
`title` |  `string` |  `undefined`  
`type` |  `string` |  `undefined`  
`args` |  `string` |  `undefined`  
`collapsible` |  `boolean` |  `false`  
`collapsed` |  `boolean` |  `false`  
#### Returns
`CalloutElement`
#### Overrides
`AbstractMarkdownElementContainer.constructor`
## Properties
### apiInstance
> `readonly` **apiInstance** : `API`
Defined in: jsEngine/api/markdown/AbstractMarkdownElement.ts:9
#### Inherited from
`AbstractMarkdownElementContainer.apiInstance`
### args
> **args** : `string`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:398
### collapsed
> **collapsed** : `boolean`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:400
### collapsible
> **collapsible** : `boolean`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:399
### markdownElements
> **markdownElements** : `AbstractMarkdownElement`[]
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:12
#### Inherited from
`AbstractMarkdownElementContainer.markdownElements`
### title
> **title** : `string`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:396
### type
> **type** : `string`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:397
## Methods
### addBoldText()
> **addBoldText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:53
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addBoldText`
### addCode()
> **addCode**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:85
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addCode`
### addCursiveText()
> **addCursiveText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:61
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addCursiveText`
### addElement()
> **addElement**(`element`): `void`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:35
Adds a child element to the container.
#### Parameters
Parameter | Type | Description  
---|---|---  
`element` |  `AbstractMarkdownElement`  
#### Returns
`void`
#### Throws
Error if the element is not allowed in the container.
#### Inherited from
`AbstractMarkdownElementContainer.addElement`
### addHighlightedText()
> **addHighlightedText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:77
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addHighlightedText`
### addText()
> **addText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:45
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addText`
### addUnderlinedText()
> **addUnderlinedText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:69
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addUnderlinedText`
### createBlockQuote()
> **createBlockQuote**(): `BlockQuoteElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:109
#### Returns
`BlockQuoteElement`
#### Inherited from
`AbstractMarkdownElementContainer.createBlockQuote`
### createCallout()
> **createCallout**(`title`, `type`, `args`): `CalloutElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:115
#### Parameters
Parameter | Type | Default value  
---|---|---  
`title` |  `string` |  `undefined`  
`type` |  `string` |  `undefined`  
`args` |  `string` |  `''`  
#### Returns
`CalloutElement`
#### Inherited from
`AbstractMarkdownElementContainer.createCallout`
### createCodeBlock()
> **createCodeBlock**(`language`, `content`): `CodeBlockElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:131
#### Parameters
Parameter | Type  
---|---  
`language` |  `string`  
`content` |  `string`  
#### Returns
`CodeBlockElement`
#### Inherited from
`AbstractMarkdownElementContainer.createCodeBlock`
### createCollapsibleCallout()
> **createCollapsibleCallout**(`title`, `type`, `args`, `collapsed`): `CalloutElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:123
#### Parameters
Parameter | Type | Default value  
---|---|---  
`title` |  `string` |  `undefined`  
`type` |  `string` |  `undefined`  
`args` |  `string` |  `''`  
`collapsed` |  `boolean` |  `false`  
#### Returns
`CalloutElement`
#### Inherited from
`AbstractMarkdownElementContainer.createCollapsibleCallout`
### createHeading()
> **createHeading**(`level`, `content`): `HeadingElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:101
#### Parameters
Parameter | Type  
---|---  
`level` |  `number`  
`content` |  `string`  
#### Returns
`HeadingElement`
#### Inherited from
`AbstractMarkdownElementContainer.createHeading`
### createList()
> **createList**(`ordered`): `ListElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:147
#### Parameters
Parameter | Type | Default value  
---|---|---  
`ordered` |  `boolean` |  `false`  
#### Returns
`ListElement`
#### Inherited from
`AbstractMarkdownElementContainer.createList`
### createOrderedList()
> **createOrderedList**(): `ListElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:155
#### Returns
`ListElement`
#### Inherited from
`AbstractMarkdownElementContainer.createOrderedList`
### createParagraph()
> **createParagraph**(`content`): `ParagraphElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:93
#### Parameters
Parameter | Type  
---|---  
`content` |  `string`  
#### Returns
`ParagraphElement`
#### Inherited from
`AbstractMarkdownElementContainer.createParagraph`
### createTable()
> **createTable**(`header`, `body`): `TableElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:139
#### Parameters
Parameter | Type  
---|---  
`header` |  `string`[]  
`body` |  `TableElementType`[][]  
#### Returns
`TableElement`
#### Inherited from
`AbstractMarkdownElementContainer.createTable`
### toMarkdown()
> **toMarkdown**(): `MarkdownString`
Defined in: jsEngine/api/markdown/AbstractMarkdownElement.ts:28
Converts the element to a MarkdownString.
#### Returns
`MarkdownString`
#### Inherited from
`AbstractMarkdownElementContainer.toMarkdown`
### toString()
> **toString**(): `string`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:412
Converts the element to a string.
#### Returns
`string`
#### Overrides
`AbstractMarkdownElementContainer.toString`


================================================================================

## 4. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/headingelement

Skip to content
# HeadingElement
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:319
Represents a markdown heading.
## Extends
  * `AbstractMarkdownElementContainer`


## Constructors
### new HeadingElement()
> **new HeadingElement**(`apiInstance`, `level`, `content`): `HeadingElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:322
#### Parameters
Parameter | Type  
---|---  
`apiInstance` |   
`level` |  `number`  
`content` |  `string`  
#### Returns
`HeadingElement`
#### Overrides
`AbstractMarkdownElementContainer.constructor`
## Properties
### apiInstance
> `readonly` **apiInstance** : `API`
Defined in: jsEngine/api/markdown/AbstractMarkdownElement.ts:9
#### Inherited from
`AbstractMarkdownElementContainer.apiInstance`
### level
> **level** : `number`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:320
### markdownElements
> **markdownElements** : `AbstractMarkdownElement`[]
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:12
#### Inherited from
`AbstractMarkdownElementContainer.markdownElements`
## Methods
### addBoldText()
> **addBoldText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:53
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addBoldText`
### addCode()
> **addCode**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:85
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addCode`
### addCursiveText()
> **addCursiveText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:61
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addCursiveText`
### addElement()
> **addElement**(`element`): `void`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:35
Adds a child element to the container.
#### Parameters
Parameter | Type | Description  
---|---|---  
`element` |  `AbstractMarkdownElement`  
#### Returns
`void`
#### Throws
Error if the element is not allowed in the container.
#### Inherited from
`AbstractMarkdownElementContainer.addElement`
### addHighlightedText()
> **addHighlightedText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:77
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addHighlightedText`
### addText()
> **addText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:45
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addText`
### addUnderlinedText()
> **addUnderlinedText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:69
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addUnderlinedText`
### createBlockQuote()
> **createBlockQuote**(): `BlockQuoteElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:109
#### Returns
`BlockQuoteElement`
#### Inherited from
`AbstractMarkdownElementContainer.createBlockQuote`
### createCallout()
> **createCallout**(`title`, `type`, `args`): `CalloutElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:115
#### Parameters
Parameter | Type | Default value  
---|---|---  
`title` |  `string` |  `undefined`  
`type` |  `string` |  `undefined`  
`args` |  `string` |  `''`  
#### Returns
`CalloutElement`
#### Inherited from
`AbstractMarkdownElementContainer.createCallout`
### createCodeBlock()
> **createCodeBlock**(`language`, `content`): `CodeBlockElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:131
#### Parameters
Parameter | Type  
---|---  
`language` |  `string`  
`content` |  `string`  
#### Returns
`CodeBlockElement`
#### Inherited from
`AbstractMarkdownElementContainer.createCodeBlock`
### createCollapsibleCallout()
> **createCollapsibleCallout**(`title`, `type`, `args`, `collapsed`): `CalloutElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:123
#### Parameters
Parameter | Type | Default value  
---|---|---  
`title` |  `string` |  `undefined`  
`type` |  `string` |  `undefined`  
`args` |  `string` |  `''`  
`collapsed` |  `boolean` |  `false`  
#### Returns
`CalloutElement`
#### Inherited from
`AbstractMarkdownElementContainer.createCollapsibleCallout`
### createHeading()
> **createHeading**(`level`, `content`): `HeadingElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:101
#### Parameters
Parameter | Type  
---|---  
`level` |  `number`  
`content` |  `string`  
#### Returns
`HeadingElement`
#### Inherited from
`AbstractMarkdownElementContainer.createHeading`
### createList()
> **createList**(`ordered`): `ListElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:147
#### Parameters
Parameter | Type | Default value  
---|---|---  
`ordered` |  `boolean` |  `false`  
#### Returns
`ListElement`
#### Inherited from
`AbstractMarkdownElementContainer.createList`
### createOrderedList()
> **createOrderedList**(): `ListElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:155
#### Returns
`ListElement`
#### Inherited from
`AbstractMarkdownElementContainer.createOrderedList`
### createParagraph()
> **createParagraph**(`content`): `ParagraphElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:93
#### Parameters
Parameter | Type  
---|---  
`content` |  `string`  
#### Returns
`ParagraphElement`
#### Inherited from
`AbstractMarkdownElementContainer.createParagraph`
### createTable()
> **createTable**(`header`, `body`): `TableElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:139
#### Parameters
Parameter | Type  
---|---  
`header` |  `string`[]  
`body` |  `TableElementType`[][]  
#### Returns
`TableElement`
#### Inherited from
`AbstractMarkdownElementContainer.createTable`
### toMarkdown()
> **toMarkdown**(): `MarkdownString`
Defined in: jsEngine/api/markdown/AbstractMarkdownElement.ts:28
Converts the element to a MarkdownString.
#### Returns
`MarkdownString`
#### Inherited from
`AbstractMarkdownElementContainer.toMarkdown`
### toString()
> **toString**(): `string`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:329
Converts the element to a string.
#### Returns
`string`
#### Overrides
`AbstractMarkdownElementContainer.toString`


================================================================================

## 5. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/codeelement

Skip to content
# CodeElement
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:217
Represents an inline markdown code block.
## Extends
  * `AbstractMarkdownLiteral`


## Constructors
### new CodeElement()
> **new CodeElement**(`apiInstance`, `content`): `CodeElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:220
#### Parameters
Parameter | Type  
---|---  
`apiInstance` |   
`content` |  `string`  
#### Returns
`CodeElement`
#### Overrides
`AbstractMarkdownLiteral.constructor`
## Properties
### apiInstance
> `readonly` **apiInstance** : `API`
Defined in: jsEngine/api/markdown/AbstractMarkdownElement.ts:9
#### Inherited from
`AbstractMarkdownLiteral.apiInstance`
### content
> **content** : `string`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:218
## Methods
### toMarkdown()
> **toMarkdown**(): `MarkdownString`
Defined in: jsEngine/api/markdown/AbstractMarkdownElement.ts:28
Converts the element to a MarkdownString.
#### Returns
`MarkdownString`
#### Inherited from
`AbstractMarkdownLiteral.toMarkdown`
### toString()
> **toString**(): `string`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:226
Converts the element to a string.
#### Returns
`string`
#### Overrides
`AbstractMarkdownLiteral.toString`


================================================================================

## 6. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/blockquoteelement

Skip to content
# BlockQuoteElement
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:382
Represents a markdown block quote.
## Extends
  * `AbstractMarkdownElementContainer`


## Constructors
### new BlockQuoteElement()
> **new BlockQuoteElement**(`apiInstance`): `BlockQuoteElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:14
#### Parameters
Parameter | Type  
---|---  
`apiInstance` |   
#### Returns
`BlockQuoteElement`
#### Inherited from
`AbstractMarkdownElementContainer.constructor`
## Properties
### apiInstance
> `readonly` **apiInstance** : `API`
Defined in: jsEngine/api/markdown/AbstractMarkdownElement.ts:9
#### Inherited from
`AbstractMarkdownElementContainer.apiInstance`
### markdownElements
> **markdownElements** : `AbstractMarkdownElement`[]
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:12
#### Inherited from
`AbstractMarkdownElementContainer.markdownElements`
## Methods
### addBoldText()
> **addBoldText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:53
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addBoldText`
### addCode()
> **addCode**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:85
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addCode`
### addCursiveText()
> **addCursiveText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:61
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addCursiveText`
### addElement()
> **addElement**(`element`): `void`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:35
Adds a child element to the container.
#### Parameters
Parameter | Type | Description  
---|---|---  
`element` |  `AbstractMarkdownElement`  
#### Returns
`void`
#### Throws
Error if the element is not allowed in the container.
#### Inherited from
`AbstractMarkdownElementContainer.addElement`
### addHighlightedText()
> **addHighlightedText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:77
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addHighlightedText`
### addText()
> **addText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:45
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addText`
### addUnderlinedText()
> **addUnderlinedText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:69
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addUnderlinedText`
### createBlockQuote()
> **createBlockQuote**(): `BlockQuoteElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:109
#### Returns
`BlockQuoteElement`
#### Inherited from
`AbstractMarkdownElementContainer.createBlockQuote`
### createCallout()
> **createCallout**(`title`, `type`, `args`): `CalloutElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:115
#### Parameters
Parameter | Type | Default value  
---|---|---  
`title` |  `string` |  `undefined`  
`type` |  `string` |  `undefined`  
`args` |  `string` |  `''`  
#### Returns
`CalloutElement`
#### Inherited from
`AbstractMarkdownElementContainer.createCallout`
### createCodeBlock()
> **createCodeBlock**(`language`, `content`): `CodeBlockElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:131
#### Parameters
Parameter | Type  
---|---  
`language` |  `string`  
`content` |  `string`  
#### Returns
`CodeBlockElement`
#### Inherited from
`AbstractMarkdownElementContainer.createCodeBlock`
### createCollapsibleCallout()
> **createCollapsibleCallout**(`title`, `type`, `args`, `collapsed`): `CalloutElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:123
#### Parameters
Parameter | Type | Default value  
---|---|---  
`title` |  `string` |  `undefined`  
`type` |  `string` |  `undefined`  
`args` |  `string` |  `''`  
`collapsed` |  `boolean` |  `false`  
#### Returns
`CalloutElement`
#### Inherited from
`AbstractMarkdownElementContainer.createCollapsibleCallout`
### createHeading()
> **createHeading**(`level`, `content`): `HeadingElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:101
#### Parameters
Parameter | Type  
---|---  
`level` |  `number`  
`content` |  `string`  
#### Returns
`HeadingElement`
#### Inherited from
`AbstractMarkdownElementContainer.createHeading`
### createList()
> **createList**(`ordered`): `ListElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:147
#### Parameters
Parameter | Type | Default value  
---|---|---  
`ordered` |  `boolean` |  `false`  
#### Returns
`ListElement`
#### Inherited from
`AbstractMarkdownElementContainer.createList`
### createOrderedList()
> **createOrderedList**(): `ListElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:155
#### Returns
`ListElement`
#### Inherited from
`AbstractMarkdownElementContainer.createOrderedList`
### createParagraph()
> **createParagraph**(`content`): `ParagraphElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:93
#### Parameters
Parameter | Type  
---|---  
`content` |  `string`  
#### Returns
`ParagraphElement`
#### Inherited from
`AbstractMarkdownElementContainer.createParagraph`
### createTable()
> **createTable**(`header`, `body`): `TableElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:139
#### Parameters
Parameter | Type  
---|---  
`header` |  `string`[]  
`body` |  `TableElementType`[][]  
#### Returns
`TableElement`
#### Inherited from
`AbstractMarkdownElementContainer.createTable`
### toMarkdown()
> **toMarkdown**(): `MarkdownString`
Defined in: jsEngine/api/markdown/AbstractMarkdownElement.ts:28
Converts the element to a MarkdownString.
#### Returns
`MarkdownString`
#### Inherited from
`AbstractMarkdownElementContainer.toMarkdown`
### toString()
> **toString**(): `string`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:383
Converts the element to a string.
#### Returns
`string`
#### Overrides
`AbstractMarkdownElementContainer.toString`


================================================================================

## 7. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/engine

Skip to content
# Engine
Defined in: jsEngine/engine/Engine.ts:33
## Constructors
### new Engine()
> **new Engine**(`app`, `plugin`): `Engine`
Defined in: jsEngine/engine/Engine.ts:40
#### Parameters
Parameter | Type  
---|---  
`app` |  `App`  
`plugin` |  `JsEnginePlugin`  
#### Returns
`Engine`
## Properties
### activeExecutions
> `readonly` **activeExecutions** : `Map`<`string`, `JsExecution`>
Defined in: jsEngine/engine/Engine.ts:38
## Methods
### execute()
> **execute**(`params`): `Promise`<`JsExecution`>
Defined in: jsEngine/engine/Engine.ts:53
Execute JavaScript code.
#### Parameters
Parameter | Type | Description  
---|---|---  
`params` |  `EngineExecutionParams`  
#### Returns
`Promise`<`JsExecution`>
### openExecutionStatsModal()
> **openExecutionStatsModal**(`jsExecution`): `void`
Defined in: jsEngine/engine/Engine.ts:73
Open the execution stats modal for a given JsExecution.
#### Parameters
Parameter | Type | Description  
---|---|---  
`jsExecution` |  `JsExecution`  
#### Returns
`void`


================================================================================

## 8. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/instanceid

Skip to content
# InstanceId
Defined in: jsEngine/api/InstanceId.ts:13
Identifies an instance of the API.
For the API passed into a JsExecution this is the id of the JsExecution itself.
## Constructors
### new InstanceId()
> **new InstanceId**(`name`, `id`, `executionContext`?): `InstanceId`
Defined in: jsEngine/api/InstanceId.ts:18
#### Parameters
Parameter | Type  
---|---  
`name` |  `string`  
`id` |  `string`  
`executionContext`? |  `ExecutionContext`  
#### Returns
`InstanceId`
## Properties
### executionContext
> `readonly` **executionContext** : `undefined` | `ExecutionContext`
Defined in: jsEngine/api/InstanceId.ts:16
### id
> `readonly` **id** : `string`
Defined in: jsEngine/api/InstanceId.ts:15
### name
> `readonly` **name** : `string`
Defined in: jsEngine/api/InstanceId.ts:14
## Methods
### toString()
> **toString**(): `string`
Defined in: jsEngine/api/InstanceId.ts:24
#### Returns
`string`
### create()
> `static` **create**(`name`): `InstanceId`
Defined in: jsEngine/api/InstanceId.ts:28
#### Parameters
Parameter | Type  
---|---  
`name` |  `string`  
#### Returns
`InstanceId`


================================================================================

## 9. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/api

Skip to content
# API
Defined in: jsEngine/api/API.ts:18
## Constructors
### new API()
> **new API**(`app`, `plugin`, `instanceId`): `API`
Defined in: jsEngine/api/API.ts:51
#### Parameters
Parameter | Type  
---|---  
`app` |  `App`  
`plugin` |  `JsEnginePlugin`  
`instanceId` |  `InstanceId`  
#### Returns
## Properties
### app
> `readonly` **app** : `App`
Defined in: jsEngine/api/API.ts:22
Reference to the obsidian app.
### instanceId
> `readonly` **instanceId** : `InstanceId`
Defined in: jsEngine/api/API.ts:27
### internal
> `readonly` **internal** : `InternalAPI`
Defined in: jsEngine/api/API.ts:49
API to interact with js engines internals.
### lib
> `readonly` **lib** : `LibAPI`
Defined in: jsEngine/api/API.ts:40
API to interact with packaged libraries.
### markdown
> `readonly` **markdown** : `MarkdownAPI`
Defined in: jsEngine/api/API.ts:32
API to interact with markdown.
### message
> `readonly` **message** : `MessageAPI`
Defined in: jsEngine/api/API.ts:36
API to interact with the plugins message system.
### plugin
> `readonly` **plugin** : `JsEnginePlugin`
Defined in: jsEngine/api/API.ts:26
Reference the JS Engine plugin.
### prompt
> `readonly` **prompt** : `PromptAPI`
Defined in: jsEngine/api/API.ts:45
### query
> `readonly` **query** : `QueryAPI`
Defined in: jsEngine/api/API.ts:44
API to query your vault with simple javascript functions.
### validators
> `readonly` **validators** : `Validators`
Defined in: jsEngine/api/API.ts:28
## Methods
### getObsidianModule()
> **getObsidianModule**(): `__module`
Defined in: jsEngine/api/API.ts:110
Gets the obsidian module. This allows you to access all things exported by the obsidian module.
#### Returns
`__module`
#### Example
```

constobsidian= engine.getObsidianModule();
new obsidian.Notice('Hello World!');

```

### getPlugin()
> **getPlugin**(`pluginId`): `undefined` | `Plugin`
Defined in: jsEngine/api/API.ts:94
Gets a plugin by its id. A plugin id can be found by looking at its manifest. If the plugin is not enabled, this will return undefined.
#### Parameters
Parameter | Type | Description  
---|---|---  
`pluginId` |  `string` |  the id of the plugin.  
#### Returns
`undefined` | `Plugin`
### importJs()
> **importJs**(`path`): `Promise`<`unknown`>
Defined in: jsEngine/api/API.ts:74
Loads an ECMAScript module from a vault relative path. Everything you import via this function will be loaded as an ECMAScript module.
Since imports are cached by the browser (aka Obsidian), you might need to reload Obsidian to see changes made to the imported file.
#### Parameters
Parameter | Type | Description  
---|---|---  
`path` |  `string` |  the vault relative path of the file to import  
#### Returns
`Promise`<`unknown`>
### parseLink()
> **parseLink**(`link`): `undefined` | `MarkdownLink`
Defined in: jsEngine/api/API.ts:149
Parses a markdown link. This link can be a markdown link or a wiki link.
#### Parameters
Parameter | Type | Description  
---|---|---  
`link` |  `string` |  the link to parse.  
#### Returns
`undefined` | `MarkdownLink`
### reactive()
> **reactive**(`fn`, …`initialArgs`): `ReactiveComponent`
Defined in: jsEngine/api/API.ts:121
Creates a reactive component. Reactive components are useful for creating dynamic content.
#### Parameters
Parameter | Type | Description  
---|---|---  
`fn` |  `JsFunc` |  the function to rerun. It’s return value will be rendered.  
…`initialArgs` |  `unknown`[] |  the initial arguments (for the first render) to pass to the function.  
#### Returns
`ReactiveComponent`
### resolveLinkToTFile()
> **resolveLinkToTFile**(`link`, `sourcePath`): `undefined` | `TFile`
Defined in: jsEngine/api/API.ts:135
Gets the target file of a link. This link can be a markdown link or a wiki link. If the link target is not found, this will return undefined.
#### Parameters
Parameter | Type | Description  
---|---|---  
`link` |  `string` |  the link to get the target file of.  
`sourcePath` |  `string` |  the path of the file that contains the link. This is needed to resolve relative links.  
#### Returns
`undefined` | `TFile`


================================================================================

## 10. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/jsexecution

Skip to content
# JsExecution
Defined in: jsEngine/engine/JsExecution.ts:165
Models the execution of a JavaScript string.
## Constructors
### new JsExecution()
> **new JsExecution**(`params`): `JsExecution`
Defined in: jsEngine/engine/JsExecution.ts:185
#### Parameters
Parameter | Type  
---|---  
`params` |  `JsExecutionParams`  
#### Returns
`JsExecution`
## Properties
### app
> `readonly` **app** : `App`
Defined in: jsEngine/engine/JsExecution.ts:166
### code
> `readonly` **code** : `string`
Defined in: jsEngine/engine/JsExecution.ts:176
### functionBuildError
> **functionBuildError** : `undefined` | `Error`
Defined in: jsEngine/engine/JsExecution.ts:179
### functionBuildTime
> **functionBuildTime** : `undefined` | `number`
Defined in: jsEngine/engine/JsExecution.ts:182
### functionRunError
> **functionRunError** : `undefined` | `Error`
Defined in: jsEngine/engine/JsExecution.ts:180
### functionRunTime
> **functionRunTime** : `undefined` | `number`
Defined in: jsEngine/engine/JsExecution.ts:183
### globals
> `readonly` **globals** : `JsExecutionGlobals`
Defined in: jsEngine/engine/JsExecution.ts:174
### plugin
> `readonly` **plugin** : `JsEnginePlugin`
Defined in: jsEngine/engine/JsExecution.ts:167
### result
> **result** : `unknown`
Defined in: jsEngine/engine/JsExecution.ts:177
### uuid
> `readonly` **uuid** : `string`
Defined in: jsEngine/engine/JsExecution.ts:175
## Methods
### buildFunction()
> **buildFunction**(): `void`
Defined in: jsEngine/engine/JsExecution.ts:211
Creates the function from the code provided in the constructor.
#### Returns
`void`
### getMessages()
> **getMessages**(): `MessageWrapper`[]
Defined in: jsEngine/engine/JsExecution.ts:286
Returns the messages generated by the function.
#### Returns
`MessageWrapper`[]
### isSuccessful()
> **isSuccessful**(): `boolean`
Defined in: jsEngine/engine/JsExecution.ts:279
Returns true if the function was built and run without errors.
#### Returns
`boolean`
### openStatsModal()
> **openStatsModal**(): `void`
Defined in: jsEngine/engine/JsExecution.ts:293
Opens the execution stats modal for this execution.
#### Returns
`void`
### runFunction()
> **runFunction**(): `Promise`<`void`>
Defined in: jsEngine/engine/JsExecution.ts:242
Runs the function created by JsExecution.buildFunction.
#### Returns
`Promise`<`void`>


================================================================================

## 11. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/internalapi

Skip to content
# InternalAPI
Defined in: jsEngine/api/Internal.ts:32
The internal API provides access to some of js engines internals.
## Constructors
### new InternalAPI()
> **new InternalAPI**(`apiInstance`): `InternalAPI`
Defined in: jsEngine/api/Internal.ts:35
#### Parameters
Parameter | Type  
---|---  
`apiInstance` |   
#### Returns
`InternalAPI`
## Methods
### createExecutionGlobals()
> **createExecutionGlobals**(`options`): `JsExecutionGlobals`
Defined in: jsEngine/api/Internal.ts:250
Creates execution globals.
#### Parameters
Parameter | Type | Description  
---|---|---  
`options` |  `JsExecutionGlobalsConstructionOptions`  
#### Returns
`JsExecutionGlobals`
### createRenderer()
> **createRenderer**(`container`, `sourcePath`, `component`): `ResultRenderer`
Defined in: jsEngine/api/Internal.ts:57
Creates a result renderer.
#### Parameters
Parameter | Type | Description  
---|---|---  
`container` |  `HTMLElement`  
`sourcePath` |  `string`  
`component` |  `Component`  
#### Returns
`ResultRenderer`
### execute()
> **execute**(`params`): `Promise`<`JsExecution`>
Defined in: jsEngine/api/Internal.ts:44
Executes the given code.
#### Parameters
Parameter | Type | Description  
---|---|---  
`params` |  `EngineExecutionParams`  
#### Returns
`Promise`<`JsExecution`>
### executeFile()
> **executeFile**(`path`, `params`): `Promise`<`JsExecution`>
Defined in: jsEngine/api/Internal.ts:72
Load and execute the given file.
#### Parameters
Parameter | Type | Description  
---|---|---  
`path` |  `string`  
`params` |  `ExecuteFileEngineExecutionParams`  
#### Returns
`Promise`<`JsExecution`>
### executeFileSimple()
> **executeFileSimple**(`path`, `params`?): `Promise`<`JsExecution`>
Defined in: jsEngine/api/Internal.ts:97
Lead and execute the given file. This method also handles the lifetime of the execution. The component for the execution is created and destroyed automatically.
#### Parameters
Parameter | Type | Description  
---|---|---  
`path` |  `string`  
`params`? |  `ExecuteFileSimpleEngineExecutionParams`  
#### Returns
`Promise`<`JsExecution`>
### executeStartupScripts()
> **executeStartupScripts**(): `Promise`<`void`>
Defined in: jsEngine/api/Internal.ts:266
Runs all startup scripts defined in the plugins settings.
#### Returns
`Promise`<`void`>
### ~~getContextForFile()~~
> **getContextForFile**(`path`): `Promise`<`ExecutionContext`>
Defined in: jsEngine/api/Internal.ts:121
Gets the execution context for a specific file, throws when the file does not exist.
#### Parameters
Parameter | Type | Description  
---|---|---  
`path` |  `string`  
#### Returns
`Promise`<`ExecutionContext`>
### getContextForJSFile()
> **getContextForJSFile**(`path`): `Promise`<`JSFileExecutionContext`>
Defined in: jsEngine/api/Internal.ts:208
Gets the execution context for a JS file.
#### Parameters
Parameter | Type | Description  
---|---|---  
`path` |  `string` |  The file path of the JS file.  
#### Returns
`Promise`<`JSFileExecutionContext`>
### getContextForMarkdownCallingJSFile()
> **getContextForMarkdownCallingJSFile**(`markdownPath`, `jsPath`): `Promise`<`MarkdownCallingJSFileExecutionContext`>
Defined in: jsEngine/api/Internal.ts:167
Gets the execution context for when a markdown file calls a JS file. This adds some extra info about the markdown file into the context, compared to getContextForJSFile.
#### Parameters
Parameter | Type | Description  
---|---|---  
`markdownPath` |  `string` |  The file path of the markdown file.  
`jsPath` |  `string` |  The file path of the JS file.  
#### Returns
`Promise`<`MarkdownCallingJSFileExecutionContext`>
### getContextForMarkdownCodeBlock()
> **getContextForMarkdownCodeBlock**(`path`): `Promise`<`MarkdownCodeBlockExecutionContext`>
Defined in: jsEngine/api/Internal.ts:145
Gets the execution context for a markdown code block.
#### Parameters
Parameter | Type | Description  
---|---|---  
`path` |  `string` |  The file path of the markdown file the code block is in.  
#### Returns
`Promise`<`MarkdownCodeBlockExecutionContext`>
### getContextForMarkdownOther()
> **getContextForMarkdownOther**(`path`): `Promise`<`MarkdownOtherExecutionContext`>
Defined in: jsEngine/api/Internal.ts:189
Gets the execution context for a markdown code block.
#### Parameters
Parameter | Type | Description  
---|---|---  
`path` |  `string` |  The file path of the markdown file the code block is in.  
#### Returns
`Promise`<`MarkdownOtherExecutionContext`>
### getContextForUnknown()
> **getContextForUnknown**(`path`?): `Promise`<`UnknownExecutionContext`>
Defined in: jsEngine/api/Internal.ts:225
Gets an unknown execution context for anything that is not a markdown code block or a JS file.
#### Parameters
Parameter | Type | Description  
---|---|---  
`path`? |  `string` |  An optional file path that will get resolved to a TFile.  
#### Returns
`Promise`<`UnknownExecutionContext`>


================================================================================

## 12. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/listelement

Skip to content
# ListElement
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:433
## Extends
  * `AbstractMarkdownElementContainer`


## Constructors
### new ListElement()
> **new ListElement**(`apiInstance`, `ordered`): `ListElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:436
#### Parameters
Parameter | Type  
---|---  
`apiInstance` |   
`ordered` |  `boolean`  
#### Returns
`ListElement`
#### Overrides
`AbstractMarkdownElementContainer.constructor`
## Properties
### apiInstance
> `readonly` **apiInstance** : `API`
Defined in: jsEngine/api/markdown/AbstractMarkdownElement.ts:9
#### Inherited from
`AbstractMarkdownElementContainer.apiInstance`
### markdownElements
> **markdownElements** : `AbstractMarkdownElement`[]
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:12
#### Inherited from
`AbstractMarkdownElementContainer.markdownElements`
### ordered
> **ordered** : `boolean`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:434
## Methods
### addBoldText()
> **addBoldText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:53
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addBoldText`
### addCode()
> **addCode**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:85
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addCode`
### addCursiveText()
> **addCursiveText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:61
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addCursiveText`
### addElement()
> **addElement**(`element`): `void`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:35
Adds a child element to the container.
#### Parameters
Parameter | Type | Description  
---|---|---  
`element` |  `AbstractMarkdownElement`  
#### Returns
`void`
#### Throws
Error if the element is not allowed in the container.
#### Inherited from
`AbstractMarkdownElementContainer.addElement`
### addHighlightedText()
> **addHighlightedText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:77
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addHighlightedText`
### addText()
> **addText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:45
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addText`
### addUnderlinedText()
> **addUnderlinedText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:69
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addUnderlinedText`
### createBlockQuote()
> **createBlockQuote**(): `BlockQuoteElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:109
#### Returns
`BlockQuoteElement`
#### Inherited from
`AbstractMarkdownElementContainer.createBlockQuote`
### createCallout()
> **createCallout**(`title`, `type`, `args`): `CalloutElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:115
#### Parameters
Parameter | Type | Default value  
---|---|---  
`title` |  `string` |  `undefined`  
`type` |  `string` |  `undefined`  
`args` |  `string` |  `''`  
#### Returns
`CalloutElement`
#### Inherited from
`AbstractMarkdownElementContainer.createCallout`
### createCodeBlock()
> **createCodeBlock**(`language`, `content`): `CodeBlockElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:131
#### Parameters
Parameter | Type  
---|---  
`language` |  `string`  
`content` |  `string`  
#### Returns
`CodeBlockElement`
#### Inherited from
`AbstractMarkdownElementContainer.createCodeBlock`
### createCollapsibleCallout()
> **createCollapsibleCallout**(`title`, `type`, `args`, `collapsed`): `CalloutElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:123
#### Parameters
Parameter | Type | Default value  
---|---|---  
`title` |  `string` |  `undefined`  
`type` |  `string` |  `undefined`  
`args` |  `string` |  `''`  
`collapsed` |  `boolean` |  `false`  
#### Returns
`CalloutElement`
#### Inherited from
`AbstractMarkdownElementContainer.createCollapsibleCallout`
### createHeading()
> **createHeading**(`level`, `content`): `HeadingElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:101
#### Parameters
Parameter | Type  
---|---  
`level` |  `number`  
`content` |  `string`  
#### Returns
`HeadingElement`
#### Inherited from
`AbstractMarkdownElementContainer.createHeading`
### createList()
> **createList**(`ordered`): `ListElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:147
#### Parameters
Parameter | Type | Default value  
---|---|---  
`ordered` |  `boolean` |  `false`  
#### Returns
`ListElement`
#### Inherited from
`AbstractMarkdownElementContainer.createList`
### createOrderedList()
> **createOrderedList**(): `ListElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:155
#### Returns
`ListElement`
#### Inherited from
`AbstractMarkdownElementContainer.createOrderedList`
### createParagraph()
> **createParagraph**(`content`): `ParagraphElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:93
#### Parameters
Parameter | Type  
---|---  
`content` |  `string`  
#### Returns
`ParagraphElement`
#### Inherited from
`AbstractMarkdownElementContainer.createParagraph`
### createTable()
> **createTable**(`header`, `body`): `TableElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:139
#### Parameters
Parameter | Type  
---|---  
`header` |  `string`[]  
`body` |  `TableElementType`[][]  
#### Returns
`TableElement`
#### Inherited from
`AbstractMarkdownElementContainer.createTable`
### toMarkdown()
> **toMarkdown**(): `MarkdownString`
Defined in: jsEngine/api/markdown/AbstractMarkdownElement.ts:28
Converts the element to a MarkdownString.
#### Returns
`MarkdownString`
#### Inherited from
`AbstractMarkdownElementContainer.toMarkdown`
### toString()
> **toString**(): `string`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:450
Converts the element to a string.
#### Returns
`string`
#### Overrides
`AbstractMarkdownElementContainer.toString`


================================================================================

## 13. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/libapi

Skip to content
# LibAPI
Defined in: jsEngine/api/LibAPI.ts:21
The lib API provides in interface to some external libraries packaged into js engine.
## Constructors
### new LibAPI()
> **new LibAPI**(`apiInstance`): `LibAPI`
Defined in: jsEngine/api/LibAPI.ts:24
#### Parameters
Parameter | Type  
---|---  
`apiInstance` |   
#### Returns
`LibAPI`
## Methods
### itertools()
> **itertools**(): `__module`
Defined in: jsEngine/api/LibAPI.ts:45
Get the itertools-ts library.
#### Returns
`__module`
### parsinom()
> **parsinom**(): `LibParsiNOM`
Defined in: jsEngine/api/LibAPI.ts:31
Get the ParsiNOM library.
#### Returns
`LibParsiNOM`


================================================================================

## 14. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/queryapi

Skip to content
# QueryAPI
Defined in: jsEngine/api/QueryAPI.ts:7
## Constructors
### new QueryAPI()
> **new QueryAPI**(`apiInstance`): `QueryAPI`
Defined in: jsEngine/api/QueryAPI.ts:10
#### Parameters
Parameter | Type  
---|---  
`apiInstance` |   
#### Returns
`QueryAPI`
## Properties
### apiInstance
> `readonly` **apiInstance** : `API`
Defined in: jsEngine/api/QueryAPI.ts:8
## Methods
### files()
> **files** <`T`>(`query`): `T`[]
Defined in: jsEngine/api/QueryAPI.ts:29
This function will run the `query` callback on every markdown file in the vault and then return a list of the results, with `undefined` filtered out.
#### Type Parameters
Type Parameter  
---  
#### Parameters
Parameter | Type  
---|---  
`query` |  (`file`) => `undefined` | `T`  
#### Returns
`T`[]
#### Examples
```

// Find all markdown `TFiles` that start with the word "Foo"
constfiles= engine.query.files(file=> file.name.startsWith("Foo") ? file :undefined);

```

```

// Find all the names of all markdown files that are in the "Foo" folder
constfileNames= engine.query.files(file=> file.path.startsWith("Foo/") ? file.name :undefined);

```

### filesWithMetadata()
> **filesWithMetadata** <`T`>(`query`): `T`[]
Defined in: jsEngine/api/QueryAPI.ts:47
This function functions similarly tp QueryAPI.files, but also provides the cache and tags of each file to the `query` callback.
#### Type Parameters
Type Parameter  
---  
#### Parameters
Parameter | Type  
---|---  
`query` |  (`file`, `cache`, `tags`, `frontmatterTags`) => `undefined` | `T`  
#### Returns
`T`[]
#### Example
```

// Find the paths of all markdown files that have the tag "Foo"
constpaths= engine.query.filesWithMetadata((file, cache, tags) => tags.includes("Foo") ? file.path :undefined);

```

### incomingLinks()
> **incomingLinks**(`file`): `object`[]
Defined in: jsEngine/api/QueryAPI.ts:92
#### Parameters
Parameter | Type  
---|---  
`file` |  `TFile`  
#### Returns
`object`[]
### outgoingLinks()
> **outgoingLinks**(`file`): `object`[]
Defined in: jsEngine/api/QueryAPI.ts:69
#### Parameters
Parameter | Type  
---|---  
`file` |  `TFile`  
#### Returns
`object`[]


================================================================================

## 15. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/markdownapi

Skip to content
# MarkdownAPI
Defined in: jsEngine/api/MarkdownAPI.ts:21
The markdown API provides utilities for creating markdown using js.
## Constructors
### new MarkdownAPI()
> **new MarkdownAPI**(`apiInstance`): `MarkdownAPI`
Defined in: jsEngine/api/MarkdownAPI.ts:24
#### Parameters
Parameter | Type  
---|---  
`apiInstance` |   
#### Returns
`MarkdownAPI`
## Methods
### create()
> **create**(`markdown`): `MarkdownString`
Defined in: jsEngine/api/MarkdownAPI.ts:42
Creates a markdown string form a normal string. This does not modify the string. It only wraps it in an object, so that the plugin can recognize and render it as markdown.
#### Parameters
Parameter | Type | Description  
---|---|---  
`markdown` |  `string` |  the string to wrap  
#### Returns
`MarkdownString`
### createBlockQuote()
> **createBlockQuote**(): `BlockQuoteElement`
Defined in: jsEngine/api/MarkdownAPI.ts:140
Creates a new markdown block quote element.
#### Returns
`BlockQuoteElement`
### createBoldText()
> **createBoldText**(`text`): `TextElement`
Defined in: jsEngine/api/MarkdownAPI.ts:64
Creates a new markdown text element with bold formatting.
#### Parameters
Parameter | Type | Description  
---|---|---  
`text` |  `string`  
#### Returns
`TextElement`
### createBuilder()
> **createBuilder**(): `MarkdownBuilder`
Defined in: jsEngine/api/MarkdownAPI.ts:31
Creates a markdown builder.
#### Returns
`MarkdownBuilder`
### createCallout()
> **createCallout**(`title`, `type`, `args`): `CalloutElement`
Defined in: jsEngine/api/MarkdownAPI.ts:151
Creates a new markdown callout element.
#### Parameters
Parameter | Type | Default value | Description  
---|---|---|---  
`title` |  `string` |  `undefined` |  the title of the callout  
`type` |  `string` |  `undefined` |  the type of the callout  
`args` |  `string` |  `''` |  the callout args, optional  
#### Returns
`CalloutElement`
### createCode()
> **createCode**(`text`): `CodeElement`
Defined in: jsEngine/api/MarkdownAPI.ts:108
Creates a new markdown code element.
#### Parameters
Parameter | Type | Description  
---|---|---  
`text` |  `string`  
#### Returns
`CodeElement`
### createCodeBlock()
> **createCodeBlock**(`language`, `content`): `CodeBlockElement`
Defined in: jsEngine/api/MarkdownAPI.ts:177
Creates a new markdown code block element.
#### Parameters
Parameter | Type | Description  
---|---|---  
`language` |  `string` |  the language of the code block  
`content` |  `string` |  the content of the code block  
#### Returns
`CodeBlockElement`
### createCollapsibleCallout()
> **createCollapsibleCallout**(`title`, `type`, `args`, `collapsed`): `CalloutElement`
Defined in: jsEngine/api/MarkdownAPI.ts:165
Creates a new markdown collapsible callout element.
#### Parameters
Parameter | Type | Default value | Description  
---|---|---|---  
`title` |  `string` |  `undefined` |  the title of the callout  
`type` |  `string` |  `undefined` |  the type of the callout  
`args` |  `string` |  `''` |  the callout args, optional  
`collapsed` |  `boolean` |  `false` |  whether the callout should be collapsed by default, optional  
#### Returns
`CalloutElement`
### createCursiveText()
> **createCursiveText**(`text`): `TextElement`
Defined in: jsEngine/api/MarkdownAPI.ts:75
Creates a new markdown text element with cursive formatting.
#### Parameters
Parameter | Type | Description  
---|---|---  
`text` |  `string`  
#### Returns
`TextElement`
### createHeading()
> **createHeading**(`level`, `content`): `HeadingElement`
Defined in: jsEngine/api/MarkdownAPI.ts:131
Creates a new markdown heading element.
#### Parameters
Parameter | Type | Description  
---|---|---  
`level` |  `number` |  the level of the heading from 1 to 6  
`content` |  `string` |  the text of the heading  
#### Returns
`HeadingElement`
### createHighlightedText()
> **createHighlightedText**(`text`): `TextElement`
Defined in: jsEngine/api/MarkdownAPI.ts:97
Creates a new markdown text element with highlighted formatting.
#### Parameters
Parameter | Type | Description  
---|---|---  
`text` |  `string`  
#### Returns
`TextElement`
### createList()
> **createList**(`ordered`): `ListElement`
Defined in: jsEngine/api/MarkdownAPI.ts:200
Creates a new markdown list element.
#### Parameters
Parameter | Type | Default value | Description  
---|---|---|---  
`ordered` |  `boolean` |  `false` |  whether the list should be ordered or not (use 1. or -), defaults to unordered  
#### Returns
`ListElement`
### createOrderedList()
> **createOrderedList**(): `ListElement`
Defined in: jsEngine/api/MarkdownAPI.ts:209
Creates a new ordered markdown list element.
#### Returns
`ListElement`
### createParagraph()
> **createParagraph**(`content`): `ParagraphElement`
Defined in: jsEngine/api/MarkdownAPI.ts:119
Creates a new markdown paragraph element.
#### Parameters
Parameter | Type | Description  
---|---|---  
`content` |  `string`  
#### Returns
`ParagraphElement`
### createTable()
> **createTable**(`header`, `body`): `TableElement`
Defined in: jsEngine/api/MarkdownAPI.ts:189
Creates a new markdown table element.
#### Parameters
Parameter | Type | Description  
---|---|---  
`header` |  `string`[] |  the header row  
`body` |  `string`[][] |  the table body  
#### Returns
`TableElement`
### createText()
> **createText**(`text`): `TextElement`
Defined in: jsEngine/api/MarkdownAPI.ts:53
Creates a new markdown text element.
#### Parameters
Parameter | Type | Description  
---|---|---  
`text` |  `string`  
#### Returns
`TextElement`
### createUnderlinedText()
> **createUnderlinedText**(`text`): `TextElement`
Defined in: jsEngine/api/MarkdownAPI.ts:86
Creates a new markdown text element with underline formatting.
#### Parameters
Parameter | Type | Description  
---|---|---  
`text` |  `string`  
#### Returns
`TextElement`


================================================================================

## 16. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/markdownstring

Skip to content
# MarkdownString
Defined in: jsEngine/api/markdown/MarkdownString.ts:10
A string that should be rendered as markdown by the plugin.
## Constructors
### new MarkdownString()
> **new MarkdownString**(`apiInstance`, `content`): `MarkdownString`
Defined in: jsEngine/api/markdown/MarkdownString.ts:14
#### Parameters
Parameter | Type  
---|---  
`apiInstance` |   
`content` |  `string`  
#### Returns
`MarkdownString`
## Properties
### apiInstance
> `readonly` **apiInstance** : `API`
Defined in: jsEngine/api/markdown/MarkdownString.ts:12
### content
> `readonly` **content** : `string`
Defined in: jsEngine/api/markdown/MarkdownString.ts:11


================================================================================

## 17. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/messageapi

Skip to content
# MessageAPI
Defined in: jsEngine/api/MessageAPI.ts:7
## Constructors
### new MessageAPI()
> **new MessageAPI**(`apiInstance`): `MessageAPI`
Defined in: jsEngine/api/MessageAPI.ts:11
#### Parameters
Parameter | Type  
---|---  
`apiInstance` |   
#### Returns
`MessageAPI`
## Properties
### apiInstance
> `readonly` **apiInstance** : `API`
Defined in: jsEngine/api/MessageAPI.ts:8
### messageManager
> `readonly` **messageManager** : `MessageManager`
Defined in: jsEngine/api/MessageAPI.ts:9
## Methods
### createMessage()
> **createMessage**(`type`, `title`, `content`, `code`): `MessageWrapper`
Defined in: jsEngine/api/MessageAPI.ts:16
#### Parameters
Parameter | Type | Default value  
---|---|---  
`type` |  `MessageType` |  `undefined`  
`title` |  `string` |  `undefined`  
`content` |  `string` |  `undefined`  
`code` |  `string` |  `''`  
#### Returns
`MessageWrapper`
### getMessageById()
> **getMessageById**(`id`): `undefined` | `MessageWrapper`
Defined in: jsEngine/api/MessageAPI.ts:27
#### Parameters
Parameter | Type  
---|---  
`id` |  `string`  
#### Returns
`undefined` | `MessageWrapper`
### getMessagesForInstance()
> **getMessagesForInstance**(): `MessageWrapper`[]
Defined in: jsEngine/api/MessageAPI.ts:33
#### Returns
`MessageWrapper`[]


================================================================================

## 18. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/markdownbuilder

Skip to content
# MarkdownBuilder
Defined in: jsEngine/api/markdown/MarkdownBuilder.ts:8
Allows for easily building markdown using JavaScript.
## Extends
  * `AbstractMarkdownElementContainer`


## Constructors
### new MarkdownBuilder()
> **new MarkdownBuilder**(`apiInstance`): `MarkdownBuilder`
Defined in: jsEngine/api/markdown/MarkdownBuilder.ts:9
#### Parameters
Parameter | Type  
---|---  
`apiInstance` |   
#### Returns
`MarkdownBuilder`
#### Overrides
`AbstractMarkdownElementContainer.constructor`
## Properties
### apiInstance
> `readonly` **apiInstance** : `API`
Defined in: jsEngine/api/markdown/AbstractMarkdownElement.ts:9
#### Inherited from
`AbstractMarkdownElementContainer.apiInstance`
### markdownElements
> **markdownElements** : `AbstractMarkdownElement`[]
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:12
#### Inherited from
`AbstractMarkdownElementContainer.markdownElements`
## Methods
### addBoldText()
> **addBoldText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:53
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addBoldText`
### addCode()
> **addCode**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:85
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addCode`
### addCursiveText()
> **addCursiveText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:61
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addCursiveText`
### addElement()
> **addElement**(`element`): `void`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:35
Adds a child element to the container.
#### Parameters
Parameter | Type | Description  
---|---|---  
`element` |  `AbstractMarkdownElement`  
#### Returns
`void`
#### Throws
Error if the element is not allowed in the container.
#### Inherited from
`AbstractMarkdownElementContainer.addElement`
### addHighlightedText()
> **addHighlightedText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:77
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addHighlightedText`
### addText()
> **addText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:45
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addText`
### addUnderlinedText()
> **addUnderlinedText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:69
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addUnderlinedText`
### createBlockQuote()
> **createBlockQuote**(): `BlockQuoteElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:109
#### Returns
`BlockQuoteElement`
#### Inherited from
`AbstractMarkdownElementContainer.createBlockQuote`
### createCallout()
> **createCallout**(`title`, `type`, `args`): `CalloutElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:115
#### Parameters
Parameter | Type | Default value  
---|---|---  
`title` |  `string` |  `undefined`  
`type` |  `string` |  `undefined`  
`args` |  `string` |  `''`  
#### Returns
`CalloutElement`
#### Inherited from
`AbstractMarkdownElementContainer.createCallout`
### createCodeBlock()
> **createCodeBlock**(`language`, `content`): `CodeBlockElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:131
#### Parameters
Parameter | Type  
---|---  
`language` |  `string`  
`content` |  `string`  
#### Returns
`CodeBlockElement`
#### Inherited from
`AbstractMarkdownElementContainer.createCodeBlock`
### createCollapsibleCallout()
> **createCollapsibleCallout**(`title`, `type`, `args`, `collapsed`): `CalloutElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:123
#### Parameters
Parameter | Type | Default value  
---|---|---  
`title` |  `string` |  `undefined`  
`type` |  `string` |  `undefined`  
`args` |  `string` |  `''`  
`collapsed` |  `boolean` |  `false`  
#### Returns
`CalloutElement`
#### Inherited from
`AbstractMarkdownElementContainer.createCollapsibleCallout`
### createHeading()
> **createHeading**(`level`, `content`): `HeadingElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:101
#### Parameters
Parameter | Type  
---|---  
`level` |  `number`  
`content` |  `string`  
#### Returns
`HeadingElement`
#### Inherited from
`AbstractMarkdownElementContainer.createHeading`
### createList()
> **createList**(`ordered`): `ListElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:147
#### Parameters
Parameter | Type | Default value  
---|---|---  
`ordered` |  `boolean` |  `false`  
#### Returns
`ListElement`
#### Inherited from
`AbstractMarkdownElementContainer.createList`
### createOrderedList()
> **createOrderedList**(): `ListElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:155
#### Returns
`ListElement`
#### Inherited from
`AbstractMarkdownElementContainer.createOrderedList`
### createParagraph()
> **createParagraph**(`content`): `ParagraphElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:93
#### Parameters
Parameter | Type  
---|---  
`content` |  `string`  
#### Returns
`ParagraphElement`
#### Inherited from
`AbstractMarkdownElementContainer.createParagraph`
### createTable()
> **createTable**(`header`, `body`): `TableElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:139
#### Parameters
Parameter | Type  
---|---  
`header` |  `string`[]  
`body` |  `TableElementType`[][]  
#### Returns
`TableElement`
#### Inherited from
`AbstractMarkdownElementContainer.createTable`
### toMarkdown()
> **toMarkdown**(): `MarkdownString`
Defined in: jsEngine/api/markdown/AbstractMarkdownElement.ts:28
Converts the element to a MarkdownString.
#### Returns
`MarkdownString`
#### Inherited from
`AbstractMarkdownElementContainer.toMarkdown`
### toString()
> **toString**(): `string`
Defined in: jsEngine/api/markdown/MarkdownBuilder.ts:13
Converts the element to a string.
#### Returns
`string`
#### Overrides
`AbstractMarkdownElementContainer.toString`


================================================================================

## 19. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/paragraphelement

Skip to content
# ParagraphElement
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:341
Represents a markdown paragraph.
## Extends
  * `AbstractMarkdownElementContainer`


## Constructors
### new ParagraphElement()
> **new ParagraphElement**(`apiInstance`, `content`): `ParagraphElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:342
#### Parameters
Parameter | Type  
---|---  
`apiInstance` |   
`content` |  `string`  
#### Returns
`ParagraphElement`
#### Overrides
`AbstractMarkdownElementContainer.constructor`
## Properties
### apiInstance
> `readonly` **apiInstance** : `API`
Defined in: jsEngine/api/markdown/AbstractMarkdownElement.ts:9
#### Inherited from
`AbstractMarkdownElementContainer.apiInstance`
### markdownElements
> **markdownElements** : `AbstractMarkdownElement`[]
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:12
#### Inherited from
`AbstractMarkdownElementContainer.markdownElements`
## Methods
### addBoldText()
> **addBoldText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:53
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addBoldText`
### addCode()
> **addCode**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:85
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addCode`
### addCursiveText()
> **addCursiveText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:61
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addCursiveText`
### addElement()
> **addElement**(`element`): `void`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:35
Adds a child element to the container.
#### Parameters
Parameter | Type | Description  
---|---|---  
`element` |  `AbstractMarkdownElement`  
#### Returns
`void`
#### Throws
Error if the element is not allowed in the container.
#### Inherited from
`AbstractMarkdownElementContainer.addElement`
### addHighlightedText()
> **addHighlightedText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:77
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addHighlightedText`
### addText()
> **addText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:45
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addText`
### addUnderlinedText()
> **addUnderlinedText**(`text`): `AbstractMarkdownElementContainer`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:69
#### Parameters
Parameter | Type  
---|---  
`text` |  `string`  
#### Returns
`AbstractMarkdownElementContainer`
#### Inherited from
`AbstractMarkdownElementContainer.addUnderlinedText`
### createBlockQuote()
> **createBlockQuote**(): `BlockQuoteElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:109
#### Returns
`BlockQuoteElement`
#### Inherited from
`AbstractMarkdownElementContainer.createBlockQuote`
### createCallout()
> **createCallout**(`title`, `type`, `args`): `CalloutElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:115
#### Parameters
Parameter | Type | Default value  
---|---|---  
`title` |  `string` |  `undefined`  
`type` |  `string` |  `undefined`  
`args` |  `string` |  `''`  
#### Returns
`CalloutElement`
#### Inherited from
`AbstractMarkdownElementContainer.createCallout`
### createCodeBlock()
> **createCodeBlock**(`language`, `content`): `CodeBlockElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:131
#### Parameters
Parameter | Type  
---|---  
`language` |  `string`  
`content` |  `string`  
#### Returns
`CodeBlockElement`
#### Inherited from
`AbstractMarkdownElementContainer.createCodeBlock`
### createCollapsibleCallout()
> **createCollapsibleCallout**(`title`, `type`, `args`, `collapsed`): `CalloutElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:123
#### Parameters
Parameter | Type | Default value  
---|---|---  
`title` |  `string` |  `undefined`  
`type` |  `string` |  `undefined`  
`args` |  `string` |  `''`  
`collapsed` |  `boolean` |  `false`  
#### Returns
`CalloutElement`
#### Inherited from
`AbstractMarkdownElementContainer.createCollapsibleCallout`
### createHeading()
> **createHeading**(`level`, `content`): `HeadingElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:101
#### Parameters
Parameter | Type  
---|---  
`level` |  `number`  
`content` |  `string`  
#### Returns
`HeadingElement`
#### Inherited from
`AbstractMarkdownElementContainer.createHeading`
### createList()
> **createList**(`ordered`): `ListElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:147
#### Parameters
Parameter | Type | Default value  
---|---|---  
`ordered` |  `boolean` |  `false`  
#### Returns
`ListElement`
#### Inherited from
`AbstractMarkdownElementContainer.createList`
### createOrderedList()
> **createOrderedList**(): `ListElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:155
#### Returns
`ListElement`
#### Inherited from
`AbstractMarkdownElementContainer.createOrderedList`
### createParagraph()
> **createParagraph**(`content`): `ParagraphElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:93
#### Parameters
Parameter | Type  
---|---  
`content` |  `string`  
#### Returns
`ParagraphElement`
#### Inherited from
`AbstractMarkdownElementContainer.createParagraph`
### createTable()
> **createTable**(`header`, `body`): `TableElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:139
#### Parameters
Parameter | Type  
---|---  
`header` |  `string`[]  
`body` |  `TableElementType`[][]  
#### Returns
`TableElement`
#### Inherited from
`AbstractMarkdownElementContainer.createTable`
### toMarkdown()
> **toMarkdown**(): `MarkdownString`
Defined in: jsEngine/api/markdown/AbstractMarkdownElement.ts:28
Converts the element to a MarkdownString.
#### Returns
`MarkdownString`
#### Inherited from
`AbstractMarkdownElementContainer.toMarkdown`
### toString()
> **toString**(): `string`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:348
Converts the element to a string.
#### Returns
`string`
#### Overrides
`AbstractMarkdownElementContainer.toString`


================================================================================

## 20. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/promptapi

Skip to content
# PromptAPI
Defined in: jsEngine/api/PromptAPI.ts:98
## Constructors
### new PromptAPI()
> **new PromptAPI**(`apiInstance`): `PromptAPI`
Defined in: jsEngine/api/PromptAPI.ts:101
#### Parameters
Parameter | Type  
---|---  
`apiInstance` |   
#### Returns
`PromptAPI`
## Properties
### apiInstance
> `readonly` **apiInstance** : `API`
Defined in: jsEngine/api/PromptAPI.ts:99
## Methods
### button()
> **button** <`T`>(`options`): `Promise`<`undefined` | `T`>
Defined in: jsEngine/api/PromptAPI.ts:132
Prompts the user with a modal containing a list of buttons. Returns the value of the button that was clicked, or undefined if the modal was closed.
#### Type Parameters
Type Parameter  
---  
#### Parameters
Parameter | Type  
---|---  
`options` |  `ButtonPromptOptions`<`T`>  
#### Returns
`Promise`<`undefined` | `T`>
#### Example
```

// Prompt the user with a true/false question.
constret=await engine.prompt.button({
title:'The set of natural numbers with zero and the addition operation is a monoid.',
buttons: 
label:'True',
value:true,
},
label:'False',
value:false,
},
label:'Cancel',
value:undefined,
});

```

### confirm()
> **confirm**(`options`): [`Promise`<`boolean`>
Defined in: jsEngine/api/PromptAPI.ts:171
Prompts the user with a confirm/cancel dialog. Returns true if the user confirms, false if the user cancels or otherwise closes the modal.
#### Parameters
Parameter | Type  
---|---  
`options` |  `ConfirmPromptOptions`  
#### Returns
`Promise`<`boolean`>
#### Example
```

// Ask the user if they want to confirm an action.
constret=await engine.prompt.confirm({
title:'Confirm File Deletion',
content:'Are you sure you want to delete this file? This action cannot be undone.',
});

```

### number()
> **number**(`options`): `Promise`<`undefined` | `number`>
Defined in: jsEngine/api/PromptAPI.ts:362
Prompts the user with a number input dialog. Returns the value of the input field, or undefined if the user closes the modal. While the input field is focused, the user can use `enter` to submit the value and `esc` to cancel and close the modal.
#### Parameters
Parameter | Type  
---|---  
`options` |  `NumberInputPromptOptions`  
#### Returns
`Promise`<`undefined` | `number`>
#### Example
```

// Prompt the user to input their age.
constret=await engine.prompt.text({
title:'Please enter your age',
content:'Please enter your age in years in the field below.',
});

```

### suggester()
> **suggester** <`T`>(`options`): `Promise`<`undefined` | `T`>
Defined in: jsEngine/api/PromptAPI.ts:248
Prompts the user with a fuzzy finder suggester dialog. Returns the value of the selected option, or undefined if the user closes the modal.
#### Type Parameters
Type Parameter  
---  
#### Parameters
Parameter | Type  
---|---  
`options` |  `SuggesterPromptOptions`<`T`>  
#### Returns
`Promise`<`undefined` | `T`>
#### Example
```

// Query a list of files and prompt the user to select one.
constfiles= engine.query.files((file) => {
return {
label: file.name,
value: file.pat,
};
});
constret=await engine.prompt.suggester({
placeholder:'Select a file',
options: files,
});

```

### text()
> **text**(`options`): `Promise`<`undefined` | `string`>
Defined in: jsEngine/api/PromptAPI.ts:275
Prompts the user with a text input dialog. Returns the value of the input field, or undefined if the user closes the modal. While the input field is focused, the user can use `enter` to submit the value and `esc` to cancel and close the modal.
#### Parameters
Parameter | Type  
---|---  
`options` |  `InputPromptOptions`  
#### Returns
`Promise`<`undefined` | `string`>
#### Example
```

// Prompt the user to input their name.
constret=await engine.prompt.text({
title:'Please enter your name',
content:'Please enter your name in the field below.',
});

```

### textarea()
> **textarea**(`options`): `Promise`<`undefined` | `string`>
Defined in: jsEngine/api/PromptAPI.ts:319
Prompts the user with a textarea input dialog. Returns the value of the input field, or undefined if the user closes the modal. While the input field is focused, the user can use `esc` to cancel and close the modal.
#### Parameters
Parameter | Type  
---|---  
`options` |  `InputPromptOptions`  
#### Returns
`Promise`<`undefined` | `string`>
#### Example
```

// Prompt the user to input a multi-line message.
constret=await engine.prompt.textarea({
title:'Please enter your message',
content:'Please enter your message in the field below.',
placeholder:'Your message here...',
});

```

### yesNo()
> **yesNo**(`options`): `Promise`<`undefined` | `boolean`>
Defined in: jsEngine/api/PromptAPI.ts:207
Prompts the user with a yes/no dialog. Returns true if the user selects yes, false if the user selects no, and undefined if the user otherwise closes the modal.
#### Parameters
Parameter | Type  
---|---  
`options` |  `YesNoPromptOptions`  
#### Returns
`Promise`<`undefined` | `boolean`>
#### Example
```

// Ask the user if they like Obsidian.
constret=await engine.prompt.yesNo({
title:'Is this a test?',
content:'Are you sure this is a test? Are you sure that your choice is really meaningless?',
});

```



================================================================================

## 21. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/interfaces/engineexecutionparams

Skip to content
# EngineExecutionParams
Defined in: jsEngine/engine/Engine.ts:10
Parameters for the Engine.execute method.
## Extended by
  * `JsExecutionParams`


## Properties
### code
> **code** : `string`
Defined in: jsEngine/engine/Engine.ts:14
The JavaScript code to execute.
### component
> **component** : `Component`
Defined in: jsEngine/engine/Engine.ts:18
Obsidian Component for lifecycle management.
### container?
> `optional` **container** : `HTMLElement`
Defined in: jsEngine/engine/Engine.ts:22
Optional container element to render results to.
### context
> **context** : `ExecutionContext`
Defined in: jsEngine/engine/Engine.ts:26
Context about the location the code was executed from.
### contextOverrides?
> `optional` **contextOverrides** : `Record`<`string`, `unknown`>
Defined in: jsEngine/engine/Engine.ts:30
Optional extra context variables to provide to the JavaScript code.


================================================================================

## 22. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/textelement

Skip to content
# TextElement
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:169
Represents a piece of pure markdown text.
## Extends
  * `AbstractMarkdownLiteral`


## Constructors
### new TextElement()
> **new TextElement**(`apiInstance`, `content`, `bold`, `cursive`, `underline`, `highlight`): `TextElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:176
#### Parameters
Parameter | Type  
---|---  
`apiInstance` |   
`content` |  `string`  
`bold` |  `boolean`  
`cursive` |  `boolean`  
`underline` |  `boolean`  
`highlight` |  `boolean`  
#### Returns
`TextElement`
#### Overrides
`AbstractMarkdownLiteral.constructor`
## Properties
### apiInstance
> `readonly` **apiInstance** : `API`
Defined in: jsEngine/api/markdown/AbstractMarkdownElement.ts:9
#### Inherited from
`AbstractMarkdownLiteral.apiInstance`
### bold
> **bold** : `boolean`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:171
### content
> **content** : `string`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:170
### cursive
> **cursive** : `boolean`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:172
### highlight
> **highlight** : `boolean`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:174
### underline
> **underline** : `boolean`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:173
## Methods
### toMarkdown()
> **toMarkdown**(): `MarkdownString`
Defined in: jsEngine/api/markdown/AbstractMarkdownElement.ts:28
Converts the element to a MarkdownString.
#### Returns
`MarkdownString`
#### Inherited from
`AbstractMarkdownLiteral.toMarkdown`
### toString()
> **toString**(): `string`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:186
Converts the element to a string.
#### Returns
`string`
#### Overrides
`AbstractMarkdownLiteral.toString`


================================================================================

## 23. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/interfaces/buttonpromptoptions

Skip to content
# ButtonPromptOptions
Defined in: jsEngine/api/PromptAPI.ts:27
Basic options for a prompt modal. This interface is used as a base for other prompt options.
## Extends
  * `ModalPromptOptions`


## Type Parameters
Type Parameter  
---  
## Properties
### buttons
> **buttons** : `ButtonPromptButtonOptions`<`T`>[]
Defined in: jsEngine/api/PromptAPI.ts:35
A list of buttons to display in the modal.
### classes?
> `optional` **classes** : `string`[]
Defined in: jsEngine/api/PromptAPI.ts:24
A list of CSS classes to apply to the modal.
#### Inherited from
`ModalPromptOptions`.`classes`
### content?
> `optional` **content** : `string`
Defined in: jsEngine/api/PromptAPI.ts:31
Text content to display in the modal.
### title
> **title** : `string`
Defined in: jsEngine/api/PromptAPI.ts:20
The title of the modal.
#### Inherited from
`ModalPromptOptions`.`title`


================================================================================

## 24. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/interfaces/buttonpromptbuttonoptions

Skip to content
# ButtonPromptButtonOptions
Defined in: jsEngine/api/PromptAPI.ts:38
## Type Parameters
Type Parameter  
---  
## Properties
### label
> **label** : `string`
Defined in: jsEngine/api/PromptAPI.ts:39
### value
> **value** : `T`
Defined in: jsEngine/api/PromptAPI.ts:40
### variant?
> `optional` **variant** : `ButtonStyleType`
Defined in: jsEngine/api/PromptAPI.ts:41


================================================================================

## 25. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/tableelement

Skip to content
# TableElement
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:236
Represents a markdown table.
## Extends
  * `AbstractMarkdownLiteral`


## Constructors
### new TableElement()
> **new TableElement**(`apiInstance`, `header`, `body`): `TableElement`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:240
#### Parameters
Parameter | Type  
---|---  
`apiInstance` |   
`header` |  `string`[]  
`body` |  `TableElementType`[][]  
#### Returns
`TableElement`
#### Overrides
`AbstractMarkdownLiteral.constructor`
## Properties
### apiInstance
> `readonly` **apiInstance** : `API`
Defined in: jsEngine/api/markdown/AbstractMarkdownElement.ts:9
#### Inherited from
`AbstractMarkdownLiteral.apiInstance`
### body
> **body** : `string`[][]
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:238
### header
> **header** : `string`[]
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:237
## Methods
### toMarkdown()
> **toMarkdown**(): `MarkdownString`
Defined in: jsEngine/api/markdown/AbstractMarkdownElement.ts:28
Converts the element to a MarkdownString.
#### Returns
`MarkdownString`
#### Inherited from
`AbstractMarkdownLiteral.toMarkdown`
### toString()
> **toString**(): `string`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:247
Converts the element to a string.
#### Returns
`string`
#### Overrides
`AbstractMarkdownLiteral.toString`


================================================================================

## 26. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/reactivecomponent

Skip to content
# ReactiveComponent
Defined in: jsEngine/api/reactive/ReactiveComponent.ts:12
A reactive component is a component that can be refreshed. This is useful for rendering dynamic content.
See API.reactive
## Constructors
### new ReactiveComponent()
> **new ReactiveComponent**(`api`, `_render`, `initialArgs`): `ReactiveComponent`
Defined in: jsEngine/api/reactive/ReactiveComponent.ts:21
#### Parameters
Parameter | Type  
---|---  
`api` |   
`_render` |  `JsFunc`  
`initialArgs` |  `unknown`[]  
#### Returns
`ReactiveComponent`
## Methods
### refresh()
> **refresh**(…`args`): `Promise`<`void`>
Defined in: jsEngine/api/reactive/ReactiveComponent.ts:32
Refreshes the component by rerunning the render function with the arguments passed into this function.
#### Parameters
Parameter | Type | Description  
---|---|---  
…`args` |  `unknown`[]  
#### Returns
`Promise`<`void`>


================================================================================

## 27. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/interfaces/jsexecutionglobals

Skip to content
# JsExecutionGlobals
Defined in: jsEngine/engine/JsExecution.ts:104
Global variables provided to a JsExecution.
## Properties
### app
> **app** : `App`
Defined in: jsEngine/engine/JsExecution.ts:108
Reference to the obsidian app (obsidian API).
### component
> **component** : `Component`
Defined in: jsEngine/engine/JsExecution.ts:116
Obsidian component for lifecycle management.
### container
> **container** : `undefined` | `HTMLElement`
Defined in: jsEngine/engine/JsExecution.ts:124
The container element that the execution can render to. This can be undefined.
### context
> **context** : `ExecutionContext` & `Record`<`string`, `unknown`>
Defined in: jsEngine/engine/JsExecution.ts:120
The context provided. This can be undefined and extended by other properties.
### engine
> **engine** : `API`
Defined in: jsEngine/engine/JsExecution.ts:112
Reference to this plugins API.
### obsidian
> **obsidian** : `__module`
Defined in: jsEngine/engine/JsExecution.ts:128
The entire obsidian module, e.g. a notice can be constructed like this: `new obsidian.Notice('Hello World')`.


================================================================================

## 28. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/enumerations/instancetype

Skip to content  
# InstanceType
Defined in: jsEngine/api/InstanceId.ts:3
## Enumeration Members
Enumeration Member | Value | Defined in  
---|---|---  
`JS_EXECUTION` |  `"JS_EXECUTION"` |  jsEngine/api/InstanceId.ts:4  
`PLUGIN` |  `"PLUGIN"` |  jsEngine/api/InstanceId.ts:5


================================================================================

## 29. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/interfaces/inputpromptoptions

Skip to content
# InputPromptOptions
Defined in: jsEngine/api/PromptAPI.ts:68
Basic options for a prompt modal. This interface is used as a base for other prompt options.
## Extends
  * `ModalPromptOptions`


## Properties
### classes?
> `optional` **classes** : `string`[]
Defined in: jsEngine/api/PromptAPI.ts:24
A list of CSS classes to apply to the modal.
#### Inherited from
`ModalPromptOptions`.`classes`
### content?
> `optional` **content** : `string`
Defined in: jsEngine/api/PromptAPI.ts:72
Text content to display in the modal.
### initialValue?
> `optional` **initialValue** : `string`
Defined in: jsEngine/api/PromptAPI.ts:80
The initial value of the input field that is pre-filled when the modal is opened.
### placeholder?
> `optional` **placeholder** : `string`
Defined in: jsEngine/api/PromptAPI.ts:76
The placeholder text for the input field. This will show when the input field is empty.
### title
> **title** : `string`
Defined in: jsEngine/api/PromptAPI.ts:20
The title of the modal.
#### Inherited from
`ModalPromptOptions`.`title`


================================================================================

## 30. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/interfaces/block

Skip to content
# Block
Defined in: jsEngine/engine/JsExecution.ts:40
## Properties
### from
> **from** : `number`
Defined in: jsEngine/engine/JsExecution.ts:41
### to
> **to** : `number`
Defined in: jsEngine/engine/JsExecution.ts:42


================================================================================

## 31. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/interfaces/confirmpromptoptions

Skip to content
# ConfirmPromptOptions
Defined in: jsEngine/api/PromptAPI.ts:44
Basic options for a prompt modal. This interface is used as a base for other prompt options.
## Extends
  * `ModalPromptOptions`


## Properties
### classes?
> `optional` **classes** : `string`[]
Defined in: jsEngine/api/PromptAPI.ts:24
A list of CSS classes to apply to the modal.
#### Inherited from
`ModalPromptOptions`.`classes`
### content?
> `optional` **content** : `string`
Defined in: jsEngine/api/PromptAPI.ts:48
Text content to display in the modal.
### title
> **title** : `string`
Defined in: jsEngine/api/PromptAPI.ts:20
The title of the modal.
#### Inherited from
`ModalPromptOptions`.`title`


================================================================================

## 32. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/classes/resultrenderer

Skip to content
# ResultRenderer
Defined in: jsEngine/engine/ResultRenderer.ts:14
Attaches to a container and renders values. Used to render the result of a JsExecution.
## Constructors
### new ResultRenderer()
> **new ResultRenderer**(`plugin`, `container`, `sourcePath`, `component`): `ResultRenderer`
Defined in: jsEngine/engine/ResultRenderer.ts:20
#### Parameters
Parameter | Type  
---|---  
`plugin` |  `JsEnginePlugin`  
`container` |  `HTMLElement`  
`sourcePath` |  `string`  
`component` |  `Component`  
#### Returns
`ResultRenderer`
## Properties
### component
> `readonly` **component** : `Component`
Defined in: jsEngine/engine/ResultRenderer.ts:18
### container
> `readonly` **container** : `HTMLElement`
Defined in: jsEngine/engine/ResultRenderer.ts:16
### plugin
> `readonly` **plugin** : `JsEnginePlugin`
Defined in: jsEngine/engine/ResultRenderer.ts:15
### sourcePath
> `readonly` **sourcePath** : `string`
Defined in: jsEngine/engine/ResultRenderer.ts:17
## Methods
### convertToSimpleObject()
> **convertToSimpleObject**(`value`): `unknown`
Defined in: jsEngine/engine/ResultRenderer.ts:92
Converts the given value to a simple object. E.g. a MarkdownBuilder will be converted to a string.
#### Parameters
Parameter | Type | Description  
---|---|---  
`value` |  `unknown` |  The value to convert.  
#### Returns
`unknown`
The simple object.
### render()
> **render**(`value`): `Promise`<`void`>
Defined in: jsEngine/engine/ResultRenderer.ts:32
Renders the given value to the container.
#### Parameters
Parameter | Type | Description  
---|---|---  
`value` |  `unknown` |  The value to render.  
#### Returns
`Promise`<`void`>


================================================================================

## 33. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/enumerations/executionsource

Skip to content  
# ExecutionSource
Defined in: jsEngine/engine/JsExecution.ts:15
## Enumeration Members
Enumeration Member | Value | Defined in  
---|---|---  
`JSFile` |  `"js-file"` |  jsEngine/engine/JsExecution.ts:19  
`MarkdownCallingJSFile` |  `"markdown-calling-js-file"` |  jsEngine/engine/JsExecution.ts:17  
`MarkdownCodeBlock` |  `"markdown-code-block"` |  jsEngine/engine/JsExecution.ts:16  
`MarkdownOther` |  `"markdown-other"` |  jsEngine/engine/JsExecution.ts:18  
`Unknown` |  `"unknown"` |  jsEngine/engine/JsExecution.ts:20


================================================================================

## 34. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/interfaces/jsexecutionglobalsconstructionoptions

Skip to content
# JsExecutionGlobalsConstructionOptions
Defined in: jsEngine/engine/JsExecution.ts:134
Interface for constructing JsExecutionGlobals.
## Properties
### component
> **component** : `Component`
Defined in: jsEngine/engine/JsExecution.ts:143
Obsidian component for lifecycle management.
### container?
> `optional` **container** : `HTMLElement`
Defined in: jsEngine/engine/JsExecution.ts:151
The container element that the execution can render to. This can be undefined.
### context
> **context** : `ExecutionContext` & `Record`<`string`, `unknown`>
Defined in: jsEngine/engine/JsExecution.ts:147
The context provided. This can be undefined and extended by other properties.
### engine?
> `optional` **engine** : `API`
Defined in: jsEngine/engine/JsExecution.ts:139
Optional API instance. If not provided, the one from which the execution globals are constructed is used.


================================================================================

## 35. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/interfaces/libparsinom

Skip to content
# LibParsiNOM
Defined in: jsEngine/api/LibAPI.ts:9
## Properties
### createParsingErrorMessage()
> **createParsingErrorMessage** : (`str`, `parseFailure`, `verbose`) => `string`
Defined in: jsEngine/api/LibAPI.ts:13
Generate an error message string for a parse failure on a specific string.
#### Parameters
Parameter | Type | Description  
---|---|---  
`str` |  `string` |  the input string that the parse failure occurred on  
`parseFailure` |  `ParseFailure` |  the failure to generate the error message for  
`verbose` |  `boolean` |  will underline the failure position in the input string, if set to true  
#### Returns
`string`
### P
> **P** : _typeof_ `P`
Defined in: jsEngine/api/LibAPI.ts:10
### P_UTILS
> **P_UTILS** : _typeof_ `P_UTILS`
Defined in: jsEngine/api/LibAPI.ts:11
### Parser
> **Parser** : _typeof_ `Parser`
Defined in: jsEngine/api/LibAPI.ts:12
### ParserContext
> **ParserContext** : _typeof_ `ParserContext`
Defined in: jsEngine/api/LibAPI.ts:15
### ParsingError
> **ParsingError** : _typeof_ `ParsingError`
Defined in: jsEngine/api/LibAPI.ts:14


================================================================================

## 36. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/interfaces/markdownotherexecutioncontext

Skip to content
# MarkdownOtherExecutionContext
Defined in: jsEngine/engine/JsExecution.ts:62
## Properties
### executionSource
> **executionSource** : `MarkdownOther`
Defined in: jsEngine/engine/JsExecution.ts:63
### file?
> `optional` **file** : `TFile`
Defined in: jsEngine/engine/JsExecution.ts:68
The file that the markdown is associated with. Since rendered markdown does not necessarily have an associated file, this can be undefined.
### metadata?
> `optional` **metadata** : `CachedMetadata`
Defined in: jsEngine/engine/JsExecution.ts:72
The metadata of the file.


================================================================================

## 37. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/interfaces/markdowncallingjsfileexecutioncontext

Skip to content
# MarkdownCallingJSFileExecutionContext
Defined in: jsEngine/engine/JsExecution.ts:45
## Properties
### executionSource
> **executionSource** : `MarkdownCallingJSFile`
Defined in: jsEngine/engine/JsExecution.ts:46
### file?
> `optional` **file** : `TFile`
Defined in: jsEngine/engine/JsExecution.ts:51
The markdown file that the JS File is called from. Since rendered markdown does not necessarily have an associated file, this can be undefined.
### jsFile
> **jsFile** : `TFile`
Defined in: jsEngine/engine/JsExecution.ts:59
The JS that is being called.
### metadata?
> `optional` **metadata** : `CachedMetadata`
Defined in: jsEngine/engine/JsExecution.ts:55
The metadata of the markdown file.


================================================================================

## 38. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/interfaces/markdowncodeblockexecutioncontext

Skip to content
# MarkdownCodeBlockExecutionContext
Defined in: jsEngine/engine/JsExecution.ts:23
## Properties
### block?
> `optional` **block** : `Block`
Defined in: jsEngine/engine/JsExecution.ts:37
Currently unused.
### executionSource
> **executionSource** : `MarkdownCodeBlock`
Defined in: jsEngine/engine/JsExecution.ts:24
### file?
> `optional` **file** : `TFile`
Defined in: jsEngine/engine/JsExecution.ts:29
The file that the code block is in. Since rendered markdown does not necessarily have an associated file, this can be undefined.
### metadata?
> `optional` **metadata** : `CachedMetadata`
Defined in: jsEngine/engine/JsExecution.ts:33
The metadata of the file.


================================================================================

## 39. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/interfaces/jsfileexecutioncontext

Skip to content
# JSFileExecutionContext
Defined in: jsEngine/engine/JsExecution.ts:75
## Properties
### executionSource
> **executionSource** : `JSFile`
Defined in: jsEngine/engine/JsExecution.ts:76
### jsFile
> **jsFile** : `TFile`
Defined in: jsEngine/engine/JsExecution.ts:80
The JS that is being executed.


================================================================================

## 40. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/interfaces/jsexecutionparams

Skip to content
# JsExecutionParams
Defined in: jsEngine/engine/JsExecution.ts:157
Parameters used to construct a JsExecution.
## Extends
  * `EngineExecutionParams`


## Properties
### app
> **app** : `App`
Defined in: jsEngine/engine/JsExecution.ts:158
### code
> **code** : `string`
Defined in: jsEngine/engine/Engine.ts:14
The JavaScript code to execute.
#### Inherited from
`EngineExecutionParams`.`code`
### component
> **component** : `Component`
Defined in: jsEngine/engine/Engine.ts:18
Obsidian Component for lifecycle management.
#### Inherited from
`EngineExecutionParams`.`component`
### container?
> `optional` **container** : `HTMLElement`
Defined in: jsEngine/engine/Engine.ts:22
Optional container element to render results to.
#### Inherited from
`EngineExecutionParams`.`container`
### context
> **context** : `ExecutionContext`
Defined in: jsEngine/engine/Engine.ts:26
Context about the location the code was executed from.
#### Inherited from
`EngineExecutionParams`.`context`
### contextOverrides?
> `optional` **contextOverrides** : `Record`<`string`, `unknown`>
Defined in: jsEngine/engine/Engine.ts:30
Optional extra context variables to provide to the JavaScript code.
#### Inherited from
`EngineExecutionParams`.`contextOverrides`
### plugin
> **plugin** : `JsEnginePlugin`
Defined in: jsEngine/engine/JsExecution.ts:159


================================================================================

## 41. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/interfaces/suggesterpromptoptions

Skip to content
# SuggesterPromptOptions
Defined in: jsEngine/api/PromptAPI.ts:58
## Type Parameters
Type Parameter  
---  
## Properties
### options
> **options** : `SuggesterOption`<`T`>[]
Defined in: jsEngine/api/PromptAPI.ts:60
### placeholder?
> `optional` **placeholder** : `string`
Defined in: jsEngine/api/PromptAPI.ts:59


================================================================================

## 42. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/interfaces/suggesteroption

Skip to content
# SuggesterOption
Defined in: jsEngine/api/PromptAPI.ts:63
## Type Parameters
Type Parameter  
---  
## Properties
### label
> **label** : `string`
Defined in: jsEngine/api/PromptAPI.ts:65
### value
> **value** : `T`
Defined in: jsEngine/api/PromptAPI.ts:64


================================================================================

## 43. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/interfaces/yesnopromptoptions

Skip to content
# YesNoPromptOptions
Defined in: jsEngine/api/PromptAPI.ts:51
Basic options for a prompt modal. This interface is used as a base for other prompt options.
## Extends
  * `ModalPromptOptions`


## Properties
### classes?
> `optional` **classes** : `string`[]
Defined in: jsEngine/api/PromptAPI.ts:24
A list of CSS classes to apply to the modal.
#### Inherited from
`ModalPromptOptions`.`classes`
### content?
> `optional` **content** : `string`
Defined in: jsEngine/api/PromptAPI.ts:55
Text content to display in the modal.
### title
> **title** : `string`
Defined in: jsEngine/api/PromptAPI.ts:20
The title of the modal.
#### Inherited from
`ModalPromptOptions`.`title`


================================================================================

## 44. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/examples/importingjs

Skip to content
# Importing JS
You can import JavaScript files using the `engine.importJs` function.
```

let lib =await engine.importJs('lib.js');
return lib.getGreeting();

```

With a file named `lib.js` in the root of the vault.
```

exportfunctiongetGreeting() {
return'Hello!';

```

> Hello!


================================================================================

## 45. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/interfaces/numberinputpromptoptions

Skip to content
# NumberInputPromptOptions
Defined in: jsEngine/api/PromptAPI.ts:83
Basic options for a prompt modal. This interface is used as a base for other prompt options.
## Extends
  * `ModalPromptOptions`


## Properties
### classes?
> `optional` **classes** : `string`[]
Defined in: jsEngine/api/PromptAPI.ts:24
A list of CSS classes to apply to the modal.
#### Inherited from
`ModalPromptOptions`.`classes`
### content?
> `optional` **content** : `string`
Defined in: jsEngine/api/PromptAPI.ts:87
Text content to display in the modal.
### initialValue?
> `optional` **initialValue** : `number`
Defined in: jsEngine/api/PromptAPI.ts:95
The initial value of the input field that is pre-filled when the modal is opened.
### placeholder?
> `optional` **placeholder** : `string`
Defined in: jsEngine/api/PromptAPI.ts:91
The placeholder text for the input field. This will show when the input field is empty.
### title
> **title** : `string`
Defined in: jsEngine/api/PromptAPI.ts:20
The title of the modal.
#### Inherited from
`ModalPromptOptions`.`title`


================================================================================

## 46. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/type-aliases/executefilesimpleengineexecutionparams

Skip to content  
# ExecuteFileSimpleEngineExecutionParams
> **ExecuteFileSimpleEngineExecutionParams** : `Omit`<`EngineExecutionParams`, `"code"` | `"component"` | `"context"`> & `object`
Defined in: jsEngine/api/Internal.ts:25
## Type declaration
Name| Type| Defined in  
---|---|---  
`context`?| `JSFileExecutionContext` | `MarkdownCallingJSFileExecutionContext`| jsEngine/api/Internal.ts:26


================================================================================

## 47. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/interfaces/modalpromptoptions

Skip to content
# ModalPromptOptions
Defined in: jsEngine/api/PromptAPI.ts:16
Basic options for a prompt modal. This interface is used as a base for other prompt options.
## Extended by
  * `ButtonPromptOptions`
  * `ConfirmPromptOptions`
  * `YesNoPromptOptions`
  * `InputPromptOptions`
  * `NumberInputPromptOptions`


## Properties
### classes?
> `optional` **classes** : `string`[]
Defined in: jsEngine/api/PromptAPI.ts:24
A list of CSS classes to apply to the modal.
### title
> **title** : `string`
Defined in: jsEngine/api/PromptAPI.ts:20
The title of the modal.


================================================================================

## 48. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/type-aliases/executefileengineexecutionparams

Skip to content  
# ExecuteFileEngineExecutionParams
> **ExecuteFileEngineExecutionParams** : `Omit`<`EngineExecutionParams`, `"code"` | `"context"`> & `object`
Defined in: jsEngine/api/Internal.ts:21
## Type declaration
Name| Type| Defined in  
---|---|---  
`context`?| `JSFileExecutionContext` | `MarkdownCallingJSFileExecutionContext`| jsEngine/api/Internal.ts:22


================================================================================

## 49. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/type-aliases/jsfunc

Skip to content
# JsFunc
> **JsFunc** : (…`args`) => `Promise`<`unknown`>
Defined in: jsEngine/engine/JsExecution.ts:13
An async JavaScript function.
## Parameters
Parameter | Type  
---|---  
…`args` |  `unknown`[]  
## Returns
`Promise`<`unknown`>


================================================================================

## 50. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/interfaces/unknownexecutioncontext

Skip to content
# UnknownExecutionContext
Defined in: jsEngine/engine/JsExecution.ts:83
## Properties
### executionSource
> **executionSource** : `Unknown`
Defined in: jsEngine/engine/JsExecution.ts:84
### file?
> `optional` **file** : `TFile`
Defined in: jsEngine/engine/JsExecution.ts:88
The file that the execution was triggered from.


================================================================================

## 51. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/type-aliases/executioncontext

Skip to content
# ExecutionContext
> **ExecutionContext** : `MarkdownCodeBlockExecutionContext` | `MarkdownCallingJSFileExecutionContext` | `MarkdownOtherExecutionContext` | `JSFileExecutionContext` | `UnknownExecutionContext`
Defined in: jsEngine/engine/JsExecution.ts:94
Context provided to a JsExecution.


================================================================================

## 52. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/examples/renderstringsasmarkdown

Skip to content
# Render Strings as Markdown
Normally strings returned from code blocks are rendered as plain text.
```

let str ='*test*';
return str;

```

> *test*
With the `engine.markdown.create` function, you can render strings as markdown.
```

let str ='*test*';
return engine.markdown.create(str);

```

> _test_


================================================================================

## 53. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/api/type-aliases/tableelementtype

Skip to content
# TableElementType
> **TableElementType** : `string` | `number` | `boolean` | `null` | `undefined`
Defined in: jsEngine/api/markdown/AbstractMarkdownElementContainer.ts:231


================================================================================

## 54. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/examples/markdownbuilder

Skip to content
# Markdown Builder
The Markdown Builder allows for easy creation of markdown with JavaScript.
```

let markdownBuilder = engine.markdown.createBuilder();
markdownBuilder.createHeading(2, 'Test Heading');
markdownBuilder.createParagraph('This is a test paragraph.');
markdownBuilder.createHeading(3, 'This is a sub heading');
markdownBuilder.createHeading(4, 'This is a sub sub heading');
markdownBuilder.createParagraph('This is another test paragraph.');
return markdownBuilder;

```

> ## Test Heading
> This is a test paragraph.
> ### This is a sub heading
> #### This is a sub sub heading
> This is another test paragraph.


================================================================================

## 55. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/guides/usage

Skip to content
# Usage
Start by creating a code block with `js-engine` as the code block language. Inside the code block you can write what ever JavaScript code that you want. The plugin will run the JavaScript and render the returned value in place of the code block.
```

## This is a Note in Obsidian
```js-engine
return engine.markdown.create('*test*');
```

```

The following example will render a simple plain text string.
```

let str ='*test*';
return str;

```

> *test*
We can use the `engine.markdown.create` function to render the string as markdown.
```

let str ='*test*';
return engine.markdown.create(str);

```

> _test_
When you return nothing or `undefined`, the plugin will not render anything and the code block will be invisible.


================================================================================

## 56. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/examples/renderinglatex

Skip to content
# Rendering LaTeX
You can render LaTeX using the `engine.markdown.create` function. You just have to keep in mind that you need to surround everything with `$` and escape the backslash character.
```

let str ='$$\\frac{1}{2}$$';
return engine.markdown.create(str);

```



================================================================================

## 57. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/guides/startupscripts

Skip to content
# Startup-Scripts
JS-Engine supports startup-scripts, similar to the CSS-snippets from Core-Obsidian.
You can select the script-file you want to use as startup-scripts and JS-Engine will run them for you when never Obsidian starts up.
## Configuring Startup-Scripts
You can configure which files you want to have run from JS-Engines settings tab.
## Global Variables
JS-Engine runs the scripts in the same context as all other code-blocks. So the available global variable are the same and can be found here.


================================================================================

## 58. https://www.moritzjung.dev/obsidian-js-engine-plugin-docs/guides/api

Skip to content
# API Guide
## Global Variables
The global variables available in code blocks can be found here.
## API
JS Engine provides an API that can be used to do a lot of useful things. Documentation for the API can be found here.


================================================================================
