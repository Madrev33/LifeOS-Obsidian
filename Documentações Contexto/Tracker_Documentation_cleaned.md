
================================================
FILE: README.md
================================================
# Obsidian Tracker Plugin

This is an Obsidian plugin that helps you collect data from notes and represent it comprehensively.

Here is a table containing simplified examples showing what you can track.

## What's New

Version 1.16.0

- Adding thresholdType parameter to Calendars
- Enable bar chart full-bar display at beginning and end
- Update dependencies

Version 1.15.1

- Fix: Added DatasetName as title for calendar in annotation mode
- Fix: Resolve scaling issue when navigating between monthly views
- Update dependencies

Version 1.15.0

- Fix: Minor spelling error in Examples.md
- Added new expression functions - First and Last
- Updated dates in examples to fix plots
- Respect thresholds in scaled months
- Update dependencies

Version 1.14.0

- Update dependencies
- Prevent overlapping external labels in pie chart
- Enable Stacked Bar Chart

Version 1.13.3

- Update dependencies
- Fix typo in FinanceTracker.md
- Fix typo in TestExpression.md
- Update main.ts - use new format for {{average}}

Version 1.13.2

- Update dependencies
- Fix typo in README.md
- Change streak counts to terminate on falsey values rather than null

Version 1.13.1

- Fix packaging script

Version 1.13.0

- Add support for inline dataview fields (including emoji support for values)
- Update dependencies

Version 1.12.0

- Add aspect ratio parameter for graphs
- Reorganize release notes in readme to be in descending order (latest release first)

Version 1.11.0

- Add support for checkboxes in new properties added in Obsidian 1.4
- Fix typos in documentation and examples

Version 1.10.9

- Replace tab characters by spaces
- Accept more unicode characters in dvField
- Allow emojis in the folder path
- Fixed bugs

Version 1.10.8

- Fixed startDate/endDate misread as a relative date

Version 1.10.7

- Allow using html image tags as emoji inputs

Version 1.10.6

- Fixed the coloring for missing data in the month view

Version 1.10.5

- Allow using a relative date value in `initMonth` in the month view

Version 1.10.4

- Allow using a regular expression as a key of the parameter `textValueMap`
- Add a parameter `shiftOnlyValueLargerThan` to determine when to do `valueShift`
- Fixed bugs reported by users
- Fixed typo in plugin settings

Version 1.10.3

- Allow using the parameter `fitPanelWidth` with the output type `month` and `pie`
- Fixed the resizing and positioning of the chart tooltip

Version 1.10.2

- Fixed plugin not rendering on some macOS machines

Version 1.10.1

- Fixed 'failed to load plugin' on iOS

Version 1.10.0

- Add annotation mode for month view (examples)
- Add parameters `xAxisTickInterval`, `yAxisTickInterval`, `xAxisTickLabelFormat` and `yAxisTickLabelFormat` for the line and bar chart (examples)
- Allow using regular expression in parameter `dateFormatPrefix` and `dateFormatSuffix` (examples)
- Add parameters `file`, `specifiedFilesOnly`, `fileContainsLinkedFiles`, and `fileMultiplierAfterLink` to retrieve data from specified files (examples)
- Add a parameter `textValueMap` to convert texts or emojis to specified values (examples)
- Fixed bugs
- Enhanced error messages

## !!! Breaking Changes !!!

From version 1.9.0, template variables, e.g. '{{sum}}', are deprecated. Instead, Tracker provide operators (+, -, *, /, %) and functions (dataset(), sum(), maxStreak(), ......etc) to help us do data processing. For users having code blocks from previous version, please replace '{{sum}}' by '{{sum()}}' or '{{sum(1)}}' by '{{sum(dataset(1))}}'. More information about the new expressions could be found here.

## Usage

1. Have some targets you want to track in daily notes.
2. Add a new note for displaying the tracker.
3. Add tracker code blocks manually (examples) or using commands.
4. Switch the document view mode to 'Preview', then the code block will get rendered.

For more use cases, please download and open the examples folder in obsidian with this plugin installed and enabled.

## More Details You May Want to Know

- Installation: Install the plugin from Obsidian or install it manually
- Concepts: Explain how this plugin works and what to setup
  - Target Evaluation
  - Input Parameters
  - Expressions
- Examples
- Plugin Settings
- Release Notes
- Road Map
- Frequently Asked Questions

## Support

- If you like this plugin or want to support further development, you can Buy Me a Coffee.
- Please report bugs and request features in GitHub Issues




================================================
FILE: docs/Commands.md
================================================
# Commands 

To smooth the process of making trackers, obsidian-tracker provides three commands (There will be more in the future release), "Add Line Chart Tracker", "Add Bar Chart Tracker", and "Add Summary Tracker". Just type Ctrl/Cmd+P to activate the command palette, then type "Tracker" to search these commands.

After a command is executed, a code block will be added to the next line below your cursor position for you. The added code block will contain the most frequently used keys. To see the complete list of input parameters and description, please check this document.


================================================
FILE: docs/Concepts.md
================================================
# Concepts

This plugin was designed to read code blocks in YAML format. The key-value pairs in the code blocks tell the plugin what data to collect and how to represent the result.

Here are all the parameters (key-value pairs) defined in this plugin. They are used for collecting data, evaluating targets, data preprocessing, and rendering output.

### Collecting Data

Providing parameters `searchType` and `searchTarget` is the minimum requirement for a successful data collection. `searchType` can be `tag`, `frontmatter`, `wiki`, `dvField`, `table`, `fileMeta`, `task`, or `text`. Then the cooresponding `searchTarget` should be provided according to the specified type.

### Target Evaluation

Depends on the `searchType` and the `searchTarget` you provided, the evaluation of a target would be different. Simply speaking, you can track the occurrences of a target or the value attached/embedded in it.

To see the detail about the target evaluation, please check the document Target Evaluation.

### Rendering Output

Currently, obsidian-tracker provides five kinds of rendering output: `line`, `bar`, `summary`, `bullet`, `month` and `pie`. You have to provide at least one output parameter in a code block.

With output type set to `line` or `bar`, Tracker plugin will generate a customizable chart. These charts are very good at seeing the variation of collected number in the notes. 

With the output type `summary`, a text block based on your '**template**' parameter will be created. You can use expressions like '{{sum()}}' or '{{maxStreak()}}' in the template parameter, to get a statistical summary of collected data.

Output type `bullet` creates a bullet chart and could serve as a gauge showing the status (level, performance, progress) of a dataset.

Output type `month` creates a month view with circled dates exceeding the given threshold and streaks showing how long it persisted.

Output type `pie` creates a pie chart. The `data` parameter should be applied for circular sectors you want to add. Parameter `label` and `extLabel` are used for displaying labels and `dataName` is used for the diplay names on legend.

Detailed description for all parameters of the output types can be found here.


================================================
FILE: docs/Examples.md
================================================
# Examples

We provide a simplified table of use cases and full examples including data.

## Table of Use Cases

Check where (Location) and what (Target to Track) is your target and find the settings (Tracker) you need.

| Location | Target to Track  | Tracker | Get (O)ccurrences/(V)alues |
|:--------|:-------|:---------|:--:|
| content | #meditation | searchType: tag<br>searchTarget: meditation | O |
| frontmatter | ---<br>tags: meditation<br>--- | searchType: tag<br>searchTarget: meditation | O |
| content | #weight:60.5kg | searchType: tag<br>searchTarget: weight | V |
| content | #finance/bank1/transfer:100USD | searchType: tag<br>searchTarget: finance/bank1/transfer | V |
| content | #finance/bank1/transfer:100USD<br>#finance/bank1/income:80USD<br>#finance/bank1/outcome:-120USD | searchType: tag<br>searchTarget: finance/bank1 | V |
| content | #blood-pressure:180/120 | searchType: tag<br>searchTarget: blood-pressure[0], blood-pressure[1] | V |
| content | dvTarget:: 20.5 | searchType: dvField<br>searchTarget: dvTarget | V |
| content | dvTarget:: 20.5/30.5 | searchType: dvField<br>searchTarget: dvTarget[0], dvTarget[1] | V |
| content | dvTarget:: 20.5, 30.5 | searchType: dvField<br>searchTarget: dvTarget[0], dvTarget[1]<br>separator: 'comma' | V |
| frontmatter | ---<br>mood: 10<br>--- | searchType: frontmatter<br>searchTarget: mood | V |
| frontmatter | ---<br>bp: 184.4/118.8<br>--- | searchType: frontmatter<br>searchTarget: bp[0], bp[1] | V |
| frontmatter | ---<br>bp: 184.4, 118.8<br>--- | searchType: frontmatter<br>searchTarget: bp[0], bp[1]<br>separator: 'comma' | V |
| frontmatter | ---<br>bp: [184.4, 118.8]<br>--- | searchType: frontmatter<br>searchTarget: bp[0], bp[1] | V |
| frontmatter | ---<br>clock-in: 10:45<br>clock-out: 20:51<br>--- | searchType: frontmatter<br>searchTarget: clock-in, clock-out | V |
| content | [[journal]] | searchType: wiki<br>searchTarget: journal | O |
| content | ⭐ | searchType: text<br>searchTarget: ⭐ | O | 
| content | love | searchType: text<br>searchTarget: love | O |
| content | test@gmail.com<br>test@hotmail.com | searchType: text<br>searchTarget: '.+\\@.+\\..+' | O |
| content | #weightlifting: 50 | searchType: text<br>searchTarget: 'weightlifting: (?\<value\>[\\-]?[0-9]+[\\.][0-9]+\|[\\-]?[0-9]+)' | V |
| content | I walked 10000 steps today. | searchType: text<br>searchTarget: 'walked\\s+(?\<value\>[0-9]+)\\s+steps' | V |
| content | myvalues 1/2/3 | searchType: text<br>searchTarget: 'myvalues\\s+(?\<value\>[0-9]+)/([0-9]+)/([0-9]+), myvalues\\s+([0-9]+)/(?\<value\>[0-9]+)/([0-9]+), myvalues\\s+([0-9]+)/([0-9]+)/(?\<value\>[0-9]+)' | V |
| table content | { a table filled with dates and values }<br>example table | searchType: table<br>searchTarget: filePath[0][0], filePath[0][1] | V |
| table content | { a table filled with dates and values }<br>example table | searchType: table<br>searchTarget: filePath[1][0], filePath[1][1][0], filePath[1][1][1] | V |
| file meta | meta data from files <br>(size, cDate, mDate, numWords, numChars, numSentences) | searchType: fileMeta<br>searchTarget: size | V |
| content | - [x] Say love<br>- [ ] Say love | searchType:task<br>searchTarget: Say love | O |
| content | - [x] Say love | searchType:task.done<br>searchTarget: Say love | O |
| content | - [ ] Say love | searchType: task.notdone<br>searchTarget: Say love | O |

## Full examples

Full tracker code blocks can be found in folder examples and the corresponding notes (data) can be found under folder 'diary' and 'data'.

List of all examples
- Bloodpressure Tracker
- Error Messages
- Finance Tracker
- Habit Tracker
- Star Tracker
- Bar Chart
- Axis Interval and Format
- Bullet Chart
- Calendar
- Date Formats
- Dataview Inline Field
- Expression
- File Meta
- Legends
- Multiple Targets / Multiple Values
- Pie Chart
- Scaling and Positioning
- Specified Files
- Summary
- Table
- Task
- Text-value Map/Mood Tracker
- Time Values
- Word Counting
- X Dataset
- Regular Expression
- Weight Tracker
- Wiki




================================================
FILE: docs/Expressions.md
================================================
# Expressions

Expressions could help us create new and meaningful data from the original collected data by using operators and functions.

## !!! Breaking Changes !!!

From version 1.9.0, template variables, e.g. '{{sum}}', are deprecated. Instead, Tracker provide operators (+, -, *, /, %) and functions (dataset(), sum(), maxStreak(), ......etc) to help us do data processing. For users having code blocks from previous version, please replace '{{sum}}' by '{{sum()}}' or '{{sum(1)}}' by '{{sum(dataset(1))}}'.

## Where to Use 

Currently, we can only use expressions in some parameters. These includes `template` in `summary` output, `value` in `bullet` output, and `data` `label` `extLabel` in `pie` output. In future release, there will be more parameters using expressiones as input.

## How to Use

Expressions should be be wrapped in curly brackets. By using the combination of operators and funtions, Tracker can resolve the whole expression in brackets and then generate a number or a string according to what was requested. 

If the resolved output of an expression is a string, we can assign a format string to it. The format string should be placed after the expression in curly brackets following by two colons. For example, The expression '{{sum()::i}}' will force the output number represented as an integer (i for integer).  

For the number output, use 'Printf Format String' for the format string. For the date output, use the date format string defined in Moment.js.

The following tables show all the operators and functions available for now. Please make sure the input type and output type when you are combining them together. Examples could be found here. Requests for operators or functions are welcome.

## List of Operators

### Uniry Operators

| Function | Description | Operant | Output | 
|:---------|:------------|:--------|:------|
| + | positive | number or dataset | number or dataset |
| - | negative | number or dataset | number or dataset |

### Binary Operators

| Function | Description | Left Operant | Right Operant | Output | 
|:---------|:------------|:-----|:------|:-------|
| + | plus | number or dataset | number or dataset | number or dataset |
| - | minus | number or dataset | number or dataset | number or dataset |
| * | multiply | number or dataset | number or dataset | number or dataset |
| / | divide | number or dataset | number or dataset | number or dataset |
| % | modulo | number or dataset | number or dataset | number or dataset |

e.g.
- number + number --> number
- dataset + number --> dataset
- number + dataset -> dataset
- dataset + dataset --> dataset

## List of Functions

### Get Dataset by Index

| Function(InputType): OutputType | Description |
|:------------------|:-----------|
| dataset(number): Dataset | Get dataset from dataset id (the order in `searchTarget`) |

### Functions Accept Dataset and return a value

**If the input dataset is missing, it will use the first available Y dataset found.**

| Function(InputType): OutputType | Description |
|:------------------|:-----------|
| first(Dataset): number | First value of the dataset |
| last(Dataset): number | Last value of the dataset |
| min(Dataset): number | Minimum value of the dataset |
| minDate(Dataset): Date | Latest date of minimum value |
| max(Dataset): number | Maximum value of the dataset |
| maxDate(Dataset): Date | Latest date of maximum value |
| startDate(Dataset): Date | Start date of the dataset |
| endDate(Dataset): Date | End date of the dataset |
| sum(Dataset): number | Summation of values of the dataset |
| numTargets(Dataset): number | Total counts of targets |
| numDays(Dataset): number | Days from startDate to endDate |
| numDaysHavingData(Dataset): number | Number of days having data |
| maxStreak(Dataset): number | Maximum continuous days without breaks |
| maxStreakStart(Dataset): Date | Start date of the max streak |
| maxStreakEnd(Dataset): Date | End date of the max streak |
| maxBreaks(Dataset): number | Maximum break days |
| maxBreaksStart(Dataset): Date | Start date of the maximum break days |
| maxBreaksEnd(Dataset): Date | End date of the maximum break days |
| currentStreak(Dataset): number | Current continuous days |
| currentStreakStart(Dataset): Date | Start date of current streak |
| currentStreakEnd(Dataset): Date | End date of current streak |
| currentBreaks(Dataset): number | Current break days |
| currentBreaksStart(Dataset): Date | Start date of current breaks |
| currentBreaksEnd(Dataset): Date | End date of current breaks |
| average(Dataset): number | Average value of the dataset |
| median(Dataset): number | Median value of the dataset |
| variance(Dataset): number | Variance value of the dataset |

### Functions Accept Dataset and Return Dataset

| Function(InputType): OutputType | Description |
|:---------|:-----------|
| normalize(Dataset): Dataset | rescale the Y values to [0, 1] |
| setMissingValues(Dataset, number): Dataset | set the missing values |

## Missing Values

Notice that the missing values (null values) are ignored in function like sum or average. Moreover, a value plus a missing value will leads to null value (missing value). To avoid these, you can set those missing values to a value by using parameter `penalty` or use expression function `setMissingValues`.



================================================
FILE: docs/InputParameters.md
================================================
# Input Parameters

Obsidian-tracker parses key-value pairs in YAML format in your code block and uses them as input parameters. The minimum requirements for parameters are `searchType`, `searchTarget` and at least one output parameter (`line`, `bar`, `summary`, `bullet`, `month`, or `pie`).

## Array Input for a Parameter

Some of the parameters can accept more than one value for each target. For those parameters accept different value for each given search target, the maximum number of values should equal to the number of search target (NT). If the number of values are less than the number of targets, Tracker will use the previously provided one in sequence or use the default value if nothing is provided.

For Y axis related parameters, like `yMin`, `yMax`, or `yAxisLabel`, they accept one value for each Y axis (`left` and `right`). If you only use one axis, or the values for the two axes are the same, only one value is required. If you need the two axes to have different values, provide two values to do the work. The first one will be used for the left Y axis and the second one for the right Y axis.

To enter array of values, we can use YAML array (e.g. ['value1', 'value2', 'value3']) or simply values separated by comma (e.g. value1, value2, value3). The second method is a syntax surgar of Tracker to simplify input process. If YAML special characters are required in the inputs, be sure to wrap the whole values by single quotes (e.g. 'value1, value2, value3'). Please also check this for more information about YAML in Tracker.

## List of Parameters

### Root Parameters

These key-value pairs are placed under the root of the code block.

| Key | Description | Number of Values | Default |
|:--------|:-------|:-----------:|:------|
| `searchType` | Type of `searchTarget` (tag\|frontmatter\|wiki\|text\|dvField\|table\|fileMeta\|task) | 1~NT | Must be provided |
| `searchTarget` | Target to search<br>[detail] | NT (Number of Targets) | Must be provided |
| `folder` | Root path containing notes to search | 1 | Root of this vault |
| `file` | Files to include for searching | N | null |
| `specifiedFilesOnly` | Ignore files found in `folder` | 1 | false |
| `fileContainsLinkedFiles` | Include the linked files in the specified files here | N | null |
| `fileMultiplierAfterLink` | Regex string include named group 'value' <br>to search the multiplier after link | 1 | '' |
| `dateFormat` | Date format<br> Use Moment.js format or use iso-8601 | 1 | 'YYYY-MM-DD' |
| `dateFormatPrefix` | Prefix before your dateFormat (accept regex) | 1 | '' |
| `dateFormatSuffix` | Suffix after your dateFormat (accept regex) | 1 | '' |
| `startDate` | Start date to collect data from<br>accept relative date | 1 | Min date found |
| `endDate` | End date of to collect data<br>accept relative date | 1 | Max date found |
| `datasetName` | Name of the dataset for a search target` | 1~NT | untitled |
| `separator` | Character used to separate multiple values appearing in the search target | 1~NT | '/' <br> ',' in front matter tags |
| `xDataset` | Index of `searchTarget` used as xDataset | 1~NT | -1 (use filename as xDataset) |
| `constValue` | Constant value of a target if no value attached | 1~NT | 1.0 |
| `ignoreAttachedValue` | Use `constValue` even if the target has a value attached on (true\|false) | 1~NT | false |
| `ignoreZeroValue` | Treat zero value as missing (true\|false) | 1~NT | false |
| `accum` | Accumulatively sum the values over time (true\|false) | 1~NT | false |
| `stack` | Support stacked charts (true\|false) | 1 | false |
| `penalty` | Value to use if the search target is missing on the day | 1~NT | |
| `valueShift` | Amount to shift for each collected value | 1~NT | 0 |
| `shiftOnlyValueLargerThan` | Do `valueShift` only if the value is larger then the specifed one | 1~NT | null |
| `valueType` | Not implemented yet | 1~NT | |
| `textValueMap` | A container key for multiple text-value mapping | | |
| `fixedScale` | Uniform scaling factor to the graph dimensions | 1 | 1.0 |
| `fitPanelWidth` | Auto-fit the width of the chart to the container | 1 | false |
| `aspectRatio` | Change the 1:1 aspect ratio of the graph | number:number | 1:1 |
| `margin` | Four margins (top\|right\|bottom\|left) of the graph | 1~4 | 10 |
| `line` | A container key for parameters related to the line chart | | |
| `bar` | A container key for parameters related to the bar chart | | |
| `summary` | A container key for parameters related to the summary output | | |
| `bullet` | A container key for parameters related to the bullet chart | | | 
| `month` | A container key for parameters related to the month view | | |
| `pie` | A container key for parameters related to the pie chart | | |

### Parameters for Common Charts
These key-value pairs should be placed under the key `line` or `bar`.

| Key | Description | Number of Values | Default |
|:--------|:-------|:-----------:|:------|
| `title` | Title of this chart | 1 | '' |
| `xAxisLabel` | Label of X axis | 1 | 'Date' |
| `xAxisColor` | Color of X axis | 1 | 'white'('black'<sup>*</sup>) |
| `xAxisLabelColor` | Color of X axis label | 1 | 'white'('black'<sup>*</sup>) |
| `yAxisLabel` | Label of Y axis | 1~2 | 'Value' |
| `yAxisColor` | Color of Y axis | 1~2 | 'white'('black'<sup>*</sup>) |
| `yAxisLabelColor` | Color of Y axis label | 1~2 | 'white'('black'<sup>*</sup>) |
| `yAxisUnit` | Unit displayed aside Y axis label | 1~2 | '' | 
| `xAxisTickInterval` | X axis interval between ticks | 1~2 | null |
| `xAxisTickLabelFormat` | Format of tick label on X axis<br> | 1~2 | null |
| `yAxisTickInterval` | Y axis interval between ticks | 1~2 | null |
| `yAxisTickLabelFormat` | Format of tick label on Y axis<br> | 1~2 | null |
| `yMin` | Minimum value on Y axis | 1~2 |Minimum Y value found | 
| `yMax` | Maximum value on Y axis | 1~2 | Maximum Y value found |
| `reverseYAxis` | Flip (upside down) the Y Axis or not (true\|false) | 1~2 | false |
| `allowInspectData` | Show data value when mouse hovered (true\|false) | 1 | true |
| `showLegend` | Show/Hide legend (true\|false) | 1 | false |
| `legendPosition` | Legend position (top\|bottom\|left\|right) | 1 | bottom |
| `legendOrientation` | Legend orientation (vertical\|horizontal) | 1 | horizontal for bottom and top<br>vertical for left and right |
| `legendBgColor` | Legend background color | 1 | none |
| `legendBorderColor` | Legend border color | 1 | white |

### Parameters for a Line Chart
These key-value pairs should be placed under the key `line`.

| Key | Description | Number of Values | Default |
|:--------|:-------|:-----------:|:------|
| `lineColor` | Color of the lines in the chart | 1~NT | 'white'('black'<sup>*</sup>) |
| `lineWidth` | Width of the lines in the chart | 1~NT | 1.5 |
| `showLine` | Show/hide lines (true\|false) | 1~NT | true |
| `showPoint` | Show/hide data points (true\|false) | 1~NT | true |
| `pointColor` | Color of data points | 1~NT | #69b3a2 |
| `pointBorderColor` | Border color of data points | 1~NT | #69b3a2 |
| `pointBorderWidth` | Border width of data points | 1~NT | 0 |
| `pointSize` | Radius of data points | 1~NT | 3 |
| `fillGap` | Connect points over missing data (true\|false) | 1~NT | false |
| `yAxisLocation` | Corresponding Y axis for the dataset (left\|right) | 1~NT | left |

### Parameters for a Bar Chart
These key-value pairs should be placed under the key `bar`.

| Key | Description | Number of Values | Default |
|:--------|:-------|:-----------:|:------|
| `barColor` | Color of bars in the chart | 1~NT | #69b3a2 |
| `xAxisPadding` | Padding to ensure bars are fully displayed | 1~2 | null |
| `yAxisLocation` |  Corresponding y-axis for the dataset (left\|right) | 1~NT | left |

### Parameters for a Summary
These key-value pairs should be placed under the key `summary`.

| Key | Description | Number of Values | Default |
|:--------|:-------|:-----------:|:------|
| `template` | Text template (you may embed expressions | 1 | '' |
| `style` | CSS style applied to the rendered text block | 1 | '' |

### Parameters for a Bullet Chart
These key-value pairs should be placed under the key `bullet`.

| Key | Description | Number of Values | Default |
|:--------|:-------|:-----------:|:------|
| `title` | Title of this chart | 1 | '' |
| `dataset` | Index of the dataset of your interest | 1 | 0 |
| `orientation` | Bar orientation (horizontal\|vertical) | 1 | 'horizontal' |
| `value` | Actual value of interest<br>(you may embed expressions | 1 | '' |
| `valueUnit` | Unit of the Y value displayed aside | 1 | '' |
| `valueColor` | Color of the value bar | 1 | '#69b3a2' |
| `range` | Data anges of defined by series of numbers | N | [] |
| `rangeColor` | Color of the range bands | N | [] |
| `showMarker` | Show/hide the marker line (true\|false) | 1 | true |
| `markerValue` | Value of the markder | 1 | 0 |
| `markerColor` | Color of the marker | 1 | 'black' |

### Parameters for a Month View
These key-value pairs should be placed under the key `month`.

| Key | Description | Number of Values | Default |
|:--------|:-------|:-----------:|:------|
| `mode` | Pick one mode of the two(circle\|annotation) | 1 | 
| `dataset` | Index of the dataset of your interest | 1~NT | all indices of non-x searchTarget |
| `startWeekOn` | First day of a week ('Sun'\|'Mon') | 1 | 'Sun' |
| `threshold` | Threshold to determine showing a circle on a day or not | 1~NT | 0 |
| `thresholdType` | Pick one of the two (GreaterThan\|LessThan) | 2 | GreaterThan
| `yMin` | Minimum value | 1~NT | Minimum value of the dataset |
| `yMax` | Maximum value | 1~NT | Maximum value of the dataset |
| `showCircle` | Circle the day label if the collected value reach the threshold (value > `threshold`) | 1 | true |
| `color` | Main color (can be override by other color parameters) | 1 | null |
| `dimNotInMonth` | Dim the color for days not in current month | 1 | true |
| `showStreak` | Show/hide streaks between circles | 1 | true |
| `showTodayRing` | Show/hide the ring on the label today | 1 | true |
| `showSelectedValue` | Show/hide the value on the selected day | 1 | true |
| `showSelectedRing` | Show/hide a ring on the label of the selected day | 1 | true |
| `circleColor` | Color of circles | 1 | '#69b3a2' |
| `circleColorByValue` | Display circle colors based on the value | 1 | false |
| `headerYearColor` | Color of the year text in header | 1 | 'white' |
| `headerMonthColor` | Color of the month text in header | 1 | 'white' |
| `dividingLineColor` | Color of the dividing line | 1 | '#69b3a2' |
| `todayRingColor` | Color of the ring on today | 1 | 'white' |
| `selectedRingColor` | Color of the ring on the selected day | 1 | 'firebrick' |
| `initMonth` | Initial month to show (YYYY-MM) | 1 | last month found |
| `showAnnotation` | Show/hide annotation | 1 | false |
| `annotation` | Annotation for each piece of data | NT | '' |
| `showAnnotationOfAllTargets` | Show annotation of all targets at the same time | 1 | false |


### Parameters for Pie Chart
These key-value pairs should be placed under the key `pie`.

| Key | Description | Number of Values | Default |
|:--------|:-------|:-----------:|:------|
| `title` | Title of this chart | 1 | '' |
| `data` | Array of values, each represents the number or fraction of a circular sector | N | '' |
| `dataColor` | Color of each circular sector | N | '' |
| `dataName` | Name of each data shown on legend | N | |
| `label` | Labels for each data shown on circular sector | N | |
| `hideLabelLessThan` | Hide the label with its fraction number lower than | 1 | 0.03 |
| `showExtLabelOnlyIfNoLabel` | Show/hide the external label only if the correstponding label is missing or empty (true\|false) | 1 | false |
| `extLabel` | Labels for each data shown aside out of circular sector | N | |
| `ratioInnerRadius` | Ratio of donut inner radius to pie radius | 1 | 0 |
| `showLegend` | Show/hide legend (true\|false) | 1 | false |
| `legendPosition` | Legend position (top\|bottom\|left\|right) | 1 | right |
| `legendOrientation` | Legend orientation (vertical\|horizontal) | 1 | horizontal for bottom and top<br>vertical for left and right |
| `legendBgColor` | Legend background color | 1 | none |
| `legendBorderColor` | Legend border color | 1 | white |



================================================
FILE: docs/Installation.md
================================================
# Installation

## Install from the Obsidian Settings Panel
1. From Settings Panel (the icon at the bottom left corner) -> Options -> Community plugins, set 'safe mode' to off.
2. In the 'Community plugins' section, click 'Browse' and find the obsidian-tracker plugin by the name 'Tracker'.
3. Press the button 'Install' and wait for the completion of the install.
4. In the section 'Installed plugins', find and enable the plugin just installed.
5. Enjoy tracking.

## Manual Installation
Download the latest release. Extract and put the three files (main.js, manifest.json, styles.css) to folder '{{obsidian_vault}}/.obsidian/plugins/obsidian-tracker'.


================================================
FILE: docs/Questions.md
================================================
# Frequently Asked Questions

- Does Tracker only track data in daily notes (file names contain dates)?

    No. The file name of your notes could be any string. But we do need a date from each file. If it is not from the file name, we should add one more `searchTarget` and use that target as the source of X values by setting parameter `xDataset` to its index. The searchType `fileMeta` with `searchTarget` cDate (creation date) and mDate (modification date) are always accessible as date sources if you don't have any. Examples of these use cases could be found here.

- Why my line chart looks broken (not connected) at some points?

    Tracker only connects adjacent points (neighbor points by date) by default. To force it connecting points over missing data, set the parameter `fillGap` under `line` or `bar` to true.

- Why does the plugin show: error 'No valid date as X value found in notes'?

    First we have to confirm where is the source of your X values. Tracker always needs X values in dates. The default source of X values are the file names of your notes. As long as a proper `dateFormat` was assigned, and combine with `dateFormatPrefix` and `dateFormatSuffix`, the dates in file names could be extracted from your file names successfully.

    If the date values are from front matter, dataview inline field, or other places, choose the right `searchType` and `searchTarget` and mark them as `xDataset`, Tracker will collect X values for you.

    If you don't have any date values, and you just want to count the number of occurrences of a target. As a trick, you can use the creation date (cDate) or modification date (mDate) of the file as X data source. 

    Examples of these use cases could be found here.

- Why does the plugin show: error 'No valid Y value found in notes'?

    That means no matched data found in your notes. Please check the document for the detail of target evaluation.

- Why does the plugin show: 'Error parsing YAML'?

    There are syntax errors in your code block. Please check this document for common issues.

---

Still have problems?? You might encounter a bug.
Welcome to leave an issue here.



================================================
FILE: docs/ReleaseNotes.md
================================================
# Release Notes

## 1.16.0

- Adding thresholdType parameter to Calendars
- Enable bar chart full-bar display at beginning and end
- Update dependencies

## 1.15.1

- Fix: Added DatasetName as title for calendar in annotation mode
- Fix: Resolve scaling issue when navigating between monthly views
- Update dependencies

## 1.15.0

- Fix: Minor spelling error in Examples.md
- Added new expression functions - First and Last
- Updated dates in examples to fix plots
- Respect thresholds in scaled months
- Update dependencies

## 1.14.0

- Update dependencies
- Prevent overlapping external labels in pie chart
- Enable Stacked Bar Chart

## 1.13.3

- Update dependencies
- Fix typo in FinanceTracker.md
- Fix typo in TestExpression.md
- Update main.ts - use new format for {{average}}

## 1.13.2

- Update dependencies
- Fix typo in README.md
- Change streak counts to terminate on falsey values rather than null

## 1.13.1

- Fix packaging script

## 1.13.0

- Add support for inline dataview fields (including emoji support for values)
- Update dependencies

## 1.12.0

- Add aspect ratio parameter for graphs
- Reorganize release notes in readme to be in descending order (latest release first)

## 1.11.0

- Add support for checkboxes in new properties added in Obsidian 1.4
- Fix typos in documentation and examples

## v1.10.9

- Replace tab characters by spaces
- Accept more unicode characters in dvField
- Allow emojis in the folder path
- Fixed bugs

## v1.10.8

- Fixed startDat/endDate misread as a relative date

## v1.10.7

- Allow using html image tags as emoji inputs

## v1.10.6

- Fixed the coloring for missing data in the month view

## v1.10.5

- Allow using a relative date value in `initMonth` in the month view

## v1.10.4

- Allow using a regular expression as a key of the parameter `textValueMap`
- Add a parameter `shiftOnlyValueLargerThan` to determine when to do `valueShift`
- Fixed bugs reported by users
- Fixed typo in plugin settings

## v1.10.3

- Allow using the parameter `fitPanelWidth` with the output type `month` and `pie`
- Fixed the resizing and positioning of the chart tooltip

## v1.10.2

- Fixed plugin not rendering on some macOS machines

## v1.10.1

- Fixed 'failed to load plugin' on iOS

## v1.10.0

- Add annotation mode for month view (examples)
- Add parameters `xAxisTickInterval`, `yAxisTickInterval`, `xAxisTickLabelFormat` and `yAxisTickLabelFormat` for the line and bar chart (examples)
- Allow using regular expression in parameter `dateFormatPrefix` and `dateFormatSuffix` (examples)
- Add parameters `file`, `specifiedFilesOnly`, `fileContainsLinkedFiles`, and `fileMultiplierAfterLink` to retrieve data from specified files (examples)
- Add a parameter `textValueMap` to convert texts or emojis to specified values (examples)
- Fixed bugs
- Enhanced error messages

## v1.9.2

- Allow using seconds in time values
- Fixed error parsing `dvField`

## v1.9.1

- Fixed errors on collecting time values from `dvField`
- Fixed errors on collecting wiki while fileCache.links is undefined

## v1.9.0

- Add a new output type `pie`, rendering a pie chart (examples)
- Allow expressions (operators and functions) as data inputs for output type `summary`, `bullet`, and `pie` (examples: expression, summary, bullet, pie)
- Allow formatting evaluated expressions by a follwing format string (examples)

## v1.8.2

- Fixed tasks searching not working for multiple targets

## v1.8.1

- Fixed bugs while using month view with parameter `xDataset`

## v1.8.0

- Add a new `searchType` `task`, retrieving data from tasks (examples)
- Enhancement
  - Month view (examples)
    - Add parameter `circleColorByValue` to show color based on the value
    - Support multiple targets (dataset), change the dataset by clicking the header
    - Add a button (◦) to show current month
  - Accept ISO-8601 date as `dateFormat` (examples)
  - Relative date input for `startDate` and `endDate` (examples)
- Fixed missing dvField values at the last line of files

## v1.7.0

- Add a new output type 'month', rendering a month view for a given dataset (examples)

## v1.6.1

- Add new targets 'numWords', 'numChars', and 'numSentences' for input type 'fileMeta' (examples)

## v1.6.0

- Add a new input type 'fileMeta', getting meta data from a file (examples)
- Add a new output type 'bullet', rendering a bullet chart (examples)
- Enhancement
  - Accept tracking time values (examples)
  - Allow tracking nested values from front matter
  - Allow using dataset with date values as xDataset (examples)
  - Add more template variables (examples)
  - Allow parsing date in wiki brackets
- Fixed bugs

## v1.5.1

- Fixed labels not shown in light theme
- Enhanced error handling for searchType 'table'

## v1.5.0

- New searchType 'table', searching records from a given table
- New searchType 'dvField', searching the inline fields used with Dataview plugin
- Enhance multiple values extraction
  - Allow using multiple values in searchType 'text'
  - Allow using array values in searchType 'frontmatter'
  - Allow using multiple values in searchType 'dvField'
  - Allow using multiple values in searchType 'table'
  - Allow using custom separator for multiple values extraction
- Improved performance
- Reduced package size

## v1.4.1

- Enhanced error handling

## v1.4.0

- Add a new parameter (fixedScale) for the scaling of the output chart
- Add a new parameter (fitPanelWidth) to enable/disable the auto-scaling of the output chart
- Add a new parameter (margin) to help to position the chart
- Tested in Obsidian mobile app on iPhone and iPad
- Fixed bugs

## v1.3.0

- Support reading and rendering multiple targets
- Support reading and rendering multiple values (a tuple of values) under a target
- New output type 'bar', rendering a bar chart
- Add a legend for the chart output
- Fixed bugs

## v1.2.1

- Fixed files with the specified dateFormat are not recognized
- Restored the plugin's settings panel for dateFormat and folder

## v1.2.0

- Enable using regular expression in text searching
- New search type 'frontmatter', searching for key-value pairs in the front matter
- New search type 'wiki', searching for wiki links
- Reduced package size

## v1.1.0

- New output type 'summary'
- Add commands help create Tracker code blocks
- Relaxed the regex for searching tags, allowing tags embedded in sentences
- Fixed issues

## v1.0.2

- Fixed the searching of nested tag in frontmatter
- Reduced the package size by using the module from Obsidian

## v1.0.1

- Remove dependencies to Node.js modules
- Add example markdown files

## v1.0.0

First version released at 2021-03-23

- Track simple tags, value-attached tags, and texts using code blocks
- Represent the tracked data in a customizable line chart
- Allow tracking in-line tags and tags in frontmatter
- Allow tracking nested tags



================================================
FILE: docs/RoadMap.md
================================================
# Road Map

- Data Collecting
    - [x] Support tracking key-value pairs in frontmatter
    - [x] Support searching text using regular expression
    - [x] Support multiple targets and multiple values
    - [x] Add a parameter xDataset to identify targets to be used as x values
    - [x] Allow tracking time values
    - [ ] Allow tracking date values
    - [x] Get data from a table
    - [x] Collect data from dataview plugin's inline fields
    - [x] Collect meta information from file
    - [x] Support tracking tasks
    - [ ] Allow manual data input (x and y values) in custom datasets
    - [ ] Allow forced value types
    - [ ] Allow using non-date x values
    - [ ] Allow multiple points (different time stamp) from a single file
- Output Type and Graph
    - [x] Implement output type 'summary', analyzes the input data and represents it using a user-defined text template
    - [x] Implement output type 'bar', rendering a bar chart
    - [x] Implement output type 'bullet', rendering
    - [x] Implement output type 'month', rendering a month view
    - [ ] Implement output type 'heatmap', rendering a heatmap like Github activity chart
    - [x] Implement output type 'pie', rendering a pie chart
    - [x] Add parameters for adjusting the size of the graph
    - [ ] Multiple outputs from one code block
    - [ ] Support graphs showing the correlation between sets of data
    - [ ] Allow a graph drawing selected dataset.
    - [x] Allow expressions evaluating operators and functions
    - [x] Allow format string for evaluated expressions
- Helper
    - [x] Add Commands help create Tracker blocks.
    - [ ] Add an 'Explode' button to the rendered blocks, it will replace the code block with the rendered result
    - [ ] Add a helper panel for adding frequently used tracking targets to article.
- Data Processing
    - [ ] Allow arithmetics operation on dataset and generate custom datasets
    - [ ] Add data post-process function, e.g. 'moving average'
- Performance
    - [ ] Use PixiJS to do rendering

And more ... Feature requests are welcome.

P.S. Features may not be implemented in the order above.


================================================
FILE: docs/Settings.md
================================================
# Plugin Settings

The default folder to search and the date format can be defined in the plugin's settings panel. If `folder` and `dateFormat` are not assigned in your code blocks, these default values will be applied automatically.

| Setting Item | Description | Default | 
|:--------|:-------|:---------|
| Default folder location | The folder to search | Root of the vault |
| Default date format | The date format you are using | 'YYYY-MM-DD' | 

For more information about the dateFormat setting, please also check the TestDateFormats example and moment.js string format.


================================================
FILE: docs/TargetEvaluation.md
================================================
# Target Evaluation

From the input parameters you provided, the search targets dispersed in the notes will be counted or evaluated as a value. Tracker plugin supports eight kinds of `searchType`: `tag`, `frontmatter`, `wiki`, `text`, `table`, `dvField`, `task`, and `fileMeta`, dealing with different types of searching condition.

## Multiple Targets
You can provide multiple search targets in code block by entering an array of targets separated by a comma under parameter `searchType` and `searchTarget`. Each of the targets will be identified in order and then the  values in notes will be evaluated and form a dataset indexed by that order in the array (zero-based indexing).

```
searchTarget: target0, target1, target2, ...... 
searchType: type0, type1, type2, .....
datasetName: dataset0, dataset1, dataset2, ......
line:
    lineColor: red, blue, yellow
```

Above is an example of multiple targets searching. In the code block, multiple targets are provided and separated by a comma. If they have a different searchType, provide the same number of types in the same order. In this case, the second search target 'target1' with index 1 has type 'type1' and name 'dataset1'. 

Many other parameters that accept multiple values (e.g. lineColor) can also be provided and the value given will be applied to the corresponding dataset.

## Multiple Values

Multiple values under a target (value tuple) separated by a slash, e.g. #bloodpressure:180/120mmHg, are supported after version 1.3.0. To identify a specific value as a target, use an accessor with bracket notation where the value in the bracket is the index by the order of values. In this case, they are bloodpressure[0] and bloodpressure[1]. You can find the example of this here. You can also use a custom separator by using the parameter `separator`.

## Search Target in Detail

### searchType: tag

Simple tags in the format of '*#tagName*' in the file content are evaluated as a constant value (default value 1.0). You can override the value by assigning the key `constValue` in the code block. Use the tag name (the name after #) as the value of key `searchTarget` or use quoted tag (`#tagName`) to make it work.

For tags in frontmatter (e.g. tags: meditation), it works like simple tags and will be evaluated as a constant value. For example, 

\-\-\-<br>
tags: tagName1, tagName2<br>
......<br>
\-\-\-<br>

Set `searchTarget` to tagName1 or tagName2 will make the plugin do its work.

In your content, a value can be attached to the tag in the format of '*#tagName:value*'. Note the value should be appended right after your tag and an extra colon **without spaces**. If a value is attached this way, the obsidian-tracker will automatically use the provided value instead of the constant one. 

Nested tags with values attached could be useful for tracking children's data separately and also still see the overall merged data using parent tags.

If you don't want value-attached tags in your content, you can also put data in front matter and use `frontmatter` as your searchType.

### searchType: frontmatter

This search type is used to query the key-value pairs in the front matter. If you don't want these values been seen in your article, the front matter would be the best place to record. For example,

\-\-\-<br>
mood: 10<br>
......<br>
\-\-\-<br>

### searchType: wiki
This search type helps you count wiki links in articles. For example,
[[01 - COMANDO/1.1 Missões/3. Ativos/Viajante do Tempo/Conteúdos/Viagens/A Fé no Coliseu - A Grande Perseguição (303 d.C)/03 - Conteúdo para Instagram/Carrousels/A Escalada do Terror Como Roma Tentou Apagar o Cristianismo em 4 Decretos/A]]
[[B|Link to B]]

### searchType: text
searchType `text` is the most powerful one among all. If you simply provide text like 'love', the number of occurrences of tags will be counted. You can provide a regular expression to search for a very complicated target by wrapping it in single quotes. If you want to retrieve a value from it, use the group name in the expression. To see more detail, see this case.

Multiple values in text search can be achieved by separate regex by comma and wrap them all in single quotes as follows:

```
searchTarget: 'regex1, regex2'
......
```

### searchType: dvField

Tracker supports retrieving inline fields used with the dataview plugin. To get "targetName:: value" in your article, try the following tracker settings.

```
searchType: dvField
searchTarget: targetName
......
```

If you have multiple values in field, like "targetName:: 123 @ 456", use the following tracker settings.
<br>
```
searchType: dvField
searchTarget: targetName[0], targetName[1]
separator: '@'
......
```

More dvField example can be found here. 

### searchType: table

This search type is very much different from others because it does not search over files in the specified folder. Instead, it looks into a given file, finds the specified table, and retrieves data from specified columns. Here is an example,

```
searchType: table
searchTarget: data/Tables[0][0], data/Tables[0][1], data/Tables[0][2]
xDataset:
line:
    yAxisLocation: none, left, right
    lineColor: none, yellow, red
    showLegend: true
```

In this case, "data/Tables" is the path of the file of interest.  The number in the first brackets after the path ([0]) is the index of the table of interest in the file, starts from 0. And the number in the second brackets is the index of the column containing target data. If there are multiple values in table cells, you can provide a third index to identify them.

More table examples can be found here.

### searchType: fileMeta

With this search type, you can retrieve infomation of files. Currently, three kinds of data you can get.

- cDate: creation date of a file
- mDate: last modification date of a file
- size: file size in bytes
- numWords: number of words in a file
- numChars: number of characters in a file (including spaces)
- numSentences: number of setences in a file

`cData` and `mDate` can be used as X dataset and `size` can be used as Y dataset.

### searchType: task

You can retrieve infomation from tasks by using `searchType` `task`.
The provided `searchTarget` will limit the result with task's contents match the input.

Using type `task` or `task.all` will get you all tasks no matter it is done or not.
To get task done, use `task.done`. By contrast, use `task.notdone`.



================================================
FILE: docs/YAML.md
================================================
# YAML Related Issues

## Special characters

YAML special characters (e.g. #, [, ], ...) are not allowed for input values in code blocks. You need to wrap the whole input up by single quotes.

### Example 1 - Tag Search
If we have a bunch of tags (say #tagName) to track.
This will leads to 'Error parsing YAML' because of the # charactter.
```
searchType: tag
searchTarget: #tagName
```

Instead, wrapping the input by single quotes will do the work.
```
searchType: tag
searchTarget: '#tagName'
```

or simply
```
searchType: tag
searchTarget: tagName
```

### Example 2 - Hex Color Codes

Hex color codes must be wrapped in single quotes.
```
searchType: tag
searchTarget: weight
line:
    lineColor: '#F08080'
```

Wrap the whole input by single quotes.
```
searchType: tag
searchTarget: weight, push-up
line:
    lineColor: '#F08080, #008080'
```

### Example 3 - Text Search with Regex

If we want to track value-attached tags not matched the standard format of Tracker, for example, weightlifting: 20.5kg. We can use search type `text` with regular expression in `searchTarget`.
```
searchType: text
searchTarget: 'weightlifting:\s(?<value>[\-]?[0-9]+[\.][0-9]+|[\-]?[0-9]+)'
```
The whole input should be wrapped in single quotes because of the special characters.

## Array input
Tracker accepts two types of array input.

- YAML Array

A YAML array input can be represented as: ['value1', 'value2', 'value3']. 

- Value Separated by Comma

Use values separated by comma: value1, value2, value3
Or single quoted string: 'value1, value2, value3'





================================================
FILE: examples/BloodPressureTracker.md
================================================


# Blood Pressure Tracker

``` tracker
searchType: frontmatter
searchTarget: bloodpressure[0], bloodpressure[1]
datasetName: systolic, diastolic
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Blood Pressures
    yAxisLabel: BP
    yAxisUnit: mmHg
    lineColor: yellow, red
    showLegend: true
    legendPosition: bottom
```

``` tracker
searchType: frontmatter
searchTarget: bloodpressure[0], bloodpressure[1]
datasetName: systolic, diastolic
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
summary:
    template: "Average: {{average(dataset(0))}}/{{average(dataset(1))}}"
```

``` tracker
searchType: frontmatter
searchTarget: bloodpressure[0], bloodpressure[1]
datasetName: systolic, diastolic
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Blood Pressures
    yAxisLabel: Systolic, Diastolic
    yAxisUnit: mmHg
    yMin: 150, 110
    yMax: 190, 125
    yAxisLocation: left, right
    yAxisColor: yellow, red
    yAxisLabelColor: yellow, red
    lineColor: yellow, red
    showLegend: true
    legendPosition: right
```

Please also check those search targets in markdown files under folder 'diary'.



================================================
FILE: examples/ErrorMessages.md
================================================
# Error Messages

## YAML
Error parsing caused by the escaping character YAMLParsError: Missing closing "quote"
``` tracker
searchType: tag
searchTarget: "\"
line:
```

'searchTypes' --> typo
'searchType' --> correct
``` tracker
searchTypes: tag
searchTarget: weight
line:
```

'searchTargets' --> typo
'searchTarget' --> correct
``` tracker
searchType: tag
searchTargets: weight
line:
```

'lines' --> typo
'line' --> correct
``` tracker
searchType: tag
searchTarget: weight
lines:
```

Missing tracker block identifier, no error message though.
```
searchType: tag
searchTarget: weight
line:
```

## searchTarget
Missing searchTarget
``` tracker
searchType: tag
searchTarget: 
line:
```

Invalid searchTarget, '#' is a special character to YAML, use single quotes to wrap it
``` tracker
searchType: tag
searchTarget: #weight 
line:
```

## Folder
Folder not exists
``` tracker
searchType: tag
searchTarget: weight
folder: abc
line:
```

## Files
No file in folder
``` tracker
searchType: tag
searchTarget: weight
folder: empty
line:
```

## Number of parameters
Two search targets provided, the number of search types shouldn't be more than two.
``` tracker
searchType: frontmatter, frontmatter, frontmatter
searchTarget: bloodpressure[0], bloodpressure[1]
line:
```

yAxisLabel allows only two inputs
``` tracker
searchType: frontmatter, frontmatter
searchTarget: bloodpressure[0], bloodpressure[1]
line:
    yAxisLabel: BP1, BP2, BP3
```

## startDate & endDate
The format of startDate or endDate does not match dateFormat in the plugin settings. Change the settings or Add a dateFormat parameter into YAML.
``` tracker
searchType: tag
searchTarget: weight
startDate: 2020-01-01_Fri
endDate: 2020-01-31_Mon
line:
```

We don't have thirty days in February
``` tracker
searchType: tag
searchTarget: weight
startDate: 2021-02-01
endDate: 2021-02-30
line:
```

## X Values (Dates)
No note found in the given date range
``` tracker
searchType: tag
searchTarget: weight
startDate: 2020-01-01
endDate: 2020-01-31
line:
```

No valid X values, add "xDataset: 0" to fix it
``` tracker
searchType: fileMeta, dvField
searchTarget: cDate, dataviewTarget
folder: data
line:
    fillGap: true
```

## Y Values
No valid Y values!!!!!
Use parameter `textValueMap` to map a text to a value.
``` tracker
searchType: frontmatter
searchTarget: randchar
folder: diary
line:
    fillGap: true
```

## Output
No output type provided, choose 'line', 'bar', or 'summary'.
``` tracker
searchType: tag
searchTarget: weight
``` 

## Line Chart
The Parameter 'lineColor' allows only one input for the single target
``` tracker
searchType: tag
searchTarget: weight
line:
    title: Line
    lineColor: red, yellow
``` 

The parameter name should be 'title', not 'titles'
``` tracker
searchType: frontmatter, frontmatter
searchTarget: bloodpressure[0], bloodpressure[1]
line:
    titles: "Blood Pressure"
``` 

## Table
All dates are invalid, leads to an error message
``` tracker
searchType: table
searchTarget: data/Tables[4][0], data/Tables[4][1]
xDataset: 0
line:
    lineColor: none, yellow
```


Please also check those search targets in markdown files under folder 'diary' and 'data'.

## Expression
Unknown function
``` tracker
searchType: task
searchTarget: Say I love you
summary:
    template: '{{unknown()}}'
```

Incomplete expression
``` tracker
searchType: task
searchTarget: Say I love you
summary:
    template: '{{1+}}'
```

No dataset found for id
``` tracker
searchType: task
searchTarget: Say I love you
summary:
    template: '{{sum(dataset(1))}}'
```

Divide by zero
``` tracker
searchType: task
searchTarget: Say I love you
summary:
    template: '{{sum()/0}}'
```

Invalid data range (data only contains 1 and null)
``` tracker
searchType: tag
searchTarget: meditation
folder: diary
summary:
    template: '{{sum(normalize(dataset(0)))}}'
```

## Deprecated
### Deprecated template variables

Deprecated template variable
``` tracker
searchType: task
searchTarget: Say I love you
summary:
    template: '{{sum}}'
```




================================================
FILE: examples/example_generator.ts
================================================
import * as fs from "fs";
import * as path from "path";
import * as moment from "moment";

let root_folder = __dirname;
let subfolder = "diary";
let dateFormat = "YYYY-MM-DD";
let startDate = moment("2021-01-01", dateFormat);
let endDate = moment("2021-12-31", dateFormat);
let seed = 1;

function random() {
    var x = Math.sin(seed++) * 10000;
    return x - Math.floor(x);
}

function randomIntFromInterval(min: number, max: number) {
    return Math.floor(random() * (max - min + 1) + min);
}

function randomFloatFromInterval(min: number, max: number) {
    return random() * (max - min + 1) + min;
}

// Check subfolder exists
let subfolderPath = path.join(root_folder, subfolder);
if (!fs.existsSync(subfolderPath)) {
    fs.mkdirSync(subfolderPath);
}

let dayCount = 0;
for (
    let curDate = startDate.clone();
    curDate <= endDate;
    curDate.add(1, "days")
) {
    dayCount++;
    let fileName = curDate.format(dateFormat);
    let filePath = path.join(subfolderPath, fileName + ".md");

    let fh = fs.openSync(filePath, "w+");

    let content: string = "";

    // fontmatter
    let frontmatter = "---\n";

    // front matter tags
    let weekday = curDate.weekday();
    if (weekday == 0 || weekday == 6) {
        frontmatter += "tags: " + "\n";
    } else {
        frontmatter += "tags: " + "work_log" + ", " + "work_log2" + "\n";
    }
    // frontmatter mood
    let moodSymbols = ["😀", "🙂", "😐", "🙁", "😞"];
    let indMood = randomIntFromInterval(0, 4);
    frontmatter += "mood: " + moodSymbols[indMood] + "\n";

    // blood pressure
    let progress = dayCount;
    if (progress > 100) {
        progress = 100;
    }
    let systolicStart = 180;
    let diastolicStart = 120;
    let systolicEnd = 120;
    let diastolicEnd = 100;
    let systolicDeviation = randomIntFromInterval(-5, 5);
    let diastolicDeviation = randomIntFromInterval(-2, 2);
    let systolic =
        ((systolicEnd - systolicStart) * dayCount) / 100 +
        systolicStart +
        systolicDeviation;
    let diastolic =
        ((diastolicEnd - diastolicStart) * dayCount) / 100 +
        diastolicStart +
        diastolicDeviation;
    frontmatter += "bloodpressure: " + systolic + "/" + diastolic + "\n";
    frontmatter += "bloodpressure1: " + systolic + ", " + diastolic + "\n";
    frontmatter +=
        "bloodpressure2: [" + systolic + ", " + diastolic + "]" + "\n";

    frontmatter += "bp:" + "\n";
    frontmatter += "    systolic: " + systolic + "\n";
    frontmatter += "    diastolic: " + diastolic + "\n";

    // clock-in clock-out, 24hr
    let time_clock_in =
        randomIntFromInterval(8, 10).toString() +
        ":" +
        randomIntFromInterval(0, 59).toString();
    let time_clock_out =
        randomIntFromInterval(16, 20).toString() +
        ":" +
        randomIntFromInterval(0, 59).toString();
    frontmatter += "clock-in: " + time_clock_in + "\n";
    frontmatter += "clock-out: " + time_clock_out + "\n";

    // sleep, 12hr + am/pm
    let time_in_bed =
        randomIntFromInterval(9, 11).toString() +
        ":" +
        randomIntFromInterval(0, 59).toString() +
        " pm";
    let time_out_of_bed =
        randomIntFromInterval(5, 7).toString() +
        ":" +
        randomIntFromInterval(0, 59).toString() +
        " am";
    frontmatter += "sleep: " + time_in_bed + "/" + time_out_of_bed + "\n";

    // deep value
    let deepValue = randomFloatFromInterval(0.0, 100.0);
    frontmatter += "deepValue: " + "\n";
    let indent = "    ";
    for (let ind = 0; ind < 5; ind++) {
        frontmatter += indent + "very: " + "\n";
        indent = indent + "    ";
    }
    frontmatter += indent + "deep: " + deepValue.toFixed(1) + "\n";

    // random character
    frontmatter += "randchar: " + String.fromCharCode(65+indMood) + "\n";

    frontmatter += "---\n";
    content += frontmatter;

    content += "\n";

    // weight
    let weight = randomFloatFromInterval(60.0, 80.0);
    let tagWeight = "#weight:" + weight.toFixed(1) + "kg";
    content += tagWeight + "\n";

    content += "\n";

    // excercise
    // pushup
    let numPushup = randomIntFromInterval(30, 50);
    let tagPushup = "#exercise-pushup:" + numPushup;
    content += tagPushup + "\n";
    //plank
    let numPlank = randomIntFromInterval(30, 120);
    let tagPlank = "#exercise-plank:" + numPlank + "sec";
    content += tagPlank + "\n";

    content += "\n";

    // meditation
    let tagMeditation = "#meditation";
    let missedMeditation = randomIntFromInterval(0, 1);
    if (!missedMeditation) {
        content += tagMeditation + "\n";
    }

    content += "\n";

    // star
    let textStar = "⭐";
    let numStar = randomIntFromInterval(0, 5);
    content += textStar.repeat(numStar) + "\n";

    content += "\n";

    // clean up
    let tagCleanUp = "#clean-up";
    let doCleanUp = randomIntFromInterval(0, 5);
    if (doCleanUp === 1) {
        content += tagCleanUp + "\n";
    }

    content += "\n";

    // finance
    let tagFinanceBank1 = "#finance/bank1";
    let tagFinanceBank2 = "#finance/bank2";

    let expense = randomFloatFromInterval(2.0, 3.0);
    content += tagFinanceBank1 + ":-" + expense.toFixed(1) + "USD" + "\n";

    if (dayCount % 30 == 0) {
        content += tagFinanceBank2 + ":" + "200USD" + "\n";
        content += tagFinanceBank2 + "/transfer:" + "-100USD" + "\n";
        content += tagFinanceBank1 + "/transfer:" + "100USD" + "\n";
    }

    content += "\n";

    // wiki links
    content += "[[todo_family|To-Do @Family]]" + "\n";
    content += "[[todo_work|To-Do @Work]]" + "\n";

    content += "\n";

    // searching text use regex
    let addEmail1 = randomIntFromInterval(0, 1);
    if (addEmail1) {
        content += "obsidian-tracker@gmail.com" + "\n";
    }
    let addEmail2 = randomIntFromInterval(0, 1);
    if (addEmail2) {
        content += "obsidian-tracker+1@gmail.com" + "\n";
    }
    let addEmail3 = randomIntFromInterval(0, 1);
    if (addEmail3) {
        content += "obsidian-tracker@yahoo.com" + "\n";
    }

    content += "\n";

    let countWeightLifting = randomIntFromInterval(10, 20);
    let addWeightLifting = randomIntFromInterval(0, 5);
    if (addWeightLifting > 0) {
        content += "weightlifting: " + countWeightLifting + "\n";
    }

    content += "\n";

    let dataviewValue = randomIntFromInterval(0, 100);
    let dataviewValue1 = randomIntFromInterval(0, 50);
    let dataviewValue2 = randomIntFromInterval(50, 100);
    content += "dataviewTarget:: " + dataviewValue + "\n";
    content += "- Make Progress:: " + dataviewValue1 + "\n";
    content += "- Make-Progress:: " + dataviewValue2 + "\n";
    content +=
        "dataviewTarget1:: " + dataviewValue + "/" + dataviewValue1 + "\n";
    content +=
        "dataviewTarget2:: " + dataviewValue1 + " @ " + dataviewValue2 + "\n";
    content +=
        "dataviewTarget3:: " + dataviewValue1 + ", " + dataviewValue2 + "\n";

    content += "\n";

    // clock-in clock-out in dvField
    let seconds = dataviewValue1;
    content += "clock-in:: " + time_clock_in + ":" + seconds + "\n";
    content += "clock-out:: " + time_clock_out + ":" + seconds +"\n";

    content += "\n";

    // sleep in dvField
    content += "sleep:: " + time_in_bed + "/" + time_out_of_bed + "\n";

    content += "\n";

    let amplitude = 1.0;
    let period = 30; // how many days to complete a sin period
    let numSinValues = 9;
    let initPhaseShift = -1.0;
    let shiftPhase = 1.0;
    let sinValues: Array<string> = [];
    for (let ind = 0; ind < numSinValues; ind++) {
        let shift = initPhaseShift + ind * shiftPhase;
        let sinValue =
            amplitude *
            Math.sin(((2.0 * Math.PI) / period) * (dayCount + shift));
        sinValues.push(sinValue.toFixed(5));
    }

    let tagSin = "#sin";

    content += tagSin + ":" + sinValues.join("/") + "\n";

    content += "\n";

    let sinSquareValues: Array<string> = [];
    for (let ind = 0; ind < numSinValues; ind++) {
        let shift = initPhaseShift + ind * shiftPhase;
        let sinSquareValue =
            (amplitude *
                Math.sin(((2.0 * Math.PI) / period) * (dayCount + shift))) **
            2;
        sinSquareValues.push(sinSquareValue.toFixed(5));
    }

    let tagSinSquare = "#sinsquare";
    content += tagSinSquare + ":" + sinSquareValues.join("/") + "\n";

    content += "\n";

    // Tasks
    let taskSayLove = "Say I love you";
    let missedSayLove = randomIntFromInterval(0, 1);
    if (!missedSayLove) {
        content += "- [x] " + taskSayLove + "\n";
    }
    else {
        content += "- [ ] " + taskSayLove + "\n";
    }

    content += "\n";

    fs.writeFileSync(fh, content);
    fs.closeSync(fh);
}



================================================
FILE: examples/FinanceTracker.md
================================================
# Finance Tracker

``` tracker
searchType: tag
searchTarget: finance
folder: diary
accum: true
endDate: 2021-01-31
line:
    title: Finance
    yAxisLabel: USD
    lineWidth: 4
```


``` tracker
searchType: tag
searchTarget: finance/bank1
folder: diary
accum: true
endDate: 2021-01-31
line:
    title: Bank1
    yAxisLabel: USD
```


``` tracker
searchType: tag
searchTarget: finance/bank2
folder: diary
accum: true
endDate: 2021-03-15
line:
    title: Bank2
    yAxisLabel: USD
    fillGap: true
```

Please also check those search targets in markdown files under folder 'diary'.



================================================
FILE: examples/HabitTracker.md
================================================
# Habit Tracker

``` tracker
searchType: tag
searchTarget: exercise-pushup
folder: diary
endDate: 2021-01-31
line:
    title: PushUp
    yAxisLabel: Count
    lineColor: "#d65d0e"
```

``` tracker
searchType: tag
searchTarget: exercise-plank
folder: diary
endDate: 2021-01-31
line:
    title: Plank
    yAxisLabel: Hold
    yAxisUnit: sec
    lineColor: "#458588"
    pointColor: red
```

``` tracker
searchType: tag
searchTarget: meditation
folder: diary
accum: true
penalty: -1
endDate: 2021-01-31
line:
    title: Meditation
    yAxisLabel: Count
```

## Summary
### Meditation
``` tracker
searchType: tag
searchTarget: meditation
folder: diary
summary:
    template: "Longest Streak: {{maxStreak()}} day(s)\nLongest Breaks: {{maxBreaks()}} day(s)\nLast streak: {{currentStreak()}} day(s)"
```

### CleanUp
``` tracker
searchType: tag
searchTarget: clean-up
folder: diary
endDate: 2021-01-31
summary:
    template: "Last Break: {{currentBreaks()}} day(s)"
```

### Work log
``` tracker
searchType: tag
searchTarget: work_log
folder: diary
accum: true
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Work Log
    yAxisLabel: Count
    pointSize: 5
    pointColor: white
    pointBorderWidth: 2
    pointBorderColor: "#d65d0e"
```

Please also check those search targets in markdown files under folder 'diary'.


================================================
FILE: examples/StarTracker.md
================================================
# Star Tracker
## Summary

``` tracker
searchType: text
searchTarget: ⭐
folder: diary
endDate: 2021-01-31
summary:
    template: "I have {{sum()}} stars in total."
    style: "font-size:20px;color:yellow;margin-left: 50px;margin-top:00px;"
```

``` tracker
searchType: text
searchTarget: ⭐
folder: diary
endDate: 2021-01-31
accum: true
line:
    title: Count the Given Stars
    yAxisLabel: Count
    showLine: false
```

Please also check those search targets in markdown files under folder 'diary'.


================================================
FILE: examples/TestAxisIntervalAndFormat.md
================================================
# Test Axis Interval and Tick Label Format

## Y Axis Interval

Numeric Y values
``` tracker
searchType: tag
searchTarget: weight
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Weight Log
    yAxisLabel: Weight
    yAxisUnit: kg
    lineColor: yellow
    yAxisTickInterval: 5
    yMin: 55
```

Y values in time
``` tracker
searchType: frontmatter
searchTarget: clock-in, clock-out
endDate: 2021-01-15
folder: diary
datasetName: Clock-In, Clock-Out
line:
    title: "Working Hours"
    yAxisLabel: "Time (24h)"
    reverseYAxis: true
    lineColor: yellow, red
    showPoint: true
    yAxisTickInterval: 1h
    yMin: 06:00
    yMax: 23:00
```

## Y Axis Tick Label Format
Float numbers with precision of 1 decimal digits
``` tracker
searchType: tag
searchTarget: weight
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Weight Log
    yAxisLabel: Weight
    yAxisUnit: kg
    lineColor: yellow
    yAxisTickInterval: 5
    yAxisTickLabelFormat: .2f
    yMin: 55
```

Y values in time
``` tracker
searchType: frontmatter
searchTarget: clock-in, clock-out
endDate: 2021-01-15
folder: diary
datasetName: Clock-In, Clock-Out
line:
    title: "Working Hours"
    yAxisLabel: "Time (24h)"
    reverseYAxis: true
    lineColor: yellow, red
    showPoint: true
    yMin: 05:00
    yMax: 22:00
    yAxisTickInterval: 50m
    yAxisTickLabelFormat: H---m
```

## X Axis Interval
``` tracker
searchType: tag
searchTarget: weight
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Weight Log
    yAxisLabel: Weight
    yAxisUnit: kg
    lineColor: yellow
    xAxisTickInterval: 1w
```

## X Axis Tick Label Format
``` tracker
searchType: tag
searchTarget: weight
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Weight Log
    yAxisLabel: Weight
    yAxisUnit: kg
    lineColor: yellow
    xAxisTickInterval: 7d
    xAxisTickLabelFormat: M-DD
```


================================================
FILE: examples/TestBarChart.md
================================================
# Test Bar Chart

``` tracker
searchType: tag
searchTarget: weight
folder: diary
startDate: 2021-01-01
endDate: 2021-01-05
bar:
    title: Weight Log
    yAxisLabel: Weight
    xAxisPadding: 12h
    yAxisUnit: kg
    yMin: 0
    barColor: darkolivegreen
```

``` tracker
searchType: tag
searchTarget: weight
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
bar:
    title: Weight Log
    yAxisLabel: Weight
    xAxisPadding: 12h
    yAxisUnit: kg
    yMin: 0
    barColor: brown
```

``` tracker
searchType: tag
searchTarget: sin[0], sin[1], sin[2]
folder: diary
startDate: 2021-01-10
endDate: 2021-01-21
bar:
    title: Sin Wave
    yAxisLabel: Value
    xAxisPadding: 12h
    barColor: yellow, red, green
```

``` tracker
searchType: tag
searchTarget: sinsquare[0], sinsquare[1], sinsquare[2], sinsquare[3], sinsquare[4], sinsquare[5]
folder: diary
startDate: 2021-01-01
endDate: 2021-01-05
bar:
    title: Sin Square Wave
    yAxisLabel: Value
    xAxisPadding: 12h
    yMin: 0
    barColor: yellow, red, green, blue, orange, white
```


``` tracker
searchType: tag
searchTarget: sinsquare[0], sinsquare[1], sinsquare[2], sinsquare[3], sinsquare[4], sinsquare[5]
folder: diary
startDate: 2021-01-01
endDate: 2021-01-05
stack: true
bar:
    title: Sin Square Wave (Stacked)
    yAxisLabel: Value
    xAxisPadding: 12h
    yMin: 0
    barColor: yellow, red, green, blue, orange, black
```
Please also check those search targets in markdown files under folder 'diary'.


================================================
FILE: examples/TestBullet.md
================================================
# Test Bullet

## Manual Input Data

Manual input `value` as 12\.5
``` tracker
searchType: tag
searchTarget: clean-up
folder: diary
endDate: 2021-01-31
fixedScale: 1.1
bullet:
    title: "Clean Up"
    dataset: 0
    orientation: horizontal
    range: 10, 20, 40
    rangeColor: darkgray, silver, lightgray
    value: 12.5
    valueUnit: times
    valueColor: '#69b3a2'
    showMarker: true
    markerValue: 30
    markerColor: black
```

## Data from Notes

Horizontal bullet chart
value from expression function currentBreaks()
``` tracker
searchType: tag
searchTarget: clean-up
folder: diary
endDate: 2021-01-31
fixedScale: 1.1
bullet:
    title: "Clean Up"
    dataset: 0
    orientation: horizontal
    range: 10, 20, 40
    rangeColor: darkgray, silver, lightgray
    value: "{{currentBreaks()}}"
    valueUnit: times
    valueColor: '#69b3a2'
    showMarker: true
    markerValue: 24
    markerColor: black
```

Vertical bullet chart
value from expression function sum()
``` tracker
searchType: tag
searchTarget: meditation
folder: diary
endDate: 2021-01-31
bullet:
    title: "Meditation"
    dataset: 0
    orientation: vertical
    range: 30, 60, 100
    rangeColor: darkgray, silver, lightgray
    value: "{{sum()}}"
    valueUnit: times
    valueColor: steelblue
    showMarker: true
    markerValue: 80
    markerColor: red
```

Please also check those search targets in markdown files under folder 'diary'.


================================================
FILE: examples/TestCalendar.md
================================================
# Test Calendar

## Single target
### Minimum setup
1. Use default colors only
2. Use parameter `datasetName` to set the title name
``` tracker
searchType: tag
searchTarget: meditation
datasetName: Meditation
folder: diary
endDate: 2021-01-31
month:
```

### Colorized
1. Click "<" to see data in previous month
2. Click ">" to see data in next month
3. Click "◦" to see data in current month
``` tracker
searchType: tag
searchTarget: exercise-pushup
datasetName: PushUp
folder: diary
endDate: 2021-01-31
month:
    startWeekOn: 'Sun'
    threshold: 40
    color: tomato
    headerMonthColor: orange
    dimNotInMonth: false
    todayRingColor: orange
    selectedRingColor: steelblue
    showSelectedValue: true
```

### Colorized
``` tracker
searchType: tag
searchTarget: meditation
datasetName: Meditation
folder: diary
endDate: 2021-01-31
month:
    startWeekOn: 'Sun'
    color: steelblue
    headerMonthColor: green
    selectedRingColor: orange
```

### Colored by Values
Use parameters `circleColorByValue`, `yMin`, and `yMax`, to color the circles based on the values
``` tracker
searchType: tag
searchTarget: exercise-pushup
datasetName: PushUp
folder: diary
endDate: 2021-01-31
month:
    startWeekOn:
    threshold: 10
    color: green
    headerMonthColor: orange
    dimNotInMonth: false
    todayRingColor: orange
    selectedRingColor: steelblue
    circleColorByValue: true
    yMin: 0
    yMax: 50
    showSelectedValue: true
```

### Colored by Threshold and thresholdType
Use parameters threshold and thresholdType - "LessThan" to color the circles
``` tracker
searchType: tag
searchTarget: exercise-pushup
datasetName: PushUp
folder: diary
endDate: 2021-01-31
month:
    startWeekOn:
    threshold: 40
    thresholdType: LessThan
    color: green
    headerMonthColor: orange
    dimNotInMonth: false
    todayRingColor: orange
    selectedRingColor: steelblue
    showSelectedValue: true
```

### Check minDate, minValue, maxDate, maxValue
``` tracker
searchType: tag
searchTarget: exercise-pushup
summary:
    template: "minDate: {{minDate()}}\nminValue: {{min()}}\nmaxDate: {{maxDate()}}\nmaxValue: {{max()}}"
```

### initMonth

Specify the initial month in YYYY-MM format
``` tracker
searchType: tag
searchTarget: exercise-pushup
datasetName: PushUp
folder: diary
month:
    startWeekOn:
    threshold: 40
    color: green
    headerMonthColor: orange
    dimNotInMonth: false
    todayRingColor: orange
    selectedRingColor: steelblue
    circleColorByValue: true
    showSelectedValue: true
    initMonth: 2021-01
```

Specify the initial month by relative date
``` tracker
searchType: tag
searchTarget: exercise-pushup
datasetName: PushUp
folder: diary
month:
    startWeekOn:
    threshold: 40
    color: green
    headerMonthColor: orange
    dimNotInMonth: false
    todayRingColor: orange
    selectedRingColor: steelblue
    circleColorByValue: true
    showSelectedValue: true
    initMonth: -47M
```

## Multiple targets
1. Use parameter `datasetName` to specify the name of each dataset
2. Use parameter `dataset` to include dataset we are going to view
3. Use parameter `threshold` to specify the level of achievement (affect the streaks)
4. Click the datasetName label in month view to change the target dataset
``` tracker
searchType: tag
searchTarget: exercise-pushup, meditation
datasetName: PushUp, Meditation
folder: diary
endDate: 2021-01-31
month:
    dataset: 0, 1
    startWeekOn: 'Sun'
    threshold: 40, 0
    color: green
    headerMonthColor: orange
    dimNotInMonth: false
    todayRingColor: orange
    selectedRingColor: steelblue
    circleColorByValue: true
    showSelectedValue: true
```

## Annotations
One target at a time
``` tracker
searchType: tag
searchTarget: exercise-pushup, meditation
datasetName: PushUp, Meditation
folder: diary
endDate: 2021-01-31
month:
    mode: annotation
    startWeekOn: 'Sun'
    threshold: 40, 0
    color: green
    headerMonthColor: orange
    dimNotInMonth: false
    annotation: 💪,🧘‍♂️
    showAnnotationOfAllTargets: false
```

All targets
``` tracker
searchType: tag
searchTarget: exercise-pushup, meditation
datasetName: PushUp, Meditation
folder: diary
endDate: 2021-01-31
month:
    mode: annotation
    startWeekOn: 'Sun'
    threshold: 40, 0
    color: green
    headerMonthColor: orange
    dimNotInMonth: false
    annotation: 💪,🧘‍♂️
    showAnnotationOfAllTargets: true
```

Please also check those search targets in markdown files under folder 'diary'.

## Scaling
fitPanelWidth: true
Click forward backward months and verify it stays scaled
``` tracker
searchType: tag
searchTarget: meditation
datasetName: Meditation
fitPanelWidth: true
folder: diary
endDate: 2021-01-31
month:
```



================================================
FILE: examples/TestCommands.md
================================================
# Test Commands

``` tracker
searchType: tag
searchTarget: weight
folder: /
startDate:
endDate: 2021-01-31
line:
    title: "Line Chart"
    xAxisLabel: Date
    yAxisLabel: Value
```


``` tracker
searchType: tag
searchTarget: weight
folder: /
startDate:
endDate: 2021-01-31
bar:
    title: "Bar Chart"
    xAxisLabel: Date
    yAxisLabel: Value
```


``` tracker
searchType: tag
searchTarget: weight
folder: /
startDate:
endDate: 2021-01-31
summary:
    template: "Average value of tagName is {{average()}}"
    style: "color:white;"
```


================================================
FILE: examples/TestDateFormats.md
================================================
# Test Date Formats

## Test Default Date Formats

Change the default dateFomat on Tracker settings panel and then check the following trackers in the preview mode. Only the one fit dateFomat settings will get rendered.

### dateFomat: YYYY-MM-DD

``` tracker
searchType: tag
searchTarget: weight
folder: diary
startDate: 2021-01-01
endDate: 2021-01-05
line:
    title: Weight Log
    yAxisLabel: Weight
    yAxisUnit: kg
    lineColor: yellow
```

### dateFormat: D-YYYYMMDD

``` tracker
searchType: tag
searchTarget: weight
folder: diary
startDate: 1-20210101
endDate: 5-20210105
line:
    title: Weight Log
    yAxisLabel: Weight
    yAxisUnit: kg
    lineColor: yellow
```

### dateFormat: YYYY-MM-DD-dddd

``` tracker
searchType: tag
searchTarget: weight
folder: diary
startDate: 2021-01-01-Friday
endDate: 2021-01-05-Tuesday
line:
    title: Weight Log
    yAxisLabel: Weight
    yAxisUnit: kg
    lineColor: yellow
```

### dateFormat: YYYY-MM-DD_ddd
``` tracker
searchType: tag
searchTarget: weight
folder: diary
startDate: 2021-01-01_Fri
endDate: 2021-01-05_Tue
line:
    title: Weight Log
    yAxisLabel: Weight
    yAxisUnit: kg
    lineColor: yellow
```

### dateFormat: DD-MM-YYYY

``` tracker
searchType: tag
searchTarget: weight
folder: diary
startDate: 01-01-2021
endDate: 05-01-2021
line:
    title: Weight Log
    yAxisLabel: Weight
    yAxisUnit: kg
    lineColor: yellow
```

### dateFormat: DD.MM.YYYY

``` tracker
searchType: tag
searchTarget: weight
folder: diary
startDate: 01.01.2021
endDate: 05.01.2021
line:
    title: Weight Log
    yAxisLabel: Weight
    yAxisUnit: kg
    lineColor: yellow
```

## ISO-8601 Date Format

``` tracker
searchType: tag
searchTarget: weight
folder: diary
dateFormat: iso-8601
startDate: 2021-01-01T14:53:25+00:00
endDate: 2021-01-05T14:53:25+00:00
line:
    title: Weight Log
    yAxisLabel: Weight
    yAxisUnit: kg
    lineColor: yellow
```

## Test Date Format Prefix and Suffix

The string provided in dateFormatPrefix and dateFormatSuffix will be removed before parsing dates.

### dateFormat: YYYYMMDD with prefix D-

``` tracker
searchType: tag
searchTarget: weight
folder: diary
dateFormat: YYYYMMDD
dateFormatPrefix: D-
startDate: D-20210101
endDate: D-20210105
line:
    title: Weight Log
    yAxisLabel: Weight
    yAxisUnit: kg
    lineColor: yellow
```

### dateFormat: YYYYMMDD with suffix -D

``` tracker
searchType: tag
searchTarget: weight
folder: diary
dateFormat: YYYYMMDD
dateFormatSuffix: -D
startDate: 20210101-D
endDate: 20210105-D
line:
    title: Weight Log
    yAxisLabel: Weight
    yAxisUnit: kg
    lineColor: yellow
```

### Using prefix and suffix with regular expression

Examples of file name
- Jeffrey-20210101-Journal
- Jeffrey-20210102-Diary
- Lucas-2021-0103-Journal
- Lucas-2021-0104-Diary

Data from the same days will be summed up.
``` tracker
searchType: tag
searchTarget: exercise-pushup
folder: diary
dateFormat: YYYYMMDD
dateFormatPrefix: '(Jeffrey-|Lucas-)'
dateFormatSuffix: '(-Journal|-Diary)'
startDate: 20210101
endDate: 20210105
line:
    title: PushUp
    yAxisLabel: Count
    yAxisUnit: times
    lineColor: yellow
```

## Relative Date Input for startDate and endDate

The reference date of the relative date input is 'today' (The current date of your computer), So
- 0d ==> today
- -1d ==> yesterday
- -1w ==> last week
- -1M ==> last month
- -1y ==> last year

Notice!! 
- small 'm' represent 'minute'
- If the date range is less than 1 day, you will get the error message 'No valid date as X value found in notes'.

``` tracker
searchType: tag
searchTarget: weight
folder: diary
startDate: -1M
endDate: 0d
line:
    title: Weight Log
    yAxisLabel: Weight
    yAxisUnit: kg
    lineColor: yellow
```

Please also check those search targets in markdown files under folder 'diary'.



================================================
FILE: examples/TestDvField.md
================================================
# Test dvField

Simple inline field
``` tracker
searchType: dvField
searchTarget: dataviewTarget
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: dvField
    lineColor: green
```

Field with a space
``` tracker
searchType: dvField
searchTarget: Make Progress
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: dvField
    lineColor: yellow
```

Field with a dash line
``` tracker
searchType: dvField
searchTarget: Make-Progress
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: dvField
    lineColor: red
```

Extract the first value from multiple values
``` tracker
searchType: dvField
searchTarget: dataviewTarget1[0]
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: dvField
    lineColor: blue
```

Multiple values separated by '/' (default)
``` tracker
searchType: dvField
searchTarget: dataviewTarget1[0], dataviewTarget1[1]
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: dvField
    lineColor: green, red
```

Multiple values seprated by 'comma'
``` tracker
searchType: dvField
searchTarget: dataviewTarget3[0], dataviewTarget3[1]
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
separator: 'comma'
line:
    title: dvField
    lineColor: green, red
```

Multiple values seprated by '\,'
``` tracker
searchType: dvField
searchTarget: dataviewTarget3[0], dataviewTarget3[1]
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
separator: '\,'
line:
    title: dvField
    lineColor: green, red
```

Use custom multiple value separator
``` tracker
searchType: dvField
searchTarget: dataviewTarget2[0], dataviewTarget2[1]
separator: '@'
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: dvField
    lineColor: green, red
```

Please also check those search targets in markdown files under folder 'diary'.


================================================
FILE: examples/TestEmoji.md
================================================

```tracker
searchType: dvfield
searchTarget: Physical
folder: diary
startDate: 2023-06-04
endDate: 2023-06-11
textValueMap:
    😀: 5
    🙂: 4
    😐: 3
    🙁: 2
    😞: 1
datasetName: 🚹 Physical
line:
	lineColor: orange
	lineWidth: 3
	showLegend: true
	legendPosition: right
```


================================================
FILE: examples/TestExpression.md
================================================
# Test Expression

All examples here using the output type `summary`.
To see examples of `bullet` and `pie`, please check bullet examples and pie examples.

## Operators

### number and number

number \+ number --> number
``` tracker
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
startDate: 2021-01-01
endDate: 2021-01-03
summary:
    template: 'Maximum value: {{10 + 10::i}} <-- should be 20'
```

### Dataset and number

Dataset \+ number --> Dataset
``` tracker
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
startDate: 2021-01-01
endDate: 2021-01-03
summary:
    template: 'Maximum value: {{max() + 10::i}} <-- should be 48 + 10'
```

Dataset \- number --> Dataset
``` tracker
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
startDate: 2021-01-01
endDate: 2021-01-03
summary:
    template: 'Maximum value: {{max() - 2::i}} <-- should be 48 - 2'
```

Dataset \* number --> Dataset
``` tracker
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
startDate: 2021-01-01
endDate: 2021-01-03
summary:
    template: 'Maximum value: {{max() * 2::i}} <-- should be 48 * 2'
```

Dataset / number --> Dataset
``` tracker
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
startDate: 2021-01-01
endDate: 2021-01-03
summary:
    template: 'Maximum value: {{max() / 2::i}} <-- should be 48 / 2'
```

Dataset % number --> Dataset
``` tracker
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
startDate: 2021-01-01
endDate: 2021-01-03
summary:
    template: 'Maximum value: {{max() % 5::i}} <-- should be 48 % 5'
```

### Dataset and Dataset

Dataset1 \+ Dataset2 --> Dataset
==> Dataset[i] = Dataset1[i] + Dataset2[i]
``` tracker
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
startDate: 2021-01-01
endDate: 2021-01-03
summary:
    template: 'Maximum value: {{max(dataset(0) + dataset(0))::i}} <-- should be 48 + 48'
```

## Functions

**If the input dataset is missing, it will use the first available Y dataset found.**

### Functions Accept Dataset and Return a Value

min(Dataset): number
``` tracker
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
endDate: 2021-01-03
summary:
    template: 'Minimum value: {{min()::i}} <-- should be 12'
```

minDate(Dataset): Date
``` tracker
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
endDate: 2021-01-03
summary:
    template: 'Latest date of minimum value: {{minDate()}} <-- should be 2021-01-03'
```

max(Dataset): number
``` tracker
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
endDate: 2021-01-03
summary:
    template: 'Maximum value: {{max()::i}} <-- should be 48'
```

maxDate(Dataset): Date
``` tracker
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
endDate: 2021-01-03
summary:
    template: 'Latest date of maximum value: {{maxDate()}} <-- should be 2021-01-01'
```

startDate(Dataset): Date
``` tracker
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
endDate: 2021-01-03
summary:
    template: 'Start date: {{startDate()}} <-- should be 2021-01-01'
```

endDate(Dataset): Date
``` tracker
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
endDate: 2021-01-03
summary:
    template: 'End date: {{endDate()}} <-- should be 2021-01-03'
```

sum(Dataset): number
``` tracker
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-04
summary:
    template: 'Sum: {{sum()::i}} <-- should be 3'
```

numTargets(Dataset): number
``` tracker
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-04
summary:
    template: 'Number of targets: {{numTargets()::i}} <-- should be 3'
```

numDays(Dataset): number
``` tracker
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-04
summary:
    template: 'Number of days: {{numDays()::i}} <-- should be 4'
```

numDaysHavingData(Dataset): number
``` tracker
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-04
summary:
    template: 'Number of days having data: {{numDaysHavingData()::i}} <-- should be 3'
```

maxStreak(Dataset): number
``` tracker
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-09
summary:
    template: 'Maximum streak: {{maxStreak()::i}} <-- should be 5'
```

maxStreakStart(Dataset): Date
``` tracker
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-09
summary:
    template: 'The start date of maximum streak: {{maxStreakStart()}} <-- should be 2021-01-02'
```

maxStreakEnd(Dataset): Date
``` tracker
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-09
summary:
    template: 'The end date of maximum streak: {{maxStreakEnd()}} <-- should be 2021-01-06'
```

maxBreaks(Dataset): number
``` tracker
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-09
summary:
    template: 'Maximum breaks: {{maxBreaks()::i}} <-- should be 2'
```

maxBreaksStart(Dataset): Date
``` tracker
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-09
summary:
    template: 'The start date of maximum breaks: {{maxBreaksStart()}} <-- should be 2021-01-07'
```

maxBreaksEnd(Dataset): Date
``` tracker
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-09
summary:
    template: 'The end date of maximum breaks: {{maxBreaksEnd()}} <-- should be 2021-01-08'
```

currentStreak(Dataset): number
``` tracker
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-24
summary:
    template: 'Latest streak: {{currentStreak()::i}} <-- should be 1'
```

currentStreakStart(Dataset): Date
``` tracker
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-24
summary:
    template: 'The start date of current streak: {{currentStreakStart()}} <-- should be 2021-01-24'
```

currentStreakEnd(Dataset): Date
``` tracker
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-24
summary:
    template: 'The end date of current streak: {{currentStreakEnd()}} <-- should be 2021-01-24'
```

currentBreaks(Dataset): number
``` tracker
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-22
summary:
    template: 'Current breaks: {{currentBreaks()::i}} <-- should be 1'
```

currentBreaksStart(Dataset): number
``` tracker
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-22
summary:
    template: 'The start date of current breaks: {{currentBreaksStart()}} <-- should be 2021-01-22'
```

currentBreaksEnd(Dataset): Date
``` tracker
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-22
summary:
    template: 'The end date of current breaks: {{currentBreaksEnd()}} <-- should be 2021-01-22'
```

average(Dataset): number
(48+25+12)/3 = 28.33
``` tracker
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
endDate: 2021-01-03
summary:
    template: 'Average value: {{average()::.2f}} <-- should be 28.33'
```

median(Dataset): number
``` tracker
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
endDate: 2021-01-03
summary:
    template: 'Median value: {{median()::i}} <-- should be 25'
```

variance(Dataset): number
https://mathworld.wolfram.com/SampleVariance.html
``` tracker
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
endDate: 2021-01-03
summary:
    template: 'Variance value: {{variance()::.2f}} <-- should be 332.33'
```

### Functions Accept Dataset and Return a Dataset

normalize(Dataset): Dataset
``` tracker
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-04
summary:
    template: 'Set missing values to -1, do normalization then do summation: {{sum( normalize( setMissingValues(dataset(0), -1) ) )::i}} <-- should be 3'
```

setMissingValues(Dataset): Dataset
``` tracker
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-04
summary:
    template: 'Set missing values to -1 then do summation: {{sum( setMissingValues( dataset(0), -1 ) )::i}} <-- should be 2'
```




================================================
FILE: examples/TestFileMeta.md
================================================
# Test FileMeta
Track the size variation of diaries 
``` tracker
searchType: fileMeta
searchTarget: size
folder: diary
endDate: 2021-01-31
line:
    title: File Size Variation
    yAxisLabel: Size
    yAxisUnit: bytes
```

Use file created dates (cDate) as x values
``` tracker
searchType: fileMeta, dvField
searchTarget: cDate, dataviewTarget
xDataset: 0
folder: data
line:
    fillGap: true
```

Use file modified dates (mDate) as x values
``` tracker
searchType: fileMeta, dvField
searchTarget: mDate, dataviewTarget
xDataset: 0
folder: data
line:
    fillGap: true
```

Please also check those search targets in markdown files under folder 'diary' and 'data'.




================================================
FILE: examples/TestFrontmatter.md
================================================
# Test Frontmatter

## Deep Values
deepValue:
    very:
        very:
            very:
                very: 
                    very:
                        deep: 27.4
``` tracker
searchType: frontmatter
searchTarget: deepValue.very.very.very.very.very.deep
folder: diary
endDate: 2021-01-31
line:
    title: Deep Values
```

## Multiple Values
bloodpressure: 184.4/118.8
``` tracker
searchType: frontmatter
searchTarget: bloodpressure[0], bloodpressure[1]
datasetName: systolic, diastolic
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Blood Pressures
    yAxisLabel: BP
    yAxisUnit: mmHg
    lineColor: yellow, red
    showLegend: true
    legendPosition: bottom
```

## Multiple Tags in Front Matter
Extract data of one tag from multiple tags
The default separator in front matter tags is comma (,)
``` tracker
searchType: tag
searchTarget: work_log
folder: diary
accum: true
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Work Log
    yAxisLabel: Count
    pointSize: 5
    pointColor: white
    pointBorderWidth: 2
    pointBorderColor: "#d65d0e"
```

Use the data of two tags
The default separator in front matter tags is comma (,)
``` tracker
searchType: tag
searchTarget: work_log, work_log2
folder: diary
datasetName: Work1, Work2
month:
    initMonth: 2021-01
```

Please also check those search targets in markdown files under folder 'diary'.


================================================
FILE: examples/TestInSentenceFields.md
================================================

```tracker
searchType: frontmatter, dvField
searchTarget: date, count
xDataset: 0
folder: "data"
bullet:
	title: Total Counts
	value: "{{sum()}}"
	range: 1,5,10,20
	rangeColor: darkRed, lightBlue, lightGreen, blue
	showMarker: true
	markerValue: 2
	markerColor: red
```



================================================
FILE: examples/TestLegends.md
================================================
# Test Legends

## Position and Orientation

- Default legendPosition ==> bottom
- Default legendOrientation ==> horizontal

### Right

- legendPosition: right
- Default legendOrientation ==> vertical

``` tracker
searchType: tag
searchTarget: sin[0], sin[1], sin[2], sin[3], sin[4], sin[5], sin[6], sin[7], sin[8]
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Sin Wave
    lineColor: yellow, blue, white, red, black, orange, purple, green, cyan
    showPoint: false
    showLegend: true
    legendPosition: right
```

- legendPosition: right
- legendOrientation: horizontal

``` tracker
searchType: tag
searchTarget: sin[0], sin[1], sin[2], sin[3], sin[4], sin[5], sin[6], sin[7], sin[8]
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Sin Wave
    lineColor: yellow, blue, white, red, black, orange, purple, green, cyan
    showPoint: false
    showLegend: true
    legendPosition: right
    legendOrientation: horizontal
```

### Left

- legendPosition: left
- Default legendOrientation ==> vertical

``` tracker
searchType: tag
searchTarget: sin[0], sin[1], sin[2], sin[3], sin[4], sin[5], sin[6], sin[7], sin[8]
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Sin Wave
    lineColor: yellow, blue, white, red, black, orange, purple, green, cyan
    showPoint: false
    showLegend: true
    legendPosition: left
```

- legendPosition: left
- legendOrientation: horizontal

``` tracker
searchType: tag
searchTarget: sin[0], sin[1], sin[2], sin[3], sin[4], sin[5], sin[6], sin[7], sin[8]
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Sin Wave
    lineColor: yellow, blue, white, red, black, orange, purple, green, cyan
    showPoint: false
    showLegend: true
    legendPosition: left
    legendOrientation: horizontal
```

### Top

- legendPosition: top
- Default legendOrientation ==> horizontal

``` tracker
searchType: tag
searchTarget: sin[0], sin[1], sin[2], sin[3], sin[4], sin[5], sin[6], sin[7], sin[8]
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Sin Wave
    lineColor: yellow, blue, white, red, black, orange, purple, green, cyan
    showPoint: false
    showLegend: true
    legendPosition: top
```

- legendPosition: top
- legendOrientation: vertical
``` tracker
searchType: tag
searchTarget: sin[0], sin[1], sin[2], sin[3], sin[4], sin[5], sin[6], sin[7], sin[8]
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Sin Wave
    lineColor: yellow, blue, white, red, black, orange, purple, green, cyan
    showPoint: false
    showLegend: true
    legendPosition: top
    legendOrientation: vertical
```

### Bottom

- Default legendPosition ==> bottom
- Default legendOrientation ==> horizontal

``` tracker
searchType: tag
searchTarget: sin[0], sin[1], sin[2], sin[3], sin[4], sin[5], sin[6], sin[7], sin[8]
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Sin Wave
    lineColor: yellow, blue, white, red, black, orange, purple, green, cyan
    showPoint: false
    showLegend: true
```

- Default legendPosition ==> bottom
- legendOrientation: vertical

``` tracker
searchType: tag
searchTarget: sin[0], sin[1], sin[2], sin[3], sin[4], sin[5], sin[6], sin[7], sin[8]
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Sin Wave
    lineColor: yellow, blue, white, red, black, orange, purple, green, cyan
    showPoint: false
    showLegend: true
    legendOrientation: vertical
    legendBorderColor: gold
```

## Lines, Points, and Bars

``` tracker
searchType: tag
searchTarget: exercise-pushup
datasetName: weight
folder: diary
endDate: 2021-01-31
line:
    title: PushUp
    yAxisLabel: Count
    lineColor: "#d65d0e"
    showLegend: true
```

``` tracker
searchType: tag
searchTarget: exercise-pushup
datasetName: weight
folder: diary
endDate: 2021-01-31
bar:
    title: PushUp
    yAxisLabel: Count
    barColor: "#458588"
    showLegend: true
```

``` tracker
searchType: tag
searchTarget: exercise-pushup
datasetName: weight
folder: diary
endDate: 2021-01-31
bar:
    title: PushUp
    yAxisLabel: Count
    barColor: "#458588"
    showLegend: true
    legendPosition: right
```

Please also check those search targets in markdown files under folder 'diary'.


================================================
FILE: examples/TestMultipleTargetsMultipleValues.md
================================================
# Test Multiple Targets and Multiple Values

## Data from Different Value-attached Tags
Put value-attached tag data of weight and exercise-push together
``` tracker
searchType: tag
searchTarget: weight, exercise-pushup
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
datasetName: Weight, Pushup
line:
    title: Multiple Targets
    lineColor: yellow, red
    yAxisLocation: left, right
    yAxisLabel: Weight, Count
    showLegend: true
```

## Multiple Values from a Single Multiple-values-attached Tag
Retrieve a single value from a multiple-values-attached tag
``` tracker
searchType: tag
searchTarget: sin[0]
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Sin Wave
    lineColor: yellow
    showLegend: false
```

Retrieve values from a multiple-values-attached tag
``` tracker
searchType: tag
searchTarget: sin[0], sin[1], sin[2], sin[3], sin[4], sin[5], sin[6], sin[7], sin[8]
folder: diary
datasetName: Sin1, Sin2, Sin3, Sin4, Sin5, Sin6, Sin7, Sin8, Sin9
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Sin Wave
    lineColor: yellow, blue, white, red, black, orange, purple, green, cyan
    showPoint: false
    showLegend: true
    legendPosition: right
    legendOrientation: vertical
```

## Multiple Values from Frontmatter
Multiple values separated by slash (/)
``` tracker
searchType: frontmatter
searchTarget: bloodpressure[0], bloodpressure[1]
folder: diary
datasetName: systolic, diastolic
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Blood Pressure
    lineColor: yellow, red
    showLegend: true
```

Multiple values separated by comma (,)
``` tracker
searchType: frontmatter
searchTarget: bloodpressure1[0], bloodpressure1[1]
folder: diary
datasetName: systolic, diastolic
startDate: 2021-01-01
endDate: 2021-01-31
separator: comma
line:
    title: Blood Pressure
    lineColor: yellow, red
    showLegend: true
```

Values from array
``` tracker
searchType: frontmatter
searchTarget: bloodpressure2[0], bloodpressure2[1]
folder: diary
datasetName: systolic, diastolic
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Blood Pressure
    lineColor: yellow, red
    showLegend: true
```

Values from nested keys
``` tracker
searchType: frontmatter
searchTarget: bp.systolic, bp.diastolic
folder: diary
datasetName: systolic, diastolic
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Blood Pressure
    lineColor: yellow, red
    showLegend: true
```

## Multiple Values in Text
Use searchType 'dvField' with separators in the target instead
``` tracker
searchType: text
searchTarget: 'dataviewTarget2::\s+(?<value>[\-]?[0-9]+[\.][0-9]+|[\-]?[0-9]+)\s+@\s+([\-]?[0-9]+[\.][0-9]+|[\-]?[0-9]+), dataviewTarget2::\s+([\-]?[0-9]+[\.][0-9]+|[\-]?[0-9]+)\s+@\s+(?<value>[\-]?[0-9]+[\.][0-9]+|[\-]?[0-9]+)'
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Dataview Data
    yAxisLabel: Count
    lineColor: red, yellow
    yMin: 0
```


## Multiple Values in dvField (Dataview inline field)
Extract the first value in dataview inline field
``` tracker
searchType: dvField
searchTarget: dataviewTarget1[0]
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: dvField
```

Multiple Values in dataview inline field
``` tracker
searchType: dvField
searchTarget: dataviewTarget1[0], dataviewTarget1[1]
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: dvField
    lineColor: green, red
```

Multiple values seprated by 'comma'
``` tracker
searchType: dvField
searchTarget: dataviewTarget3[0], dataviewTarget3[1]
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
separator: comma
line:
    title: dvField
    lineColor: green, red
```

Use custom multiple value separator
``` tracker
searchType: dvField
searchTarget: dataviewTarget2[0], dataviewTarget2[1]
separator: '@'
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: dvField
    lineColor: green, red
```

## Multiple Values in Table

Use first column as X dataset. Second column posses multiple values in each cell.
``` tracker
searchType: table
searchTarget: data/Tables[1][0], data/Tables[1][1][0], data/Tables[1][1][1]
xDataset: 0
separator: "@"
line:
    yAxisLocation: none, left, right
    lineColor: none, yellow, red
```

Please also check those search targets in markdown files under folder 'diary' and 'data'.



================================================
FILE: examples/TestPieChart.md
================================================
# Test Pie Chart

Expressions could be used in parameter `data`, `label`, and `extLabel`.

## Manual Input Data

### Numbers as Data
Pie chart with labels showing percentages
``` tracker
searchType: task.done, task.notdone
searchTarget: Say I love you, Say I love you
pie:
    title: Pie Chart
    label: '{{2/30*100}}%, {{4/30*100}}%, {{6/30*100}}%, {{8/30*100}}%, {{10/30*100}}%'
    data: 2, 4, 6, 8, 10
    dataColor: '#4daf4a,#377eb8,#ff7f00,#984ea3,#e41a1c'
    ratioInnerRadius: 0.0
```

### Arithmetic

Pie chart with labels showing percentages
``` tracker
searchType: task.done, task.notdone
searchTarget: Say I love you, Say I love you
datasetName: Done, NotDone
pie:
    title: Arithmetic
    data: '{{1 + 1}}, {{2 * 2}}, {{12/ 2}}, {{1+(2+3*2)-1}}, {{27%17}}'
    label: '{{2/30*100}}%, {{4/30*100}}%, {{6/30*100}}%, {{8/30*100}}%, {{10/30*100}}%'
    dataColor: '#4daf4a,#377eb8,#ff7f00,#984ea3,#e41a1c'
    ratioInnerRadius: 0.5
```

### Legend

Use parameter `dataName` for the name on the legend
``` tracker
searchType: task.done, task.notdone
searchTarget: Say I love you, Say I love you
datasetName: Done, NotDone
pie:
    title: Manual Input Data
    label: '{{2/30*100}}%, {{4/30*100}}%, {{6/30*100}}%, {{8/30*100}}%, {{10/30*100}}%'
    data: '2, 4, 6, 8, 10'
    dataColor: '#4daf4a,#377eb8,#ff7f00,#984ea3,#e41a1c'
    dataName: Data1, Data2, Data3, Data4, Data5
    ratioInnerRadius: 0.5
    showLegend: true
    legendPosition: right
    legendOrientation: vertical	
```

### Default data colors
``` tracker
searchType: task.done, task.notdone
searchTarget: Say I love you, Say I love you
pie:
    title: Pie Chart
    label: '{{2/30*100}}%, {{4/30*100}}%, {{6/30*100}}%, {{8/30*100}}%, {{10/30*100}}%'
    data: 2, 4, 6, 8, 10
    ratioInnerRadius: 0.0
```

## Data from Notes

Using function dataset() to get Dataset then use function sum() to get the summation
``` tracker
searchType: task.done, task.notdone
searchTarget: Say I love you, Say I love you
folder: diary
datasetName: Done, NotDone
pie:
    title: Love is Action
    data: '{{sum(dataset(0))}},{{sum(dataset(1))}}'
    dataColor: '#4daf4a,#377eb8'
    label: Say👍,Not Say💔
    ratioInnerRadius: 0.3
```

Summary
``` tracker
searchType: task.done, task.notdone
searchTarget: Say I love you, Say I love you
folder: diary
summary:
    template: "How many days I said love: {{sum(dataset(0))::i}}\nHow many days I didn't say love: {{sum(dataset(1))::i}}"
```

## External Labels
``` tracker
searchType: task.done, task.notdone
searchTarget: Say I love you, Say I love you
datasetName: Done, NotDone
pie:
    label: '{{0.5/28.5*100}}%, {{4/28.5*100}}%, {{6/28.5*100}}%, {{8/28.5*100}}%, {{10/28.5*100}}%'
    extLabel: 'DataA {{0.5/28.5*100}}%, DataB, DataC, DataD, DataE'
    data: '0.5, 4, 6, 8, 10'
    dataColor: '#4daf4a,#377eb8,#ff7f00,#984ea3,#e41a1c'
    ratioInnerRadius: 0.6
```

1. Label for the first data was hidden because the fraction of it is too small (less than 0.03, 3%).
2. showExtLabelOnlyIfNoLabel was set to true, thus the external label of the first data was shown due to the hidden label.
``` tracker
searchType: task.done, task.notdone
searchTarget: Say I love you, Say I love you
datasetName: Done, NotDone
pie:
    label: '{{0.5/28.5*100}}%, B {{4/28.5*100}}%, C {{6/28.5*100}}%, D {{8/28.5*100}}%, E {{10/28.5*100}}%'
    extLabel:  'A {{0.5/28.5*100}}%, {{4/28.5*100}}%, {{6/28.5*100}}%, {{8/28.5*100}}%, {{10/28.5*100}}%'
    data: '0.5, 4, 6, 8, 10'
    dataColor: '#4daf4a,#377eb8,#ff7f00,#984ea3,#e41a1c'
    ratioInnerRadius: 0.4
    hideLabelLessThan: 0.03
    showExtLabelOnlyIfNoLabel: true
```

When there are multiple external labels, make sure they won't overlap with each other
``` tracker
searchType: task.done, task.notdone
searchTarget: Say I love you, Say I love you
datasetName: Done, NotDone
pie:
    label: '{{0.5/11*100}}%, B {{0.4/11*100}}%, C {{0.1/11*100}}%, D {{8/11*100}}%, E {{9.7/11*100}}%, F {{0.3/28.5*100}}'
    extLabel:  'A {{0.5/11*100}}%, B {{0.4/11*100}}%, C {{0.1/11*100}}%, D {{8/11*100}}%, E {{9.7/11*100}}, F {{0.3/11*100}}%'
    data: '0.5, 0.4, 0.1, 8, 9.7, 0.3'
    dataColor: '#4daf4a,#377eb8,#ff7f00,#984ea3,#e41a1c,#aaaaaa'
    ratioInnerRadius: 0.4
    hideLabelLessThan: 0.03
    showExtLabelOnlyIfNoLabel: true
```



================================================
FILE: examples/TestRegex.md
================================================
# Search Text using Regular Expression

**Important**!!
1. Use single quotes to wrap the regular expression, or use double quotes with all back slashes (escape characters) duplicated.
2. You can make your own expression, or find a suitable one from website like regex101.
3. Use a named group "(?\<value\>XXXXXX)" in your expression if you need values be retrieved from text.

## Count Occurencies (No Value)
### Occurencies of Email
Regex for searching simple emails
``` tracker
searchType: text
searchTarget: '.+\@.+\..+'
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Email Occurencies
    yAxisLabel: Count
    lineColor: yellow
    yAxisTickInterval: 1.0
    yAxisTickLabelFormat: i
    yMin: 0
    yMax: 5
```

``` tracker
searchType: text
searchTarget: '.+\@.+\..+'
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
summary:
    template: "Total number of emails found: {{sum()::i}}"
    style: "font-size:20px;color:red;margin-left: 50px;margin-top:00px;"
```

## Count Values
### Weightlifting Tracker 
Track text in format "weightlifting: 10".
Regex for searching value-attached texts
``` tracker
searchType: text
searchTarget: 'weightlifting:\s+(?<value>[\-]?[0-9]+[\.][0-9]+|[\-]?[0-9]+)'
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Weight Lifting
    yAxisLabel: Count
    lineColor: yellow
```

### Dataview Compatible Tracker
Use searchType 'dvField' instead
``` tracker
searchType: text
searchTarget: 'dataviewTarget::\s+(?<value>[\-]?[0-9]+[\.][0-9]+|[\-]?[0-9]+)'
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Dataview Data
    yAxisLabel: Count
    lineColor: red
    yMin: 0
```

Use searchType 'dvField' with separators in the target instead
``` tracker
searchType: text
searchTarget: 'dataviewTarget2::\s+(?<value>[\-]?[0-9]+[\.][0-9]+|[\-]?[0-9]+)\s+@\s+([\-]?[0-9]+[\.][0-9]+|[\-]?[0-9]+), dataviewTarget2::\s+([\-]?[0-9]+[\.][0-9]+|[\-]?[0-9]+)\s+@\s+(?<value>[\-]?[0-9]+[\.][0-9]+|[\-]?[0-9]+)'
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Dataview Data
    yAxisLabel: Count
    lineColor: red, yellow
    yMin: 0
```


Please also check those search targets in markdown files under folder 'diary'.



================================================
FILE: examples/TestRelativeStartEndDate.md
================================================
# Test Relative startDate and endDate

``` tracker
searchType: tag
searchTarget: exercise-pushup
folder: diary
startDate: -48M
endDate: -46M
line:
    title: PushUp
    yAxisLabel: Count
    lineColor: "#d65d0e"
    yAxisTickInterval: 2
```


================================================
FILE: examples/TestScalingAndPositioning.md
================================================
# Test Scaling and Positioning
## Scaling the chart
Scaling factor 0.5
``` tracker
searchType: tag
searchTarget: exercise-pushup
folder: diary
endDate: 2021-01-31
fixedScale: 0.5
fitPanelWidth: false
line:
    title: PushUp
    yAxisLabel: Count
    lineColor: "#d65d0e"
```

Scaling factor 1.5
``` tracker
searchType: tag
searchTarget: exercise-pushup
folder: diary
endDate: 2021-01-31
fixedScale: 1.5
fitPanelWidth: false
line:
    title: PushUp
    yAxisLabel: Count
    lineColor: "#d65d0e"
```

## Fitting the chart to the panel width
``` tracker
searchType: tag
searchTarget: exercise-pushup
folder: diary
endDate: 2021-01-31
fixedScale: 1.0
fitPanelWidth: true
line:
    title: PushUp
    yAxisLabel: Count
    lineColor: "#d65d0e"
```

## Chart Positioning
margin: top right bottom left
``` tracker
searchType: tag
searchTarget: exercise-pushup
folder: diary
endDate: 2021-01-31
fixedScale: 1.0
fitPanelWidth: false
margin: 10, 10, 10, 0
line:
    title: PushUp
    yAxisLabel: Count
    lineColor: "#d65d0e"
```

``` tracker
searchType: tag
searchTarget: exercise-pushup
folder: diary
endDate: 2021-01-31
fixedScale: 1.0
fitPanelWidth: false
margin: 10, 10, 10, 50
line:
    title: PushUp
    yAxisLabel: Count
    lineColor: "#d65d0e"
```

``` tracker
searchType: tag
searchTarget: exercise-pushup
folder: diary
endDate: 2021-01-31
fixedScale: 1.0
fitPanelWidth: false
margin: 10, 10, 10, 100
line:
    title: PushUp
    yAxisLabel: Count
    lineColor: "#d65d0e"
```

``` tracker
searchType: tag
searchTarget: exercise-pushup
folder: diary
endDate: 2021-01-31
fixedScale: 1.0
fitPanelWidth: false
margin: 10, 10, 10, 150
line:
    title: PushUp
    yAxisLabel: Count
    lineColor: "#d65d0e"
```

Please also check those search targets in markdown files under folder 'diary'.


================================================
FILE: examples/TestSpecifiedFiles.md
================================================
# Test Specified Files

## Collect Data from the Specified Files Only
``` tracker
searchType: frontmatter, dvField
searchTarget: date, dataviewTarget
xDataset: 0
file: data/data1, data/data2, data/data3
specifiedFilesOnly: true
line:
```

## Collect Data from the Linked Files Only
Count the MTG mana cost in linked files
``` tracker
searchType: fileMeta, text
searchTarget: 'cDate, {W}, {R}, {G}, {B}, {(?<value>[0-9]+)}'
fileContainsLinkedFiles: data/MTG-Deck-1
specifiedFilesOnly: true
fileMultiplierAfterLink: 'x(?<value>[0-9]+)'
xDataset: 0
pie:
    label: '{{sum(dataset(1))::i}},{{sum(dataset(2))::i}},{{sum(dataset(3))::i}},{{sum(dataset(4))::i}},{{sum(dataset(5))::i}}'
    data: '{{sum(dataset(1))}},{{sum(dataset(2))}}, {{sum(dataset(3))}}, {{sum(dataset(4))}},{{sum(dataset(5))}}'
    dataColor: lightgray, firebrick, yellowgreen, lightblue, gray
```


================================================
FILE: examples/TestSummary.md
================================================
# Test Summary

## Multiple Lines

``` tracker
searchType: tag
searchTarget: weight
folder: diary
summary:
    template: "Minimum: {{min()}}kg\nMaximum: {{max()}}kg\nMedian: {{median()}}kg\nAverage: {{average()}}kg"
```

## Styling

``` tracker
searchType: text
searchTarget: ⭐
folder: diary
summary:
    template: "I have {{sum()}} stars in total."
    style: "font-size:20px;color:yellow;margin-left: 50px;margin-top:00px;"
```

``` tracker
searchType: frontmatter
searchTarget: sleptwell
folder: diary
summary:
    template: "I once slept well for {{maxStreak()::i}} days in a row!"
```
## Using Expressions

Please check expression examples for more examples.


================================================
FILE: examples/TestTabCharacters.md
================================================
# Test Tab Characters

Tab characters will be replaced by numbers of spaces according to the tabSize defined in your editor settings

## Single Tab
``` tracker
searchType: tag
searchTarget: exercise-pushup
folder: diary
endDate: 2021-01-31
line:
	title: PushUp
    yAxisLabel: Count
    lineColor: "#d65d0e"
```

## Multiple Tabs

``` tracker
searchType: tag
searchTarget: exercise-pushup
folder: diary
endDate: 2021-01-31
line:
	title: PushUp
    yAxisLabel: Count
	lineColor: "#d65d0e"
```








================================================
FILE: examples/TestTable.md
================================================
# Test Table

## Line Chart
Use first column as X dataset , and second and third columns as Y values
``` tracker
searchType: table
searchTarget: data/Tables[0][0], data/Tables[0][1], data/Tables[0][2]
xDataset: 0
line:
    yAxisLocation: none, left, right
    lineColor: none, yellow, red
    showLegend: true
```

Use first column as X dataset , and third and forth columns as Y values
``` tracker
searchType: table
searchTarget: data/Tables[0][0], data/Tables[0][2], data/Tables[0][3]
xDataset: 0
line:
    yAxisLocation: none, left, right
    lineColor: none, yellow, red
    showLegend: true
    legendPosition: right
```

Use first column as X dataset. Second column posses multiple values in each cell.
``` tracker
searchType: table
searchTarget: data/Tables[1][0], data/Tables[1][1][0], data/Tables[1][1][1]
xDataset: 0
separator: "@"
line:
    yAxisLocation: none, left, right
    lineColor: none, yellow, red
    showLegend: true
    legendPosition: right
```

### Tables with Defects
``` tracker
searchType: table
searchTarget: data/Tables[2][0], data/Tables[2][1]
xDataset: 0
line:
    lineColor: none, yellow
```

Wrong date format in Table
``` tracker
searchType: table
searchTarget: data/Tables[3][0], data/Tables[3][1]
xDataset: 0
line:
    lineColor: none, yellow
```

## Month View

``` tracker
searchType: table
searchTarget: data/Tables[0][0], data/Tables[0][1], data/Tables[0][2], data/Tables[0][3]
xDataset: 0
datasetName: null, Jeffrey, Lucas, Anne
month:
    startWeekOn: 'Sun'
    threshold: 0, 62.2, 20.8, 18.2
    color: green
    headerMonthColor: orange
    dimNotInMonth: false
    todayRingColor: orange
    selectedRingColor: steelblue
    circleColorByValue: true
    showSelectedValue: true
```

Please also check those search targets in markdown file /data/Tables.



================================================
FILE: examples/TestTask.md
================================================
# Test Task

## Summary
### All Tasks
Collect all tasks matched `searchTarget`
``` tracker
searchType: task
searchTarget: Say I love you
folder: diary
summary:
    template: "Total count: {{sum()}}"
```

### All Tasks
Collect all tasks matched `searchTarget`
``` tracker
searchType: task.all
searchTarget: Say I love you
folder: diary
summary:
    template: "Total count: {{sum()}}"
```

### Task Done
Collect all tasks done matched `searchTarget`
``` tracker
searchType: task.done
searchTarget: Say I love you
folder: diary
summary:
    template: "How many days I said: {{sum()}}"
```

### Task Not Done
Collect all tasks not-done matched `searchTarget`
``` tracker
searchType: task.notdone
searchTarget: Say I love you
folder: diary
summary:
    template: "How many days I didn't say: {{sum()}}"
```

## Month View
See tasks done in month view
``` tracker
searchType: task.done
searchTarget: Say I love you
folder: diary
datasetName: Love
endDate: 2021-01-31
month:
    color: tomato
    headerMonthColor: orange
    todayRingColor: orange
    selectedRingColor: steelblue
    showSelectedValue: false
```

task.done and task.notdone
``` tracker
searchType: task.done, task.notdone
searchTarget: Say I love you, Say I love you
folder: diary
datasetName: Good Lover, Bad Lover
endDate: 2021-01-31
month:
    color: tomato
    headerMonthColor: orange
    todayRingColor: orange
    selectedRingColor: steelblue
    showSelectedValue: false
```


================================================
FILE: examples/TestTextValueMap.md
================================================
# Test textValueMap

## Mood
``` tracker
searchType: frontmatter
searchTarget: "mood"
folder: diary
endDate: 2021-01-31
textValueMap:
    😀: 5
    🙂: 4
    😐: 3
    🙁: 2
    😞: 1
line:
    title: "Mood"
    yAxisLabel: Mood
    lineColor: "#d65d0e"
    yAxisTickInterval: 1
    yAxisTickLabelFormat: i
    yMin: 0
```



================================================
FILE: examples/TestTimeValues.md
================================================
# Test Time Values

## From frontmatter
Clock-In & Clock-Out from front matter
``` tracker
searchType: frontmatter
searchTarget: clock-in, clock-out
endDate: 2021-01-15
folder: diary
datasetName: Clock-In, Clock-Out
line:
    title: "Working Hours"
    yAxisLabel: "Time (24h)"
    reverseYAxis: true
    lineColor: yellow, red
    showPoint: true
    showLegend: true
```

Sleep time separated by / from front matter
``` tracker
searchType: frontmatter
searchTarget: sleep[0], sleep[1]
endDate: 2021-01-15
folder: diary
valueShift: -24:00, 00:00
datasetName: Sleep, WakeUp
line:
    title: "Sleep"
    yAxisLabel: "Time (24h)"
    lineColor: yellow, red
    showPoint: true
    showLegend: true
```

## From dvField
Clock-In & Clock-Out from dvField
time granularity to one second
``` tracker
searchType: dvField
searchTarget: clock-in, clock-out
endDate: 2021-01-15
folder: diary
datasetName: Clock-In, Clock-Out
line:
    title: "Working Hours"
    yAxisLabel: "Time (24h)"
    reverseYAxis: true
    lineColor: yellow, red
    showPoint: true
    showLegend: true
```

Sleep time separated by / from dvField
``` tracker
searchType: dvField
searchTarget: sleep[0], sleep[1]
endDate: 2021-01-15
folder: diary
valueShift: -24:00, 00:00
datasetName: Sleep, WakeUp
line:
    title: "Sleep"
    yAxisLabel: "Time (24h)"
    lineColor: yellow, red
    showPoint: true
    showLegend: true
```

Please also check those search targets in markdown files under folder 'diary'.


================================================
FILE: examples/TestWordCounting.md
================================================
# Test Word Counting


## Word counts of daily notes
``` tracker
searchType: fileMeta
searchTarget: numWords, numChars
folder: diary
startDate: 2021-01-01
endDate: 2021-01-05
datasetName: words, chars
line:
    title: Word Counting
    yAxisLocation: left, right
    yAxisLabel: Words, Characters
    lineColor: red, yellow
    showLegend: true
```

``` tracker
searchType: fileMeta
searchTarget: numWords
folder: diary
startDate: 2021-01-01
endDate: 2021-01-05
summary:
    template: 'Total number of words: {{sum()}}'
```

``` tracker
searchType: fileMeta
searchTarget: numChars
folder: diary
startDate: 2021-01-01
endDate: 2021-01-05
summary:
    template: 'Total number of characters: {{sum()}}'
```

## Word counts of all notes
Use file creation dates as x values then sum the counts up
``` tracker
searchType: fileMeta
searchTarget: cDate, numWords
xDataset: 0
folder: /
summary:
    template: "Total word count: {{sum(dataset(1))}}"
```




================================================
FILE: examples/TestXDataset.md
================================================
# Test X Dataset

Use file created dates (cDate) as x values
``` tracker
searchType: fileMeta, dvField
searchTarget: cDate, dataviewTarget
xDataset: 0
folder: data
line:
    fillGap: true
```

Use dates from front matter as x values
``` tracker
searchType: frontmatter, dvField
searchTarget: date, dataviewTarget
xDataset: 0
folder: data
line:
    title: Dataview Inline Field
    fillGap: true
```

Use dates from date-attached tags as x values
``` tracker
searchType: tag, dvField
searchTarget: date, dataviewTarget
xDataset: 0
folder: data
line:
    title: Dataview Inline Field
    fillGap: true
```

Use dates from Dataview inline fields as x values
``` tracker
searchType: dvField, dvField
searchTarget: date, dataviewTarget
xDataset: 0
folder: data
line:
    title: Dataview Inline Field
    fillGap: true
```

Use dates from formatted text as x values
``` tracker
searchType: text, dvField
searchTarget: 'Today\sis\s(?<value>([0-9]{4})-([0-9]{2})-([0-9]{2})), dataviewTarget'
xDataset: 0
folder: data
line:
    title: Dataview Inline Field
    fillGap: true
```

Please also check those search targets in markdown files under folder 'data'.



================================================
FILE: examples/WeightTracker.md
================================================
# Weight Tracker

``` tracker
searchType: tag
searchTarget: weight
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
aspectRatio: 20:9
fitPanelWidth: 1
line:
    title: Weight Log
    yAxisLabel: Weight
    yAxisUnit: kg
    lineColor: yellow
```

## Summary
``` tracker
searchType: tag
searchTarget: weight
folder: diary
summary:
    template: "First: {{first()}}kg\nLast: {{last()}}kg\nMinimum: {{min()}}kg\nMaximum: {{max()}}kg\nMedian: {{median()}}kg\nAverage: {{average()}}kg"
```

``` tracker
searchType: tag
searchTarget: weight
folder: diary
endDate: 2021-01-31
line:
    title: Weight Log
    yAxisLabel: Weight
    yAxisUnit: kg
    showPoint: false
    lineColor: "#b16286"
```

Please also check those search targets in markdown files under folder 'diary'.












================================================
FILE: examples/WikiTracker.md
================================================
# Wiki Tracker

wiki --> Try parse the display text first, if it does not exist, parse the link text
wiki.link --> Parse the link text
wiki.display --> Parse the display text

In the example notes, we have
[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

## wiki.link
``` tracker
searchType: wiki.link
searchTarget: todo_work
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
summary:
    template: '{{sum()::i}}'
```

## wiki.display
``` tracker
searchType: wiki.display
searchTarget: To
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
summary:
    template: '{{sum()::i}}'
```


Please also check those search targets in markdown files under folder 'diary'.



================================================
FILE: examples/data/data1.md
================================================
---
date: 2021-01-01
---

#date:2021-01-01
date:: 2021-01-01

dataviewTarget:: 50

Today is 2021-01-01


================================================
FILE: examples/data/data2.md
================================================
---
date: 2021-01-02
---

#date:2021-01-03
date:: 2021-01-05

dataviewTarget:: 30

Today is 2021-01-10


================================================
FILE: examples/data/data3.md
================================================
---
date: 2021-01-03
---

#date:2021-01-05
date:: 2021-01-09

dataviewTarget:: 80

Today is 2021-01-20


================================================
FILE: examples/data/In-Sentence-Fields.md
================================================
---
date: 2021-01-05
---

I am [count:: 1] inline
So am (count::2) I
count:: 3
| count:: 4 |
|count:: 5|


================================================
FILE: examples/data/MTG-Card-1.md
================================================


{R}{R}


================================================
FILE: examples/data/MTG-Card-2.md
================================================


{B}{B}{R}{2}


================================================
FILE: examples/data/MTG-Card-3.md
================================================


{G}{G}{G}{G}{G}{0}


================================================
FILE: examples/data/MTG-Card-4.md
================================================


{W}


================================================
FILE: examples/data/MTG-Deck-1.md
================================================


[[MTG-Card-1]] x1
[[MTG-Card-2]] x2
[[MTG-Card-3]] x2
[[MTG-Card-4]] x5


================================================
FILE: examples/data/Set-FileDates.ps1
================================================
(Get-Item "./data1.md").CreationTime=("25 May 2021 17:00:00")
(Get-Item "./data2.md").CreationTime=("27 May 2021 17:00:00")
(Get-Item "./data3.md").CreationTime=("29 May 2021 17:00:00")
(Get-Item "./data1.md").LastWriteTime=("25 May 2021 17:00:00")
(Get-Item "./data2.md").LastWriteTime=("27 May 2021 17:00:00")
(Get-Item "./data3.md").LastWriteTime=("29 May 2021 17:00:00")


================================================
FILE: examples/data/Tables.md
================================================
# Tables

## Weight Table
 Date | Jeffrey (kg) | Lucas (kg) | Anne (kg) |
| - | - | - | - |
| 2021-05-01 | 60.0 | 20.1 | 18.2
 2021-05-02 | 62.1 | 20.5 | 18.1 |
| 2021-05-03 | 62.2 | 20.3 | 18.3
| 2021-05-04 | 62.3 | 20.4 | 18.2 |
 2021-05-05 | 62.2 | 20.2 | 18.4
| [[2021-05-06]] | 62.4 | 21.0 | 18.4
| 2021-05-07 | 62.6 | 20.9 | 18.3 |
| 2021-05-08 | 62.3 | 20.9 | 18.2
| [[2021-05-09]] | 62.2 | 20.3 | 18.5
| [[2021-05-10]] | 62.1 | 20.8 | 18.9


## Running Records

 Date | km @ min/km |
| - | - | 
| 2021-05-01 | 5.32 @ 6.32 |
 2021-05-02 | 5.0 @ 6.30
| 2021-05-03 | 5.22 @ 6.12
| 2021-05-04 | 5.10 @ 6.10 |
 2021-05-05 | 5.35 @ 6.05
| 2021-05-06 | 5.45 @ 6.05 |
| 2021-05-07 | 5.73 @ 5.05 | 
| 2021-05-08 | 6.25 @ 5.55 | 
| 2021-05-09 | 6.25 @ 5.45 | 
| 2021-05-10 | 6.35 @ 5.75 | 

## Tables with Defects
More columns than need, graph still rendered

 Date | Weight (kg) | 
| - | - | - 
| 2021-05-01 | 60.0 | 20.1 |
 2021-05-02 | 62.1 | 20.5 
 | 2021-05-03 | 62.2 | 20.3 |
 
The row with wrong date format will be skipped
 
  Date | Weight (kg) | 
| - | - | - 
| not a date | 60.0 | 20.1 |
 2021-05-02 | 62.1 | 20.5 
  | 2021-05-03 | 62.2 | 20.3 |
  
All dates are invalid, leads to an error message
 
  Date | Weight (kg) | 
| - | - | - 
| not a date | 60.0 | 20.1 |
 not a date | 62.1 | 20.5 
  | not a date | 62.2 | 20.3 |


================================================
FILE: examples/diary/01-01-2021.md
================================================
---
tags: work_log
mood: 6
---

#weight:66.9kg

#exercise-pushup:33
#exercise-plank:85sec


⭐⭐⭐⭐

#finance/bank1:-2.7USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com





================================================
FILE: examples/diary/01.01.2021.md
================================================
---
tags: work_log
mood: 6
---

#weight:66.9kg

#exercise-pushup:33
#exercise-plank:85sec


⭐⭐⭐⭐

#finance/bank1:-2.7USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com





================================================
FILE: examples/diary/02-01-2021.md
================================================
---
tags: 
mood: 5
---

#weight:69.4kg

#exercise-pushup:30
#exercise-plank:93sec


⭐⭐

#finance/bank1:-3.1USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 14




================================================
FILE: examples/diary/02.01.2021.md
================================================
---
tags: 
mood: 5
---

#weight:69.4kg

#exercise-pushup:30
#exercise-plank:93sec


⭐⭐

#finance/bank1:-3.1USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 14




================================================
FILE: examples/diary/03-01-2021.md
================================================
---
tags: 
mood: 5
---

#weight:69.3kg

#exercise-pushup:39
#exercise-plank:98sec


⭐

#finance/bank1:-2.2USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker+1@gmail.com

weightlifting: 14




================================================
FILE: examples/diary/03.01.2021.md
================================================
---
tags: 
mood: 5
---

#weight:69.3kg

#exercise-pushup:39
#exercise-plank:98sec


⭐

#finance/bank1:-2.2USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker+1@gmail.com

weightlifting: 14




================================================
FILE: examples/diary/04-01-2021.md
================================================
---
tags: work_log
mood: 7
---

#weight:70.6kg

#exercise-pushup:41
#exercise-plank:87sec


⭐

#finance/bank1:-3.3USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 11




================================================
FILE: examples/diary/04.01.2021.md
================================================
---
tags: work_log
mood: 7
---

#weight:70.6kg

#exercise-pushup:41
#exercise-plank:87sec


⭐

#finance/bank1:-3.3USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 11




================================================
FILE: examples/diary/05-01-2021.md
================================================
---
tags: work_log
mood: 8
---

#weight:60.2kg

#exercise-pushup:50
#exercise-plank:55sec

#meditation

⭐⭐⭐

#finance/bank1:-2.2USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@yahoo.com

weightlifting: 20




================================================
FILE: examples/diary/05.01.2021.md
================================================
---
tags: work_log
mood: 8
---

#weight:60.2kg

#exercise-pushup:50
#exercise-plank:55sec

#meditation

⭐⭐⭐

#finance/bank1:-2.2USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@yahoo.com

weightlifting: 20




================================================
FILE: examples/diary/1-20210101.md
================================================
---
tags: work_log
mood: 6
---

#weight:66.9kg

#exercise-pushup:33
#exercise-plank:85sec


⭐⭐⭐⭐

#finance/bank1:-2.7USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com





================================================
FILE: examples/diary/2-20210102.md
================================================
---
tags: 
mood: 5
---

#weight:69.4kg

#exercise-pushup:30
#exercise-plank:93sec


⭐⭐

#finance/bank1:-3.1USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 14




================================================
FILE: examples/diary/2021-01-01-Friday.md
================================================
---
tags: work_log
mood: 6
---

#weight:66.9kg

#exercise-pushup:33
#exercise-plank:85sec


⭐⭐⭐⭐

#finance/bank1:-2.7USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com





================================================
FILE: examples/diary/2021-01-01.md
================================================
---
tags: work_log, work_log2
mood: 🙁
bloodpressure: 184.4/118.8
bloodpressure1: 184.4, 118.8
bloodpressure2: [184.4, 118.8]
bp:
    systolic: 184.4
    diastolic: 118.8
clock-in: 10:45
clock-out: 20:51
sleep: 10:11 pm/7:5 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 27.4
randchar: D
---

#weight:74.1kg

#exercise-pushup:31
#exercise-plank:109sec





#finance/bank1:-3.5USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker+1@gmail.com

weightlifting: 18

dataviewTarget:: 48
- Make Progress:: 29
- Make-Progress:: 88
dataviewTarget1:: 48/29
dataviewTarget2:: 29 @ 88
dataviewTarget3:: 29, 88

clock-in:: 10:45:29
clock-out:: 20:51:29

sleep:: 10:11 pm/7:5 am

#sin:0.00000/0.20791/0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452

#sinsquare:0.00000/0.04323/0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907

- [x] Say I love you




================================================
FILE: examples/diary/2021-01-02-Saturday.md
================================================
---
tags: 
mood: 5
---

#weight:69.4kg

#exercise-pushup:30
#exercise-plank:93sec


⭐⭐

#finance/bank1:-3.1USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 14




================================================
FILE: examples/diary/2021-01-02.md
================================================
---
tags: 
mood: 🙁
bloodpressure: 180.8/120.6
bloodpressure1: 180.8, 120.6
bloodpressure2: [180.8, 120.6]
bp:
    systolic: 180.8
    diastolic: 120.6
clock-in: 8:7
clock-out: 20:10
sleep: 9:37 pm/7:57 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 13.3
randchar: D
---

#weight:76.2kg

#exercise-pushup:46
#exercise-plank:52sec

#meditation




#finance/bank1:-3.5USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]


weightlifting: 13

dataviewTarget:: 25
- Make Progress:: 5
- Make-Progress:: 72
dataviewTarget1:: 25/5
dataviewTarget2:: 5 @ 72
dataviewTarget3:: 5, 72

clock-in:: 8:7:5
clock-out:: 20:10:5

sleep:: 9:37 pm/7:57 am

#sin:0.20791/0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452/0.95106

#sinsquare:0.04323/0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451

- [x] Say I love you




================================================
FILE: examples/diary/2021-01-03-Sunday.md
================================================
---
tags: 
mood: 5
---

#weight:69.3kg

#exercise-pushup:39
#exercise-plank:98sec


⭐

#finance/bank1:-2.2USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker+1@gmail.com

weightlifting: 14




================================================
FILE: examples/diary/2021-01-03.md
================================================
---
tags: 
mood: 🙁
bloodpressure: 180.2/118.4
bloodpressure1: 180.2, 118.4
bloodpressure2: [180.2, 118.4]
bp:
    systolic: 180.2
    diastolic: 118.4
clock-in: 10:49
clock-out: 16:33
sleep: 9:17 pm/6:48 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 73.0
randchar: D
---

#weight:63.2kg

#exercise-pushup:49
#exercise-plank:79sec

#meditation

⭐


#finance/bank1:-2.4USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@yahoo.com


dataviewTarget:: 12
- Make Progress:: 14
- Make-Progress:: 82
dataviewTarget1:: 12/14
dataviewTarget2:: 14 @ 82
dataviewTarget3:: 14, 82

clock-in:: 10:49:14
clock-out:: 16:33:14

sleep:: 9:17 pm/6:48 am

#sin:0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452/0.95106/0.86603

#sinsquare:0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000

- [ ] Say I love you




================================================
FILE: examples/diary/2021-01-04-Monday.md
================================================
---
tags: work_log
mood: 7
---

#weight:70.6kg

#exercise-pushup:41
#exercise-plank:87sec


⭐

#finance/bank1:-3.3USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 11




================================================
FILE: examples/diary/2021-01-04.md
================================================
---
tags: work_log, work_log2
mood: 🙂
bloodpressure: 176.6/121.2
bloodpressure1: 176.6, 121.2
bloodpressure2: [176.6, 121.2]
bp:
    systolic: 176.6
    diastolic: 121.2
clock-in: 10:41
clock-out: 20:52
sleep: 10:10 pm/6:37 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 88.6
randchar: B
---

#weight:61.6kg

#exercise-pushup:33
#exercise-plank:114sec

#meditation

⭐

#clean-up

#finance/bank1:-3.8USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 18

dataviewTarget:: 43
- Make Progress:: 29
- Make-Progress:: 74
dataviewTarget1:: 43/29
dataviewTarget2:: 29 @ 74
dataviewTarget3:: 29, 74

clock-in:: 10:41:29
clock-out:: 20:52:29

sleep:: 10:10 pm/6:37 am

#sin:0.58779/0.74314/0.86603/0.95106/0.99452/0.99452/0.95106/0.86603/0.74314

#sinsquare:0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000/0.55226

- [x] Say I love you




================================================
FILE: examples/diary/2021-01-05-Tuesday.md
================================================
---
tags: work_log
mood: 8
---

#weight:60.2kg

#exercise-pushup:50
#exercise-plank:55sec

#meditation

⭐⭐⭐

#finance/bank1:-2.2USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@yahoo.com

weightlifting: 20




================================================
FILE: examples/diary/2021-01-05.md
================================================
---
tags: work_log, work_log2
mood: 😀
bloodpressure: 180/118
bloodpressure1: 180, 118
bloodpressure2: [180, 118]
bp:
    systolic: 180
    diastolic: 118
clock-in: 9:1
clock-out: 18:57
sleep: 9:9 pm/5:57 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 13.1
randchar: A
---

#weight:72.5kg

#exercise-pushup:5
#exercise-plank:57sec

#meditation

⭐


#finance/bank1:-3.9USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker+1@gmail.com

weightlifting: 17

dataviewTarget:: 86
- Make Progress:: 24
- Make-Progress:: 90
dataviewTarget1:: 86/24
dataviewTarget2:: 24 @ 90
dataviewTarget3:: 24, 90

clock-in:: 9:1:24
clock-out:: 18:57:24

sleep:: 9:9 pm/5:57 am

#sin:0.74314/0.86603/0.95106/0.99452/0.99452/0.95106/0.86603/0.74314/0.58779

#sinsquare:0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000/0.55226/0.34549

- [x] Say I love you




================================================
FILE: examples/diary/2021-01-06.md
================================================
---
tags: work_log, work_log2
mood: 🙁
bloodpressure: 171.4/118.8
bloodpressure1: 171.4, 118.8
bloodpressure2: [171.4, 118.8]
bp:
    systolic: 171.4
    diastolic: 118.8
clock-in: 10:27
clock-out: 19:26
sleep: 10:30 pm/5:29 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 20.7
randchar: D
---

#weight:60.1kg

#exercise-pushup:46
#exercise-plank:110sec

#meditation

⭐⭐⭐

#clean-up

#finance/bank1:-2.4USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker+1@gmail.com

weightlifting: 19

dataviewTarget:: 98
- Make Progress:: 46
- Make-Progress:: 75
dataviewTarget1:: 98/46
dataviewTarget2:: 46 @ 75
dataviewTarget3:: 46, 75

clock-in:: 10:27:46
clock-out:: 19:26:46

sleep:: 10:30 pm/5:29 am

#sin:0.86603/0.95106/0.99452/0.99452/0.95106/0.86603/0.74314/0.58779/0.40674

#sinsquare:0.75000/0.90451/0.98907/0.98907/0.90451/0.75000/0.55226/0.34549/0.16543

- [x] Say I love you




================================================
FILE: examples/diary/2021-01-07.md
================================================
---
tags: work_log, work_log2
mood: 😀
bloodpressure: 175.8/120.6
bloodpressure1: 175.8, 120.6
bloodpressure2: [175.8, 120.6]
bp:
    systolic: 175.8
    diastolic: 120.6
clock-in: 9:53
clock-out: 17:39
sleep: 10:53 pm/7:13 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 47.8
randchar: A
---

#weight:70.2kg

#exercise-pushup:33
#exercise-plank:103sec


⭐


#finance/bank1:-2.6USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 10

dataviewTarget:: 43
- Make Progress:: 6
- Make-Progress:: 77
dataviewTarget1:: 43/6
dataviewTarget2:: 6 @ 77
dataviewTarget3:: 6, 77

clock-in:: 9:53:6
clock-out:: 17:39:6

sleep:: 10:53 pm/7:13 am

#sin:0.95106/0.99452/0.99452/0.95106/0.86603/0.74314/0.58779/0.40674/0.20791

#sinsquare:0.90451/0.98907/0.98907/0.90451/0.75000/0.55226/0.34549/0.16543/0.04323

- [x] Say I love you




================================================
FILE: examples/diary/2021-01-08.md
================================================
---
tags: work_log, work_log2
mood: 😀
bloodpressure: 172.2/116.4
bloodpressure1: 172.2, 116.4
bloodpressure2: [172.2, 116.4]
bp:
    systolic: 172.2
    diastolic: 116.4
clock-in: 8:5
clock-out: 16:5
sleep: 9:1 pm/6:56 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 68.6
randchar: A
---

#weight:74.0kg

#exercise-pushup:33
#exercise-plank:77sec


⭐


#finance/bank1:-2.9USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 19

dataviewTarget:: 39
- Make Progress:: 25
- Make-Progress:: 77
dataviewTarget1:: 39/25
dataviewTarget2:: 25 @ 77
dataviewTarget3:: 25, 77

clock-in:: 8:5:25
clock-out:: 16:5:25

sleep:: 9:1 pm/6:56 am

#sin:0.99452/0.99452/0.95106/0.86603/0.74314/0.58779/0.40674/0.20791/0.00000

#sinsquare:0.98907/0.98907/0.90451/0.75000/0.55226/0.34549/0.16543/0.04323/0.00000

- [ ] Say I love you




================================================
FILE: examples/diary/2021-01-09.md
================================================
---
tags: 
mood: 😀
bloodpressure: 175.6/118.2
bloodpressure1: 175.6, 118.2
bloodpressure2: [175.6, 118.2]
bp:
    systolic: 175.6
    diastolic: 118.2
clock-in: 8:37
clock-out: 17:9
sleep: 9:23 pm/5:51 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 68.6
randchar: A
---

#weight:68.8kg

#exercise-pushup:35
#exercise-plank:112sec

#meditation

⭐⭐⭐


#finance/bank1:-3.8USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 10

dataviewTarget:: 37
- Make Progress:: 36
- Make-Progress:: 53
dataviewTarget1:: 37/36
dataviewTarget2:: 36 @ 53
dataviewTarget3:: 36, 53

clock-in:: 8:37:36
clock-out:: 17:9:36

sleep:: 9:23 pm/5:51 am

#sin:0.99452/0.95106/0.86603/0.74314/0.58779/0.40674/0.20791/0.00000/-0.20791

#sinsquare:0.98907/0.90451/0.75000/0.55226/0.34549/0.16543/0.04323/0.00000/0.04323

- [x] Say I love you




================================================
FILE: examples/diary/2021-01-10.md
================================================
---
tags: 
mood: 🙂
bloodpressure: 179/116
bloodpressure1: 179, 116
bloodpressure2: [179, 116]
bp:
    systolic: 179
    diastolic: 116
clock-in: 10:25
clock-out: 17:55
sleep: 10:11 pm/5:31 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 17.7
randchar: B
---

#weight:62.1kg

#exercise-pushup:41
#exercise-plank:92sec


⭐⭐⭐


#finance/bank1:-2.2USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker@yahoo.com


dataviewTarget:: 4
- Make Progress:: 10
- Make-Progress:: 92
dataviewTarget1:: 4/10
dataviewTarget2:: 10 @ 92
dataviewTarget3:: 10, 92

clock-in:: 10:25:10
clock-out:: 17:55:10

sleep:: 10:11 pm/5:31 am

#sin:0.95106/0.86603/0.74314/0.58779/0.40674/0.20791/0.00000/-0.20791/-0.40674

#sinsquare:0.90451/0.75000/0.55226/0.34549/0.16543/0.04323/0.00000/0.04323/0.16543

- [ ] Say I love you




================================================
FILE: examples/diary/2021-01-11.md
================================================
---
tags: work_log, work_log2
mood: 😐
bloodpressure: 173.4/117.8
bloodpressure1: 173.4, 117.8
bloodpressure2: [173.4, 117.8]
bp:
    systolic: 173.4
    diastolic: 117.8
clock-in: 9:42
clock-out: 20:35
sleep: 11:47 pm/6:8 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 26.2
randchar: C
---

#weight:80.8kg

#exercise-pushup:48
#exercise-plank:46sec


⭐⭐⭐⭐


#finance/bank1:-2.5USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@yahoo.com


dataviewTarget:: 97
- Make Progress:: 19
- Make-Progress:: 82
dataviewTarget1:: 97/19
dataviewTarget2:: 19 @ 82
dataviewTarget3:: 19, 82

clock-in:: 9:42:19
clock-out:: 20:35:19

sleep:: 11:47 pm/6:8 am

#sin:0.86603/0.74314/0.58779/0.40674/0.20791/0.00000/-0.20791/-0.40674/-0.58779

#sinsquare:0.75000/0.55226/0.34549/0.16543/0.04323/0.00000/0.04323/0.16543/0.34549

- [x] Say I love you




================================================
FILE: examples/diary/2021-01-12.md
================================================
---
tags: work_log, work_log2
mood: 😀
bloodpressure: 176.8/118.6
bloodpressure1: 176.8, 118.6
bloodpressure2: [176.8, 118.6]
bp:
    systolic: 176.8
    diastolic: 118.6
clock-in: 8:54
clock-out: 16:19
sleep: 11:23 pm/6:15 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 45.0
randchar: A
---

#weight:61.7kg

#exercise-pushup:32
#exercise-plank:31sec

#meditation

⭐⭐⭐


#finance/bank1:-2.7USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com

weightlifting: 10

dataviewTarget:: 79
- Make Progress:: 36
- Make-Progress:: 66
dataviewTarget1:: 79/36
dataviewTarget2:: 36 @ 66
dataviewTarget3:: 36, 66

clock-in:: 8:54:36
clock-out:: 16:19:36

sleep:: 11:23 pm/6:15 am

#sin:0.74314/0.58779/0.40674/0.20791/0.00000/-0.20791/-0.40674/-0.58779/-0.74314

#sinsquare:0.55226/0.34549/0.16543/0.04323/0.00000/0.04323/0.16543/0.34549/0.55226

- [x] Say I love you




================================================
FILE: examples/diary/2021-01-13.md
================================================
---
tags: work_log, work_log2
mood: 😞
bloodpressure: 168.2/116.4
bloodpressure1: 168.2, 116.4
bloodpressure2: [168.2, 116.4]
bp:
    systolic: 168.2
    diastolic: 116.4
clock-in: 8:1
clock-out: 17:0
sleep: 9:2 pm/6:37 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 64.5
randchar: E
---

#weight:71.7kg

#exercise-pushup:44
#exercise-plank:45sec

#meditation




#finance/bank1:-3.4USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]



dataviewTarget:: 87
- Make Progress:: 46
- Make-Progress:: 73
dataviewTarget1:: 87/46
dataviewTarget2:: 46 @ 73
dataviewTarget3:: 46, 73

clock-in:: 8:1:46
clock-out:: 17:0:46

sleep:: 9:2 pm/6:37 am

#sin:0.58779/0.40674/0.20791/0.00000/-0.20791/-0.40674/-0.58779/-0.74314/-0.86603

#sinsquare:0.34549/0.16543/0.04323/0.00000/0.04323/0.16543/0.34549/0.55226/0.75000

- [x] Say I love you




================================================
FILE: examples/diary/2021-01-14.md
================================================
---
tags: work_log, work_log2
mood: 😐
bloodpressure: 175.6/117.2
bloodpressure1: 175.6, 117.2
bloodpressure2: [175.6, 117.2]
bp:
    systolic: 175.6
    diastolic: 117.2
clock-in: 8:53
clock-out: 17:19
sleep: 9:40 pm/7:25 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 61.5
randchar: C
---

#weight:77.1kg

#exercise-pushup:37
#exercise-plank:89sec

#meditation

⭐

#clean-up

#finance/bank1:-2.5USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com

weightlifting: 15

dataviewTarget:: 43
- Make Progress:: 5
- Make-Progress:: 92
dataviewTarget1:: 43/5
dataviewTarget2:: 5 @ 92
dataviewTarget3:: 5, 92

clock-in:: 8:53:5
clock-out:: 17:19:5

sleep:: 9:40 pm/7:25 am

#sin:0.40674/0.20791/0.00000/-0.20791/-0.40674/-0.58779/-0.74314/-0.86603/-0.95106

#sinsquare:0.16543/0.04323/0.00000/0.04323/0.16543/0.34549/0.55226/0.75000/0.90451

- [x] Say I love you




================================================
FILE: examples/diary/2021-01-15.md
================================================
---
tags: work_log, work_log2
mood: 😀
bloodpressure: 176/115
bloodpressure1: 176, 115
bloodpressure2: [176, 115]
bp:
    systolic: 176
    diastolic: 115
clock-in: 9:20
clock-out: 18:40
sleep: 11:14 pm/6:44 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 44.0
randchar: A
---

#weight:69.6kg

#exercise-pushup:40
#exercise-plank:100sec

#meditation




#finance/bank1:-2.5USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@yahoo.com

weightlifting: 14

dataviewTarget:: 60
- Make Progress:: 7
- Make-Progress:: 81
dataviewTarget1:: 60/7
dataviewTarget2:: 7 @ 81
dataviewTarget3:: 7, 81

clock-in:: 9:20:7
clock-out:: 18:40:7

sleep:: 11:14 pm/6:44 am

#sin:0.20791/0.00000/-0.20791/-0.40674/-0.58779/-0.74314/-0.86603/-0.95106/-0.99452

#sinsquare:0.04323/0.00000/0.04323/0.16543/0.34549/0.55226/0.75000/0.90451/0.98907

- [ ] Say I love you




================================================
FILE: examples/diary/2021-01-16.md
================================================
---
tags: 
mood: 😞
bloodpressure: 168.4/114.8
bloodpressure1: 168.4, 114.8
bloodpressure2: [168.4, 114.8]
bp:
    systolic: 168.4
    diastolic: 114.8
clock-in: 9:54
clock-out: 18:3
sleep: 11:24 pm/6:40 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 81.6
randchar: E
---

#weight:70.0kg

#exercise-pushup:38
#exercise-plank:113sec


⭐⭐

#clean-up

#finance/bank1:-2.6USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker+1@gmail.com


dataviewTarget:: 17
- Make Progress:: 21
- Make-Progress:: 93
dataviewTarget1:: 17/21
dataviewTarget2:: 21 @ 93
dataviewTarget3:: 21, 93

clock-in:: 9:54:21
clock-out:: 18:3:21

sleep:: 11:24 pm/6:40 am

#sin:0.00000/-0.20791/-0.40674/-0.58779/-0.74314/-0.86603/-0.95106/-0.99452/-0.99452

#sinsquare:0.00000/0.04323/0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907

- [ ] Say I love you




================================================
FILE: examples/diary/2021-01-17.md
================================================
---
tags: 
mood: 🙂
bloodpressure: 165.8/114.6
bloodpressure1: 165.8, 114.6
bloodpressure2: [165.8, 114.6]
bp:
    systolic: 165.8
    diastolic: 114.6
clock-in: 8:3
clock-out: 16:23
sleep: 10:42 pm/6:30 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 43.0
randchar: B
---

#weight:64.6kg

#exercise-pushup:48
#exercise-plank:93sec


⭐⭐⭐⭐


#finance/bank1:-3.6USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 17

dataviewTarget:: 46
- Make Progress:: 38
- Make-Progress:: 82
dataviewTarget1:: 46/38
dataviewTarget2:: 38 @ 82
dataviewTarget3:: 38, 82

clock-in:: 8:3:38
clock-out:: 16:23:38

sleep:: 10:42 pm/6:30 am

#sin:-0.20791/-0.40674/-0.58779/-0.74314/-0.86603/-0.95106/-0.99452/-0.99452/-0.95106

#sinsquare:0.04323/0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451

- [ ] Say I love you




================================================
FILE: examples/diary/2021-01-18.md
================================================
---
tags: work_log, work_log2
mood: 😀
bloodpressure: 167.2/118.4
bloodpressure1: 167.2, 118.4
bloodpressure2: [167.2, 118.4]
bp:
    systolic: 167.2
    diastolic: 118.4
clock-in: 8:48
clock-out: 19:49
sleep: 9:10 pm/7:51 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 19.5
randchar: A
---

#weight:78.7kg

#exercise-pushup:42
#exercise-plank:77sec

#meditation

⭐


#finance/bank1:-3.3USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com

weightlifting: 20

dataviewTarget:: 28
- Make Progress:: 40
- Make-Progress:: 81
dataviewTarget1:: 28/40
dataviewTarget2:: 40 @ 81
dataviewTarget3:: 40, 81

clock-in:: 8:48:40
clock-out:: 19:49:40

sleep:: 9:10 pm/7:51 am

#sin:-0.40674/-0.58779/-0.74314/-0.86603/-0.95106/-0.99452/-0.99452/-0.95106/-0.86603

#sinsquare:0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000

- [ ] Say I love you




================================================
FILE: examples/diary/2021-01-19.md
================================================
---
tags: work_log, work_log2
mood: 😐
bloodpressure: 165.6/117.2
bloodpressure1: 165.6, 117.2
bloodpressure2: [165.6, 117.2]
bp:
    systolic: 165.6
    diastolic: 117.2
clock-in: 8:30
clock-out: 17:42
sleep: 9:34 pm/7:2 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 29.5
randchar: C
---

#weight:69.3kg

#exercise-pushup:47
#exercise-plank:69sec

#meditation

⭐⭐


#finance/bank1:-3.5USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com

weightlifting: 16

dataviewTarget:: 73
- Make Progress:: 8
- Make-Progress:: 59
dataviewTarget1:: 73/8
dataviewTarget2:: 8 @ 59
dataviewTarget3:: 8, 59

clock-in:: 8:30:8
clock-out:: 17:42:8

sleep:: 9:34 pm/7:2 am

#sin:-0.58779/-0.74314/-0.86603/-0.95106/-0.99452/-0.99452/-0.95106/-0.86603/-0.74314

#sinsquare:0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000/0.55226

- [ ] Say I love you




================================================
FILE: examples/diary/2021-01-20.md
================================================
---
tags: work_log, work_log2
mood: 🙂
bloodpressure: 163/117
bloodpressure1: 163, 117
bloodpressure2: [163, 117]
bp:
    systolic: 163
    diastolic: 117
clock-in: 9:30
clock-out: 20:13
sleep: 9:28 pm/7:58 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 56.2
randchar: B
---

#weight:80.7kg

#exercise-pushup:33
#exercise-plank:90sec


⭐⭐⭐


#finance/bank1:-3.2USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]


weightlifting: 19

dataviewTarget:: 64
- Make Progress:: 0
- Make-Progress:: 54
dataviewTarget1:: 64/0
dataviewTarget2:: 0 @ 54
dataviewTarget3:: 0, 54

clock-in:: 9:30:0
clock-out:: 20:13:0

sleep:: 9:28 pm/7:58 am

#sin:-0.74314/-0.86603/-0.95106/-0.99452/-0.99452/-0.95106/-0.86603/-0.74314/-0.58779

#sinsquare:0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000/0.55226/0.34549

- [x] Say I love you




================================================
FILE: examples/diary/2021-01-21.md
================================================
---
tags: work_log, work_log2
mood: 🙂
bloodpressure: 170.4/113.8
bloodpressure1: 170.4, 113.8
bloodpressure2: [170.4, 113.8]
bp:
    systolic: 170.4
    diastolic: 113.8
clock-in: 9:4
clock-out: 19:29
sleep: 10:43 pm/6:37 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 11.1
randchar: B
sleptwell: false
---

#weight:67.3kg

#exercise-pushup:50
#exercise-plank:94sec

#meditation

⭐⭐⭐


#finance/bank1:-2.8USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com

weightlifting: 19

dataviewTarget:: 88
- Make Progress:: 41
- Make-Progress:: 75
dataviewTarget1:: 88/41
dataviewTarget2:: 41 @ 75
dataviewTarget3:: 41, 75

clock-in:: 9:4:41
clock-out:: 19:29:41

sleep:: 10:43 pm/6:37 am

#sin:-0.86603/-0.95106/-0.99452/-0.99452/-0.95106/-0.86603/-0.74314/-0.58779/-0.40674

#sinsquare:0.75000/0.90451/0.98907/0.98907/0.90451/0.75000/0.55226/0.34549/0.16543

- [x] Say I love you




================================================
FILE: examples/diary/2021-01-22.md
================================================
---
tags: work_log, work_log2
mood: 😞
bloodpressure: 165.8/116.6
bloodpressure1: 165.8, 116.6
bloodpressure2: [165.8, 116.6]
bp:
    systolic: 165.8
    diastolic: 116.6
clock-in: 9:32
clock-out: 20:27
sleep: 10:25 pm/5:12 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 83.3
randchar: E
sleptwell: true
---

#weight:64.7kg

#exercise-pushup:30
#exercise-plank:100sec


⭐


#finance/bank1:-3.3USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com

weightlifting: 11

dataviewTarget:: 36
- Make Progress:: 0
- Make-Progress:: 91
dataviewTarget1:: 36/0
dataviewTarget2:: 0 @ 91
dataviewTarget3:: 0, 91

clock-in:: 9:32:0
clock-out:: 20:27:0

sleep:: 10:25 pm/5:12 am

#sin:-0.95106/-0.99452/-0.99452/-0.95106/-0.86603/-0.74314/-0.58779/-0.40674/-0.20791

#sinsquare:0.90451/0.98907/0.98907/0.90451/0.75000/0.55226/0.34549/0.16543/0.04323

- [x] Say I love you




================================================
FILE: examples/diary/2021-01-23.md
================================================
---
tags: 
mood: 😀
bloodpressure: 164.2/115.4
bloodpressure1: 164.2, 115.4
bloodpressure2: [164.2, 115.4]
bp:
    systolic: 164.2
    diastolic: 115.4
clock-in: 10:36
clock-out: 19:31
sleep: 10:9 pm/7:30 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 28.8
randchar: A
sleptwell: true
---

#weight:67.3kg

#exercise-pushup:47
#exercise-plank:83sec


⭐⭐⭐⭐


#finance/bank1:-2.7USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com

weightlifting: 12

dataviewTarget:: 45
- Make Progress:: 27
- Make-Progress:: 95
dataviewTarget1:: 45/27
dataviewTarget2:: 27 @ 95
dataviewTarget3:: 27, 95

clock-in:: 10:36:27
clock-out:: 19:31:27

sleep:: 10:9 pm/7:30 am

#sin:-0.99452/-0.99452/-0.95106/-0.86603/-0.74314/-0.58779/-0.40674/-0.20791/-0.00000

#sinsquare:0.98907/0.98907/0.90451/0.75000/0.55226/0.34549/0.16543/0.04323/0.00000

- [ ] Say I love you




================================================
FILE: examples/diary/2021-01-24.md
================================================
---
tags: 
mood: 🙂
bloodpressure: 170.6/113.2
bloodpressure1: 170.6, 113.2
bloodpressure2: [170.6, 113.2]
bp:
    systolic: 170.6
    diastolic: 113.2
clock-in: 8:1
clock-out: 18:9
sleep: 10:53 pm/5:33 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 39.4
randchar: B
sleptwell: true
---

#weight:64.1kg

#exercise-pushup:43
#exercise-plank:44sec

#meditation

⭐⭐⭐⭐


#finance/bank1:-3.3USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 10

dataviewTarget:: 63
- Make Progress:: 23
- Make-Progress:: 60
dataviewTarget1:: 63/23
dataviewTarget2:: 23 @ 60
dataviewTarget3:: 23, 60

clock-in:: 8:1:23
clock-out:: 18:9:23

sleep:: 10:53 pm/5:33 am

#sin:-0.99452/-0.95106/-0.86603/-0.74314/-0.58779/-0.40674/-0.20791/-0.00000/0.20791

#sinsquare:0.98907/0.90451/0.75000/0.55226/0.34549/0.16543/0.04323/0.00000/0.04323

- [ ] Say I love you




================================================
FILE: examples/diary/2021-01-25.md
================================================
---
tags: work_log, work_log2
mood: 😞
bloodpressure: 167/114
bloodpressure1: 167, 114
bloodpressure2: [167, 114]
bp:
    systolic: 167
    diastolic: 114
clock-in: 9:52
clock-out: 17:55
sleep: 10:53 pm/6:3 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 81.4
randchar: E
sleptwell: false
---

#weight:62.4kg

#exercise-pushup:30
#exercise-plank:110sec





#finance/bank1:-3.6USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker+1@gmail.com


dataviewTarget:: 88
- Make Progress:: 12
- Make-Progress:: 96
dataviewTarget1:: 88/12
dataviewTarget2:: 12 @ 96
dataviewTarget3:: 12, 96

clock-in:: 9:52:12
clock-out:: 17:55:12

sleep:: 10:53 pm/6:3 am

#sin:-0.95106/-0.86603/-0.74314/-0.58779/-0.40674/-0.20791/-0.00000/0.20791/0.40674

#sinsquare:0.90451/0.75000/0.55226/0.34549/0.16543/0.04323/0.00000/0.04323/0.16543

- [ ] Say I love you




================================================
FILE: examples/diary/2021-01-26.md
================================================
---
tags: work_log, work_log2
mood: 🙂
bloodpressure: 162.4/114.8
bloodpressure1: 162.4, 114.8
bloodpressure2: [162.4, 114.8]
bp:
    systolic: 162.4
    diastolic: 114.8
clock-in: 10:24
clock-out: 19:12
sleep: 11:36 pm/6:2 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 73.1
randchar: B
---

#weight:72.7kg

#exercise-pushup:42
#exercise-plank:114sec

#meditation

⭐


#finance/bank1:-3.3USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@yahoo.com


dataviewTarget:: 42
- Make Progress:: 19
- Make-Progress:: 93
dataviewTarget1:: 42/19
dataviewTarget2:: 19 @ 93
dataviewTarget3:: 19, 93

clock-in:: 10:24:19
clock-out:: 19:12:19

sleep:: 11:36 pm/6:2 am

#sin:-0.86603/-0.74314/-0.58779/-0.40674/-0.20791/-0.00000/0.20791/0.40674/0.58779

#sinsquare:0.75000/0.55226/0.34549/0.16543/0.04323/0.00000/0.04323/0.16543/0.34549

- [ ] Say I love you




================================================
FILE: examples/diary/2021-01-27.md
================================================
---
tags: work_log, work_log2
mood: 🙂
bloodpressure: 165.8/113.6
bloodpressure1: 165.8, 113.6
bloodpressure2: [165.8, 113.6]
bp:
    systolic: 165.8
    diastolic: 113.6
clock-in: 10:28
clock-out: 18:4
sleep: 11:34 pm/6:12 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 78.5
randchar: B
---

#weight:63.7kg

#exercise-pushup:46
#exercise-plank:40sec

#meditation

⭐⭐⭐


#finance/bank1:-2.2USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@yahoo.com

weightlifting: 11

dataviewTarget:: 59
- Make Progress:: 31
- Make-Progress:: 67
dataviewTarget1:: 59/31
dataviewTarget2:: 31 @ 67
dataviewTarget3:: 31, 67

clock-in:: 10:28:31
clock-out:: 18:4:31

sleep:: 11:34 pm/6:12 am

#sin:-0.74314/-0.58779/-0.40674/-0.20791/-0.00000/0.20791/0.40674/0.58779/0.74314

#sinsquare:0.55226/0.34549/0.16543/0.04323/0.00000/0.04323/0.16543/0.34549/0.55226

- [ ] Say I love you




================================================
FILE: examples/diary/2021-01-28.md
================================================
---
tags: work_log, work_log2
mood: 😀
bloodpressure: 158.2/115.4
bloodpressure1: 158.2, 115.4
bloodpressure2: [158.2, 115.4]
bp:
    systolic: 158.2
    diastolic: 115.4
clock-in: 10:44
clock-out: 16:41
sleep: 10:27 pm/5:11 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 80.6
randchar: A
---

#weight:79.2kg

#exercise-pushup:36
#exercise-plank:90sec





#finance/bank1:-3.9USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 18

dataviewTarget:: 36
- Make Progress:: 33
- Make-Progress:: 92
dataviewTarget1:: 36/33
dataviewTarget2:: 33 @ 92
dataviewTarget3:: 33, 92

clock-in:: 10:44:33
clock-out:: 16:41:33

sleep:: 10:27 pm/5:11 am

#sin:-0.58779/-0.40674/-0.20791/-0.00000/0.20791/0.40674/0.58779/0.74314/0.86603

#sinsquare:0.34549/0.16543/0.04323/0.00000/0.04323/0.16543/0.34549/0.55226/0.75000

- [ ] Say I love you




================================================
FILE: examples/diary/2021-01-29.md
================================================
---
tags: work_log, work_log2
mood: 🙁
bloodpressure: 163.6/112.2
bloodpressure1: 163.6, 112.2
bloodpressure2: [163.6, 112.2]
bp:
    systolic: 163.6
    diastolic: 112.2
clock-in: 8:19
clock-out: 16:35
sleep: 11:47 pm/6:39 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 18.6
randchar: D
---

#weight:63.5kg

#exercise-pushup:42
#exercise-plank:30sec


⭐


#finance/bank1:-2.7USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@yahoo.com

weightlifting: 15

dataviewTarget:: 96
- Make Progress:: 44
- Make-Progress:: 90
dataviewTarget1:: 96/44
dataviewTarget2:: 44 @ 90
dataviewTarget3:: 44, 90

clock-in:: 8:19:44
clock-out:: 16:35:44

sleep:: 11:47 pm/6:39 am

#sin:-0.40674/-0.20791/-0.00000/0.20791/0.40674/0.58779/0.74314/0.86603/0.95106

#sinsquare:0.16543/0.04323/0.00000/0.04323/0.16543/0.34549/0.55226/0.75000/0.90451

- [x] Say I love you




================================================
FILE: examples/diary/2021-01-30.md
================================================
---
tags: 
mood: 😐
bloodpressure: 159/114
bloodpressure1: 159, 114
bloodpressure2: [159, 114]
bp:
    systolic: 159
    diastolic: 114
clock-in: 10:24
clock-out: 18:4
sleep: 11:10 pm/5:46 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 17.9
randchar: C
---

#weight:63.3kg

#exercise-pushup:30
#exercise-plank:83sec


⭐⭐⭐


#finance/bank1:-2.2USD
#finance/bank2:200USD
#finance/bank2/transfer:-100USD
#finance/bank1/transfer:100USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com

weightlifting: 10

dataviewTarget:: 44
- Make Progress:: 48
- Make-Progress:: 84
dataviewTarget1:: 44/48
dataviewTarget2:: 48 @ 84
dataviewTarget3:: 48, 84

clock-in:: 10:24:48
clock-out:: 18:4:48

sleep:: 11:10 pm/5:46 am

#sin:-0.20791/-0.00000/0.20791/0.40674/0.58779/0.74314/0.86603/0.95106/0.99452

#sinsquare:0.04323/0.00000/0.04323/0.16543/0.34549/0.55226/0.75000/0.90451/0.98907

- [ ] Say I love you




================================================
FILE: examples/diary/2021-01-31.md
================================================
---
tags: 
mood: 🙂
bloodpressure: 160.4/115.8
bloodpressure1: 160.4, 115.8
bloodpressure2: [160.4, 115.8]
bp:
    systolic: 160.4
    diastolic: 115.8
clock-in: 10:5
clock-out: 17:3
sleep: 9:14 pm/5:9 am
deepValue: 
    very: 
        very: 
            very: 
                very: 
                    very: 
                        deep: 56.8
randchar: B
---

#weight:72.2kg

#exercise-pushup:36
#exercise-plank:119sec


⭐⭐⭐⭐⭐


#finance/bank1:-2.8USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com

weightlifting: 17

dataviewTarget:: 59
- Make Progress:: 22
- Make-Progress:: 55
dataviewTarget1:: 59/22
dataviewTarget2:: 22 @ 55
dataviewTarget3:: 22, 55

clock-in:: 10:5:22
clock-out:: 17:3:22

sleep:: 9:14 pm/5:9 am

#sin:-0.00000/0.20791/0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452

#sinsquare:0.00000/0.04323/0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907

- [ ] Say I love you




================================================
FILE: examples/diary/20210101-D.md
================================================
---
tags: work_log
mood: 10
bloodpressure: 177.4/121.8
---

#weight:74.0kg

#exercise-pushup:44
#exercise-plank:37sec


⭐⭐⭐⭐⭐

#finance/bank1:-3.4USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 10

#sin:0.00000/0.20791/0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452

#sinsquare:0.00000/0.04323/0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907




================================================
FILE: examples/diary/20210102-D.md
================================================
---
tags: 
mood: 8
bloodpressure: 174.8/121.6
---

#weight:68.8kg

#exercise-pushup:38
#exercise-plank:112sec


⭐⭐⭐

#finance/bank1:-2.7USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 16

#sin:0.20791/0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452/0.95106

#sinsquare:0.04323/0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451




================================================
FILE: examples/diary/20210103-D.md
================================================
---
tags: 
mood: 7
bloodpressure: 178.2/119.4
---

#weight:74.9kg

#exercise-pushup:32
#exercise-plank:56sec

#meditation

⭐⭐⭐⭐⭐

#finance/bank1:-3.7USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 16

#sin:0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452/0.95106/0.86603

#sinsquare:0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000




================================================
FILE: examples/diary/20210104-D.md
================================================
---
tags: work_log
mood: 3
bloodpressure: 178.6/119.2
---

#weight:73.5kg

#exercise-pushup:40
#exercise-plank:74sec

#meditation

⭐⭐⭐⭐⭐

#finance/bank1:-2.5USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]


weightlifting: 19

#sin:0.58779/0.74314/0.86603/0.95106/0.99452/0.99452/0.95106/0.86603/0.74314

#sinsquare:0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000/0.55226




================================================
FILE: examples/diary/20210105-D.md
================================================
---
tags: work_log
mood: 1
bloodpressure: 177/119
---

#weight:70.0kg

#exercise-pushup:5
#exercise-plank:34sec

#meditation

⭐⭐

#finance/bank1:-2.6USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com

weightlifting: 10

#sin:0.74314/0.86603/0.95106/0.99452/0.99452/0.95106/0.86603/0.74314/0.58779

#sinsquare:0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000/0.55226/0.34549




================================================
FILE: examples/diary/2023-06-05.md
================================================
Physical:: 😐


================================================
FILE: examples/diary/2023-06-06.md
================================================
Physical:: 😐


================================================
FILE: examples/diary/2023-06-07.md
================================================
Physical:: 😀


================================================
FILE: examples/diary/2023-06-08.md
================================================
Physical:: 😞


================================================
FILE: examples/diary/3-20210103.md
================================================
---
tags: 
mood: 5
---

#weight:69.3kg

#exercise-pushup:39
#exercise-plank:98sec


⭐

#finance/bank1:-2.2USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker+1@gmail.com

weightlifting: 14




================================================
FILE: examples/diary/4-20210104.md
================================================
---
tags: work_log
mood: 7
---

#weight:70.6kg

#exercise-pushup:41
#exercise-plank:87sec


⭐

#finance/bank1:-3.3USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 11




================================================
FILE: examples/diary/5-20210105.md
================================================
---
tags: work_log
mood: 8
---

#weight:60.2kg

#exercise-pushup:50
#exercise-plank:55sec

#meditation

⭐⭐⭐

#finance/bank1:-2.2USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@yahoo.com

weightlifting: 20




================================================
FILE: examples/diary/D-20210101.md
================================================
---
tags: work_log
mood: 10
bloodpressure: 177.4/121.8
---

#weight:74.0kg

#exercise-pushup:44
#exercise-plank:37sec


⭐⭐⭐⭐⭐

#finance/bank1:-3.4USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 10

#sin:0.00000/0.20791/0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452

#sinsquare:0.00000/0.04323/0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907




================================================
FILE: examples/diary/D-20210102.md
================================================
---
tags: 
mood: 8
bloodpressure: 174.8/121.6
---

#weight:68.8kg

#exercise-pushup:38
#exercise-plank:112sec


⭐⭐⭐

#finance/bank1:-2.7USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 16

#sin:0.20791/0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452/0.95106

#sinsquare:0.04323/0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451




================================================
FILE: examples/diary/D-20210103.md
================================================
---
tags: 
mood: 7
bloodpressure: 178.2/119.4
---

#weight:74.9kg

#exercise-pushup:32
#exercise-plank:56sec

#meditation

⭐⭐⭐⭐⭐

#finance/bank1:-3.7USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 16

#sin:0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452/0.95106/0.86603

#sinsquare:0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000




================================================
FILE: examples/diary/D-20210104.md
================================================
---
tags: work_log
mood: 3
bloodpressure: 178.6/119.2
---

#weight:73.5kg

#exercise-pushup:40
#exercise-plank:74sec

#meditation

⭐⭐⭐⭐⭐

#finance/bank1:-2.5USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]


weightlifting: 19

#sin:0.58779/0.74314/0.86603/0.95106/0.99452/0.99452/0.95106/0.86603/0.74314

#sinsquare:0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000/0.55226




================================================
FILE: examples/diary/D-20210105.md
================================================
---
tags: work_log
mood: 1
bloodpressure: 177/119
---

#weight:70.0kg

#exercise-pushup:5
#exercise-plank:34sec

#meditation

⭐⭐

#finance/bank1:-2.6USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com

weightlifting: 10

#sin:0.74314/0.86603/0.95106/0.99452/0.99452/0.95106/0.86603/0.74314/0.58779

#sinsquare:0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000/0.55226/0.34549




================================================
FILE: examples/diary/Jeffrey-20210101-Diary.md
================================================
---
tags: work_log
mood: 10
bloodpressure: 177.4/121.8
---

#weight:74.0kg

#exercise-pushup:44
#exercise-plank:37sec


⭐⭐⭐⭐⭐

#finance/bank1:-3.4USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 10

#sin:0.00000/0.20791/0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452

#sinsquare:0.00000/0.04323/0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907




================================================
FILE: examples/diary/Jeffrey-20210101-Journal.md
================================================
---
tags: work_log
mood: 10
bloodpressure: 177.4/121.8
---

#weight:74.0kg

#exercise-pushup:44
#exercise-plank:37sec


⭐⭐⭐⭐⭐

#finance/bank1:-3.4USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 10

#sin:0.00000/0.20791/0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452

#sinsquare:0.00000/0.04323/0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907




================================================
FILE: examples/diary/Jeffrey-20210102-Diary.md
================================================
---
tags: 
mood: 8
bloodpressure: 174.8/121.6
---

#weight:68.8kg

#exercise-pushup:38
#exercise-plank:112sec


⭐⭐⭐

#finance/bank1:-2.7USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 16

#sin:0.20791/0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452/0.95106

#sinsquare:0.04323/0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451




================================================
FILE: examples/diary/Jeffrey-20210102-Journal.md
================================================
---
tags: 
mood: 8
bloodpressure: 174.8/121.6
---

#weight:68.8kg

#exercise-pushup:38
#exercise-plank:112sec


⭐⭐⭐

#finance/bank1:-2.7USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 16

#sin:0.20791/0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452/0.95106

#sinsquare:0.04323/0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451




================================================
FILE: examples/diary/Jeffrey-20210103-Diary.md
================================================
---
tags: 
mood: 7
bloodpressure: 178.2/119.4
---

#weight:74.9kg

#exercise-pushup:32
#exercise-plank:56sec

#meditation

⭐⭐⭐⭐⭐

#finance/bank1:-3.7USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 16

#sin:0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452/0.95106/0.86603

#sinsquare:0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000




================================================
FILE: examples/diary/Jeffrey-20210103-Journal.md
================================================
---
tags: 
mood: 7
bloodpressure: 178.2/119.4
---

#weight:74.9kg

#exercise-pushup:32
#exercise-plank:56sec

#meditation

⭐⭐⭐⭐⭐

#finance/bank1:-3.7USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 16

#sin:0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452/0.95106/0.86603

#sinsquare:0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000




================================================
FILE: examples/diary/Jeffrey-20210104-Diary.md
================================================
---
tags: work_log
mood: 3
bloodpressure: 178.6/119.2
---

#weight:73.5kg

#exercise-pushup:40
#exercise-plank:74sec

#meditation

⭐⭐⭐⭐⭐

#finance/bank1:-2.5USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]


weightlifting: 19

#sin:0.58779/0.74314/0.86603/0.95106/0.99452/0.99452/0.95106/0.86603/0.74314

#sinsquare:0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000/0.55226




================================================
FILE: examples/diary/Jeffrey-20210104-Journal.md
================================================
---
tags: work_log
mood: 3
bloodpressure: 178.6/119.2
---

#weight:73.5kg

#exercise-pushup:40
#exercise-plank:74sec

#meditation

⭐⭐⭐⭐⭐

#finance/bank1:-2.5USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]


weightlifting: 19

#sin:0.58779/0.74314/0.86603/0.95106/0.99452/0.99452/0.95106/0.86603/0.74314

#sinsquare:0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000/0.55226




================================================
FILE: examples/diary/Jeffrey-20210105-Diary.md
================================================
---
tags: work_log
mood: 1
bloodpressure: 177/119
---

#weight:70.0kg

#exercise-pushup:5
#exercise-plank:34sec

#meditation

⭐⭐

#finance/bank1:-2.6USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com

weightlifting: 10

#sin:0.74314/0.86603/0.95106/0.99452/0.99452/0.95106/0.86603/0.74314/0.58779

#sinsquare:0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000/0.55226/0.34549




================================================
FILE: examples/diary/Jeffrey-20210105-Journal.md
================================================
---
tags: work_log
mood: 1
bloodpressure: 177/119
---

#weight:70.0kg

#exercise-pushup:5
#exercise-plank:34sec

#meditation

⭐⭐

#finance/bank1:-2.6USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com

weightlifting: 10

#sin:0.74314/0.86603/0.95106/0.99452/0.99452/0.95106/0.86603/0.74314/0.58779

#sinsquare:0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000/0.55226/0.34549




================================================
FILE: examples/diary/Lucas-20210101-Diary.md
================================================
---
tags: work_log
mood: 10
bloodpressure: 177.4/121.8
---

#weight:74.0kg

#exercise-pushup:44
#exercise-plank:37sec


⭐⭐⭐⭐⭐

#finance/bank1:-3.4USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 10

#sin:0.00000/0.20791/0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452

#sinsquare:0.00000/0.04323/0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907




================================================
FILE: examples/diary/Lucas-20210101-Journal.md
================================================
---
tags: work_log
mood: 10
bloodpressure: 177.4/121.8
---

#weight:74.0kg

#exercise-pushup:44
#exercise-plank:37sec


⭐⭐⭐⭐⭐

#finance/bank1:-3.4USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 10

#sin:0.00000/0.20791/0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452

#sinsquare:0.00000/0.04323/0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907




================================================
FILE: examples/diary/Lucas-20210102-Diary.md
================================================
---
tags: 
mood: 8
bloodpressure: 174.8/121.6
---

#weight:68.8kg

#exercise-pushup:38
#exercise-plank:112sec


⭐⭐⭐

#finance/bank1:-2.7USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 16

#sin:0.20791/0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452/0.95106

#sinsquare:0.04323/0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451




================================================
FILE: examples/diary/Lucas-20210102-Journal.md
================================================
---
tags: 
mood: 8
bloodpressure: 174.8/121.6
---

#weight:68.8kg

#exercise-pushup:38
#exercise-plank:112sec


⭐⭐⭐

#finance/bank1:-2.7USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 16

#sin:0.20791/0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452/0.95106

#sinsquare:0.04323/0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451




================================================
FILE: examples/diary/Lucas-20210103-Diary.md
================================================
---
tags: 
mood: 7
bloodpressure: 178.2/119.4
---

#weight:74.9kg

#exercise-pushup:32
#exercise-plank:56sec

#meditation

⭐⭐⭐⭐⭐

#finance/bank1:-3.7USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 16

#sin:0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452/0.95106/0.86603

#sinsquare:0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000




================================================
FILE: examples/diary/Lucas-20210103-Journal.md
================================================
---
tags: 
mood: 7
bloodpressure: 178.2/119.4
---

#weight:74.9kg

#exercise-pushup:32
#exercise-plank:56sec

#meditation

⭐⭐⭐⭐⭐

#finance/bank1:-3.7USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com
obsidian-tracker+1@gmail.com
obsidian-tracker@yahoo.com

weightlifting: 16

#sin:0.40674/0.58779/0.74314/0.86603/0.95106/0.99452/0.99452/0.95106/0.86603

#sinsquare:0.16543/0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000




================================================
FILE: examples/diary/Lucas-20210104-Diary.md
================================================
---
tags: work_log
mood: 3
bloodpressure: 178.6/119.2
---

#weight:73.5kg

#exercise-pushup:40
#exercise-plank:74sec

#meditation

⭐⭐⭐⭐⭐

#finance/bank1:-2.5USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]


weightlifting: 19

#sin:0.58779/0.74314/0.86603/0.95106/0.99452/0.99452/0.95106/0.86603/0.74314

#sinsquare:0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000/0.55226




================================================
FILE: examples/diary/Lucas-20210104-Journal.md
================================================
---
tags: work_log
mood: 3
bloodpressure: 178.6/119.2
---

#weight:73.5kg

#exercise-pushup:40
#exercise-plank:74sec

#meditation

⭐⭐⭐⭐⭐

#finance/bank1:-2.5USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]


weightlifting: 19

#sin:0.58779/0.74314/0.86603/0.95106/0.99452/0.99452/0.95106/0.86603/0.74314

#sinsquare:0.34549/0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000/0.55226




================================================
FILE: examples/diary/Lucas-20210105-Diary.md
================================================
---
tags: work_log
mood: 1
bloodpressure: 177/119
---

#weight:70.0kg

#exercise-pushup:5
#exercise-plank:34sec

#meditation

⭐⭐

#finance/bank1:-2.6USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com

weightlifting: 10

#sin:0.74314/0.86603/0.95106/0.99452/0.99452/0.95106/0.86603/0.74314/0.58779

#sinsquare:0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000/0.55226/0.34549




================================================
FILE: examples/diary/Lucas-20210105-Journal.md
================================================
---
tags: work_log
mood: 1
bloodpressure: 177/119
---

#weight:70.0kg

#exercise-pushup:5
#exercise-plank:34sec

#meditation

⭐⭐

#finance/bank1:-2.6USD

[[todo_family|To-Do @Family]]
[[todo_work|To-Do @Work]]

obsidian-tracker@gmail.com

weightlifting: 10

#sin:0.74314/0.86603/0.95106/0.99452/0.99452/0.95106/0.86603/0.74314/0.58779

#sinsquare:0.55226/0.75000/0.90451/0.98907/0.98907/0.90451/0.75000/0.55226/0.34549




