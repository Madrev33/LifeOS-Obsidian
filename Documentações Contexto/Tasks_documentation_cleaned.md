# Documentação Completa - publish_obsidian_md

**URL Original**: https://publish.obsidian.md/tasks/Introduction
**Data**: 28/05/2025 21:34:31
**Estratégia**: BFS
**Extraído com**: Crawl4AI - Madrev Edition

---

## 1. https://publish.obsidian.md/tasks/Introduction


```

# Introduction 
## Navigation around this site 
These are the main pages and sections, that connect to all the pages here:
Navigation
### Basics
  * Getting Started ...
    * Statuses ...
  * Editing...
  * Queries ...
  * Quick Reference


### Advanced and Detail
  * Scripting ...
  * Advanced ...
  * Other Plugins ...
  * Reference ...
    * Status Collections ...
    * Task Formats ...


### Help
  * How Tos ...
  * Support and Help ...
  * Changelog...


## Task management for the Obsidian knowledge base 
Track tasks across your entire Obsidian vault. Query them and mark them as done wherever you want. Supports due dates, recurring tasks (repetition), done dates, sub-set of checklist items, and filtering.
You can toggle the task status in any view or query and it will update the source file.
## Screenshots 
  * _All screenshots assume the global filter`#task` which is not set by default (see also "Getting Started")._
  * _The theme is default Obsidian theme._


!ACME Tasks The `ACME` note has some tasks.
!Important Project Tasks The `Important Project` note also has some tasks.
!Tasks Queries The `Tasks` note gathers all tasks from the vault and displays them using queries.
!Create or Edit Modal The `Tasks: Create or edit` command helps you when editing a task.
Introduction


================================================================================

## 2. https://publish.obsidian.md/tasks/Other+Plugins/About+Other+Plugins


```

# About Editing 
#index-pages
Tasks has a growing number of ways to conveniently add data to your task lines.
## General editing techniques 
  * Auto-Suggest
    * Intelligent auto-suggest facility does a lot of your typing of task data for you.
  * Create or edit Task
    * Helpful dialog/modal for easy adding and editing of task data.


## Editing specific task properties 
  * Toggling and Editing Statuses
    * All the ways to edit task statuses.
  * Editing Dates
    * All the ways to edit dates on tasks.
  * Postponing
    * Easy deferring or snoozing of due, scheduled and start dates.


About Editing


================================================================================

## 4. https://publish.obsidian.md/tasks/How+To/About+How+Tos


```

# About Statuses 
#index-pages #feature/statuses
This section provides more detail to flesh out the introductory material in Statuses.
## Types of Status 
  * Core Statuses
  * Custom Statuses
  * Status Types


## Setting up your Statuses 
  * Status Settings
  * Editing a Status
  * Check your Statuses


## Statuses in Use 
  * Recurring Tasks and Custom Statuses


About Statuses


================================================================================

## 8. https://publish.obsidian.md/tasks/Getting+Started/About+Getting+Started


```

# About Getting Started 
#index-pages
## Basics 
  * Installation
  * Getting Started
    * Descriptive overview of setting up your tasks.
    * Also has a long list of known limitations.
  * Global Filter
    * **Optionally** set a global filter so Tasks only matches specific checklist items.
    * See also Global Query, which is much more powerful, once you know how searching works.
  * Settings
    * A convenient list of all the Tasks plugin options.


## Adding data to your tasks 
  * Dates
    * Record when you need to work on your tasks.
    * Track the history of your tasks.
  * Priority
    * Indicate the importance of your tasks.
  * Recurring Tasks
    * Use recurring tasks to easily track actions you must do regularly.
  * On Completion
    * Specify an automatic action to perform on a task when it is completed.
  * Statuses
    * Also known as Custom Checkboxes.
    * In vanilla Obsidian tasks are either 'TODO' or 'DONE'.
    * Statuses allow you to track `IN_PROGRESS`, `CANCELLED` and `NON_TASK` actions too.
  * Use Filename as Default Date
    * Automatically set a scheduled date for tasks based on the name of their files.
  * Tags
    * Why and how to use tags to manage your tasks.


## More specialised facilities 
  * Task Dependencies
    * Define the order in which you want to work on a set of tasks.
    * Then adjust your searches, perhaps to see tasks that are blocking others, or hide ones that are blocked and cannot yet be done.
  * Obsidian Properties
    * Learn how to use data in Obsidian Properties in your queries, for example to only search tasks in Kanban plugin files.


## Easy editing of tasks 
About Getting Started


================================================================================

## 9. https://publish.obsidian.md/tasks/Queries/About+Queries


aliases:
 - Queries/Queries
```

# About Queries 
#index-pages
## The Simplest Query 
You can list tasks from your entire vault by querying them using a `tasks` code block. You can edit the tasks from the query results by clicking on the little pencil icon next to them. Tasks are by default sorted by status, due date, and then path. You can change the sorting (see query options below).
The simplest way to query tasks is this:
```
```tasks
```

```

In Live Preview and Reading modes, this will list _all_ tasks from your vault, regardless of their properties like status.
This is probably not what you want. Therefore, Tasks allows you to set query options to filter the tasks that you want to show.
For instance, you can show only the tasks (from anywhere in the vault) that are due today:
About Queries


================================================================================

## 10. https://publish.obsidian.md/tasks/Reference/Status+Collections/About+Status+Collections


aliases:
 - Reference/Status Collections/Status Collections
```

# About Status Collections 
#index-pages #feature/statuses
## Background 
Released
Custom statuses were introduced in Tasks 1.23.0.
You can control the behaviour of your tasks (such as what happens when you click on a checkbox), using Tasks' Statuses feature.
Info
Broad steps to understand and set up Statuses (or "Alternate Checkboxes"):
  * Understand what Statuses are: 
    * Statuses
    * Custom Statuses
  * Choose your status styling scheme: this will determine the names and symbols for your custom statuses: 
    * Some common ones are shown in About Status Collections
  * Set up your status styling scheme 
    * How to style custom statuses.
  * Configure Tasks to use your custom statuses 
    * How to set up your custom statuses
    * Check your Statuses
  * Optionally, update your tasks searches to take advantage of the new flexibility 
    * Filters for Task Statuses


The theme and snippet authors generally refer to this as 'custom checkboxes'.
About Status Collections


================================================================================

## 11. https://publish.obsidian.md/tasks/Support+and+Help/About+Support+and+Help


aliases:
 - Advanced/Advanced
```

# About Advanced 
#index-pages
This section provides some more advanced material - content which is typically too specialised for other parts of the documentation.
## Advanced section contents 
  * Daily Agenda
    * Some tips on templating to set up daily agenda pages
  * Styling
    * Use CSS to style your Tasks query results
  * Urgency
    * Calculate an urgency score, based on your task data
  * Notifications
    * About the Reminders plugin, in conjunction with Tasks
  * Tasks Api
    * Integrate Tasks in to other Plugins, scripts or dynamic code blocks.


## Related pages 
See also About Other Plugins for some information about plugins that may be useful with Tasks.
About Advanced


================================================================================

## 14. https://publish.obsidian.md/tasks/Quick+Reference


aliases:
 - Quick Reference/Quick Reference
```

# Quick Reference 
This table summarizes the filters and other options available inside a `tasks` block.
Filters | Sort | Group | Display | Scripting  
---|---|---|---|---  
**Status** |  |  |  |   
`done``not done` | `sort by status` | `group by status` |  | `task.isDone`  
`status.name (includes, does not include) <string>``status.name (regex matches, regex does not match) /regex/i` | `sort by status.name` | `group by status.name` |  | `task.status.name`  
`status.type (is, is not) (TODO, DONE, IN_PROGRESS, CANCELLED, NON_TASK)` | `sort by status.type` | `group by status.type` |  | `task.status.type``task.status.typeGroupText`  
|  |  |  | `task.status.symbol`  
|  |  |  | `task.status.nextSymbol`  
**Task Dependencies** |  |  |  |   
`id (includes, does not include) <string>``id (regex matches, regex does not match) /regex/i``has id``no id` | `sort by id` | `group by id` | `hide id` | `task.id`  
`has depends on``no depends on` |  |  | `hide depends on` | `task.dependsOn`  
`is blocked``is not blocked` |  |  |  | `task.isBlocked(query.allTasks)`  
`is blocking``is not blocking` |  |  |  | `task.isBlocking(query.allTasks)`  
**Dates** |  |  |  |   
`done (on, before, after, on or before, on or after) <date>``done (in, before, after, in or before, in or after) ...``... YYYY-MM-DD YYYY-MM-DD``... (last, this, next) (week, month, quarter, year)``... (YYYY-Www,YYYY-mm, YYYY-Qq, YYYY)``has done date``no done date``done date is invalid` | `sort by done` | `group by done` | `hide done date` | `task.done`  
`created (on, before, after, on or before, on or after) <date>``created (in, before, after, in or before, in or after) ...``... YYYY-MM-DD YYYY-MM-DD``... (last, this, next) (week, month, quarter, year)``... (YYYY-Www,YYYY-mm, YYYY-Qq, YYYY)``has created date``no created date``created date is invalid` | `sort by created` | `group by created` | `hide created date` | `task.created`  
`starts (on, before, after, on or before, on or after) <date>``starts (in, before, after, in or before, in or after) ...``... YYYY-MM-DD YYYY-MM-DD``... (last, this, next) (week, month, quarter, year)``... (YYYY-Www,YYYY-mm, YYYY-Qq, YYYY)``has start date``no start date``start date is invalid` | `sort by start` | `group by start` | `hide start date` | `task.start`  
`scheduled (on, before, after, on or before, on or after) <date>``scheduled (in, before, after, in or before, in or after) ...``... YYYY-MM-DD YYYY-MM-DD``... (last, this, next) (week, month, quarter, year)``... (YYYY-Www,YYYY-mm, YYYY-Qq, YYYY)``has scheduled date``no scheduled date``scheduled date is invalid` | `sort by scheduled` | `group by scheduled` | `hide scheduled date` | `task.scheduled`  
`due (on, before, after, on or before, on or after) <date>``due (in, before, after, in or before, in or after) ...``... YYYY-MM-DD YYYY-MM-DD``... (last, this, next) (week, month, quarter, year)``... (YYYY-Www,YYYY-mm, YYYY-Qq, YYYY)``has due date``no due date``due date is invalid` | `sort by due` | `group by due` | `hide due date` | `task.due`  
`cancelled (on, before, after, on or before, on or after) <date>``cancelled (in, before, after, in or before, in or after) ...``... YYYY-MM-DD YYYY-MM-DD``... (last, this, next) (week, month, quarter, year)``... (YYYY-Www,YYYY-mm, YYYY-Qq, YYYY)``has cancelled date``no cancelled date``cancelled date is invalid` | `sort by cancelled` | `group by cancelled` | `hide cancelled date` | `task.cancelled`  
`happens (on, before, after, on or before, on or after) <date>``happens (in, before, after, in or before, in or after) ...``... YYYY-MM-DD YYYY-MM-DD``... (last, this, next) (week, month, quarter, year)``... (YYYY-Www,YYYY-mm, YYYY-Qq, YYYY)``has happens date``no happens date` | `sort by happens` | `group by happens` |  | `task.happens`  
**Recurrence** |  |  |  |   
`is recurring``is not recurring` | `sort by recurring` | `group by recurring` |  | `task.isRecurring`  
`recurrence (includes, does not include) <string>``recurrence (regex matches, regex does not match) /regex/i` |  | `group by recurrence` | `hide recurrence rule` | `task.recurrenceRule`  
**On Completion** |  |  |  |   
|  |  | `hide on completion` | `task.onCompletion`  
**Priority** and **urgency** |  |  |  |   
`priority is (above, below, not)? (lowest, low, none, medium, high, highest)` | `sort by priority` | `group by priority` | `hide priority` | `task.priorityName``task.priorityNameGroupText``task.priorityNumber`  
| `sort by urgency` | `group by urgency` | `show urgency` | `task.urgency`  
**File properties** |  |  |  |   
`path (includes, does not include) <path>``path (regex matches, regex does not match) /regex/i``path includes {{query.file.path}}``path includes {{query.file.pathWithoutExtension}}` | `sort by path` | `group by path` |  | `task.file.path``task.file.pathWithoutExtension``query.file.path``query.file.pathWithoutExtension`  
`root (includes, does not include) <root>``root (regex matches, regex does not match) /regex/i``root includes {{query.file.root}}` |  | `group by root` |  | `task.file.root``query.file.root`  
`folder (includes, does not include) <folder>``folder (regex matches, regex does not match) /regex/i``folder includes {{query.file.folder}}` |  | `group by folder` |  | `task.file.folder``query.file.folder`  
`filename (includes, does not include) <filename>``filename (regex matches, regex does not match) /regex/i``filename includes {{query.file.filename}}``filename includes {{query.file.filenameWithoutExtension}}` | `sort by filename` | `group by filename` |  | `task.file.filename``task.file.filenameWithoutExtension``query.file.filename``query.file.filenameWithoutExtension`  
`heading (includes, does not include) <string>``heading (regex matches, regex does not match) /regex/i` | `sort by heading` | `group by heading` |  | `task.hasHeading``task.heading`  
|  | `group by backlink` | `hide backlink` |   
**Obsidian Properties** |  |  |  | `task.file.hasProperty('property name')``task.file.property('property name')``query.file.hasProperty('property name')``query.file.property('property name')`  
**Description** , **Tags** and other odds and ends |  |  |  |   
`description (includes, does not include) <string>``description (regex matches, regex does not match) /regex/i` | `sort by description` |  |  | `task.description``task.descriptionWithoutTags`  
`has tags``no tags``tag (includes, does not include) <tag>``tags (include, do not include) <tag>``tag (regex matches, regex does not match) /regex/i``tags (regex matches, regex does not match) /regex/i` | `sort by tag``sort by tag <tag_number>` | `group by tags` | `hide tags` | `task.tags`  
|  |  | `show tree` |   
|  |  |  | `task.originalMarkdown``task.lineNumber`  
| `sort by random` |  |  |   
**Scripting** |  |  |  |   
`filter by function` | `sort by function` | `group by function` |  |   
**Combining Filters** |  |  |  |   
`(filter 1) AND (filter 2)` |  |  |  |   
`(filter 1) OR (filter 2)` |  |  |  |   
`NOT (filter 1)` |  |  |  |   
`(filter 1) XOR (filter 2)` |  |  |  |   
`(filter 1) AND NOT (filter 2)` |  |  |  |   
`(filter 1) OR NOT (filter 2)` |  |  |  |   
`(filter 1) AND ((filter 2) OR (filter 3))` |  |  |  |   
**Other Filter Options** |  |  |  |   
`exclude sub-items` |  |  |  |   
`limit to <number> tasks``limit <number>` |  |  |  |   
`limit groups to <number> tasks``limit groups <number>` |  |  |  |   
**Other Layout Options** |  |  |  |   
`hide edit button` |  |  |  |   
`hide postpone button` |  |  |  |   
`hide task count` |  |  |  |   
`short mode` |  |  |  |   
`full mode` |  |  |  |   
**Other Instructions** |  |  |  |   
`ignore global query` |  |  |  |   
`explain` |  |  |  |   
`# comment` |  |  |  |   
Quick Reference


================================================================================

## 15. https://publish.obsidian.md/tasks/Reference/Task+Formats/About+Task+Formats


```

# About Task Formats 
#task-formats #index-pages
## What is a "Task Format"? 
In this project, we use "Task Format" to refer to the characters to include in a task line in Markdown to express that task's properties, such as Due date and Priority.
Since its creation, the Tasks plugin has only ever used Emoji characters such as 📅 and ⏫.
## Selecting the task format 
Released
Introduced in Tasks 3.3.0.
You can now choose the task format that Tasks will use to read and write data on task lines:
!Screenshot of the settings option to select Task Format
About Task Formats


================================================================================

## 16. https://publish.obsidian.md/tasks/What+is+New/Changelog


```

# Urgency 
## Introduction 
By default, Tasks sorts query results by decreasing urgency. Tasks tries to calculate urgency based on what you should likely work on next.
The urgency score isn't perfect, of course, as many more factors may influence the order on which you want to work on tasks. Urgency can only consider the parameters it knows: dates and priorities. It is likely that the task you want to work on next is one of the tasks at the top of the list.
The idea of Tasks' urgency is based on Taskwarrior's concept of urgency.
## How Urgency is Calculated 
Urgency is a numeric score that Tasks calculates for each task. Tasks simply sums up urgency scores of different aspects of a task:
  1. Due date
  2. Priority
  3. Scheduled date
  4. Start date


As you can tell from the table below, **due dates have the strongest influence on urgency.**
Urgency


================================================================================

## 18. https://publish.obsidian.md/tasks/Advanced/Tasks+Api


```

# Tasks API 
#plugin/quickadd
## Tasks API Interface 
Released
The Tasks API Interface was introduced in Tasks 2.0.0.
Tasks exposes an API that can be used to integrate Tasks in other Plugins, scripts or dynamic code blocks.
The Tasks API is available from `app.plugins.plugins['obsidian-tasks-plugin'].apiV1`, where `app` is the Obsidian App. A reference to the Obsidian App is usually available via `this.app`, however, this depends on the context of the executing script.
This is the interface the API exposes:
```
/**
 * Tasks API v1 interface
 */
export interface TasksApiV1 {
  /**
   * Opens the Tasks UI and returns the Markdown string for the task entered.
   *
   * @returns {Promise<string>} A promise that contains the Markdown string for the task entered or
   * an empty string, if data entry was cancelled.
   */
  createTaskLineModal(): Promise<string>;
  /**
   * Executes the 'Tasks: Toggle task done' command on the supplied line string
   *
   * @param line The markdown string of the task line being toggled
   * @param path The path to the file containing line
   * @returns The updated line string, which will contain two lines
   *     if a recurring task was completed.
   */
  executeToggleTaskDoneCommand: (line: string, path: string) => string;
}

```

Tasks Api


================================================================================

## 19. https://publish.obsidian.md/tasks/Editing/Auto-Suggest


aliases:
 - Getting Started/Auto-Suggest
```

# Intelligent Auto-Suggest 
## Introduction 
Released
Introduced in Tasks 1.9.0.
The Priorities, Dates, Recurring Tasks, Task Dependencies and On Completion pages show various emojis and special phrases that the Tasks plugin recognises, when searching for tasks.
If you prefer to type your tasks, instead of using a dialog, there is now an intelligent auto-suggest completion mechanism that does a lot of the typing of emojis and dates for you.
It is particularly powerful when creating and editing tasks on mobile phones.
Released
  * `➕ created today` was introduced in Tasks 3.2.0.
  * `🆔 id` and `⛔ depends on id` were introduced in Tasks 7.4.0.


Developers of other task plugins may offer this Auto-Suggest facility to their users: see Auto-Suggest Integration.
### Video Demo 
Auto-Suggest


================================================================================

## 20. https://publish.obsidian.md/tasks/Getting+Started/Dates


```

# Dates 
#feature/dates
## When to work on a task 
This section explains the different types of date that you can add to task lines, in order to tell Tasks when you wish/need to do the work.
You don't have to use all available dates. Maybe due dates are sufficient for you. Don't over-engineer your task management.
Info
Instead of adding an emoji and a date manually, you can use the `Tasks: Create or edit` command when creating or editing a task. When you use the command, you can also set dates like "Monday", "tomorrow", or "next week" and Tasks will automatically save the date in the correct format. You can find out more in ‘Create or edit Task’ Modal.
Info
If you prefer to type, it is now very easy to add emojis and other information for your tasks using Intelligent Auto-Suggest.
Dates


================================================================================

## 21. https://publish.obsidian.md/tasks/Advanced/Daily+Agenda


```

# Priority 
## Priorities and Order 
Tasks can have a priority. In order to specify the priority of a task, you can append one of the "priority signifiers", shown here in decreasing order of priority:
  1. 🔺 for highest priority
  2. ⏫ for high priority
  3. 🔼 for medium priority
  4. use no signifier to indicate no priority
  5. 🔽 for low priority
  6. ⏬️ for lowest priority


If a task has no priority at all, it is considered between low and medium priority. This means that the priority of 🔽 low tasks is considered lower than the priority of tasks without any specific priority. The idea is that you can easily filter out unimportant tasks without needing to assign a priority to all relevant tasks.
```
- [ ] take out the trash 🔼

```

Released
Priorities 'lowest' and 'highest' were introduced in Tasks 3.9.0.
## Easy adding of Priorities 
Instead of adding the emoji manually, you can:
  * Use the `Tasks: Create or edit` command when creating or editing a task. You will be able to select the priority from the options in the ‘Create or edit Task’ Modal.
  * Using Intelligent Auto-Suggest, start typing the first few characters of `high`, `medium` or `low`, and press `<return>` to accept the suggested signifier.


## Related Tasks Block Instructions 
The following instructions use the priority signifiers in tasks.
  * `priority is (above, below)? (lowest, low, none, medium, high, highest)`
    * Documentation
  * `sort by priority`
    * Documentation
  * `group by priority`
    * Documentation
  * `hide priority`
    * Documentation
  * Accessible as task properties:
    * `task.priorityNumber`
    * `task.priorityName`
    * `task.priorityNameGroupText`



================================================================================

## 24. https://publish.obsidian.md/tasks/Editing/Toggling+and+Editing+Statuses


```

# Toggling and Changing Task Statuses 
#feature/statuses
## Summary 
This page describes ways to mark a task line as `TODO` or `DONE`, or any other Statuses and Custom Statuses your vault may be configured to use.
You can left-click or right-click on task checkboxes.
Other options are a command and a modal.
What is "toggling"?
The simplest meaning of 'toggling' is converting a task between these two states:
  1. `- [ ] ...` - meaning `to do`.
  2. `- [x] ...` - meaning `done`.


## Toggling Tasks with mouse 
The most common way to change a task status is to **single-click on its checkbox**.
Where | Viewing Mode | Works?  
---|---|---  
Task lines in markdown files | Source mode | ❌  
Task lines in markdown files | Live Preview | ✅  
Task lines in markdown files | Reading mode | ✅  
In Tasks query search results | Live Preview | ✅  
In Tasks query search results | Reading mode | ✅  
## 'Change task status' context menu 
**Right-click** or **press-and-hold** on **a task's checkbox** to bring up a menu to allow any known status to be applied to the task.
This works in both **Reading mode** and in **Tasks Query results**.
!Sample 'Change task status' context menu, in a vault with various custom statuses added. Sample 'Change task status' context menu, in a vault with various Custom Statuses added.
Tip
The 'Change task status' context menu does correctly add Done dates, and create new instances of recurring tasks, when appropriate.
The statuses are obtained from the vault's Status Settings.
  * Core Statuses are shown first,
  * then any Custom Statuses.


Changing from one `DONE` status to another:
  * retains any original Done date.
  * does not create a new recurrence of recurring tasks.


Where | Viewing Mode | Works?  
---|---|---  
Task lines in markdown files | Source mode | ❌  
Task lines in markdown files | Live Preview | ❌  
Task lines in markdown files | Reading mode | ✅  
In Tasks query search results | Live Preview | ✅  
In Tasks query search results | Reading mode | ✅  
Released
The 'Change task status' context menu was introduced in Tasks 5.3.0.
## 'Tasks: Toggle task done' command 
There is also a command 'Tasks: Toggle task done'.
Obsidian allows you to assign a hotkey to commands, for ease of use.
Where | Viewing Mode | Works?  
---|---|---  
Task lines in markdown files | Source mode | ✅  
Task lines in markdown files | Live Preview | ✅  
Task lines in markdown files | Reading mode | ❌  
In Tasks query search results | Live Preview | ❌  
In Tasks query search results | Reading mode | ❌  
Since Tasks 7.2.0, this command can also be triggered programmatically via the Tasks API => string;`).
## Edit task modal 
The Create or edit Task modal also allows editing of task statuses.

================================================================================

## 25. https://publish.obsidian.md/tasks/Editing/Create+or+edit+Task


aliases:
 - Getting Started/Create or edit Task
```

# 'Create or edit Task' Modal 
## Introduction 
!Create or Edit Modal The `Tasks: Create or edit` command helps you when adding or editing a task.
## Opening the 'Create or edit Task' Modal 
Use the command 'Tasks: Create or edit task' to launch the modal.
  * If the cursor was on an existing task, the modal will modify that task's properties.
  * If the cursor was on a blank line, the modal will create a brand new task on that line.


## Keyboard shortcuts 
Released
Introduced in Tasks 1.17.0.
All the fields of the form have "access keys", that is, keyboard shortcuts. The access keys are displayed as the underlined letters in the labels.
Create or edit Task


================================================================================

## 26. https://publish.obsidian.md/tasks/Getting+Started/Settings


```

# Settings 
## Restart after changing settings 
Regrettably, many of the settings for customising Tasks require one of the following to be done, for the new options to take effect:
  * Obsidian to be restarted,
  * or the vault to be closed and re-opened.


The Tasks Settings pane warns of this:
!Changing any settings requires a restart of obsidian
## Available settings 
As the number of options in Tasks has grown, we have documented each setting in the page for the relevant topic.
For convenience, here is a list of all those documentation pages (in the order the options appear in the Tasks Settings pane):
Settings


================================================================================

## 27. https://publish.obsidian.md/tasks/Editing/Postponing


```

# Postponing 
#feature/dates
## Introduction 
Tip
Do you ever find that your Task list is full of overdue tasks that you scheduled with the best of intentions?
  * And now you want to postpone many of them, so you can focus on the immediate priorities?
  * Or perhaps you want to remove the date instead?


Then the ⏩ Postpone button is for you!
The ⏩ button in Tasks Search results allows you to quickly postpone (or "snooze") a task until tomorrow or later.
Released
  * Postpone was introduced in Tasks 5.3.0.
  * The ability to remove the existing date was introduced in Tasks 7.3.0.


### Click and Context Menu 
The ⏩ button provides two choices:
  1. **Click the button** to advance the date to the **earlier** of:
     * tomorrow
     * the day after its current date !Tooltip on the Postpone button shows tomorrow's date, for dates before or on today **Tooltip** on the Postpone button shows **tomorrow's date** , for dates **before or on today**. !Tooltip on the Postpone button shows 'postpone by day', for future dates. **Tooltip** on the Postpone button shows '**postpone by day** ', for **future dates**.
  2. **Right-click** or **press-and-hold** the button to select from a context menu with:
     * future dates in the next 6 days
     * more future dates, further ahead
     * an option to remove the date instead: !Context menu on the Postpone button shows options for dates before or on today **Context menu** on the Postpone button shows options for dates **before or on today** !Context menu on the Postpone button shows options for future dates. **Context menu** on the Postpone button shows options for **future dates**.


Postponing


================================================================================

## 28. https://publish.obsidian.md/tasks/Editing/Editing+Dates


```

# Editing Dates 
#feature/dates
## Summary 
Tasks supports a range of date properties for managing your tasks: see Dates.
This page describes ways to add, edit and remove date values on tasks.
There is a Date-picker on task dates and a Context menu on task dates, or you can use various other date-editing options.
## Date-picker on task dates 
Released
Introduced in Tasks 7.14.0.
**Left-click on any task date field** in **Reading mode** and **Tasks query search results** to use a date-picker and calendar to edit or remove a date.
Editing Dates


================================================================================

## 29. https://publish.obsidian.md/tasks/Advanced/Styling


```

# Styling Tasks 
#css
## Introduction 
Released
Almost all the features below were introduced in Tasks 3.0.0.
In rendered queries and Reading View, the Tasks plugin adds detailed CSS classes and data attributes that represent many of each task's content, to allow for very extensive styling options via CSS. Not only each component in a rendered task line is tagged with classes to differentiate it, many components also add classes and data attributes that represent the actual content of the task, so CSS rules can refer to data such as the relative due date of a task or its specific priority.
### Please share your styles online 
We invite Tasks users who create their own Obsidian CSS snippets to share them in the "Show and tell" Discussions category - to inspire others and allow them to use and learn from your CSS and design skills.
Thank you in advance!
### Backwards compatibility and CSS snippets 
Warning
If you find any existing Tasks CSS snippets stopped working with Tasks 3.0.0, follow the advice in Appendix: Fixing CSS pre-existing snippets for Tasks 3.0.0 below.
## Basic Task Structure 
Released
The following description relates to a restructuring of the rendered tasks that was introduced in Tasks 3.0.0.
The Tasks plugin renders a task in the following structure (this refers to query results, but the Reading View is the same except the top-most containers):
```
- Obsidian code block (div class="block-language-tasks")
 - Results list (ul class="plugin-tasks-query-result") OR Reading View list (ul class="contains-task-list")
  - Task (li class="task-list-item" + attributes like data-task-priority="medium" data-task-due="past-1d" + data-task="[custom_status]" + data-line="[line]")
   - Task checkbox (li class="task-list-item-checkbox")
   - Task content (span class="tasks-list-text")
    - Task description and tags (span class="task-description")
     - Internal span
      - Each tag in the description is wrapped in <a href class="tag" data-tag-name="[tag-name]">
    - Task ID (span class="task-id")
     - Internal span
    - Task 'depends on' (span class="task-dependsOn")
     - Internal span
    - Task priority (span class="task-priority" + data-task-priority attribute)
     - Internal span
    - Task recurrence rule (span class="task-recurring")
     - Internal span
    - Task 'on completion' (span class="onCompletion")
     - Internal span
    - Task created date (span class="task-created" + data-task-created attribute)
     - Internal span
    - ... start date, scheduled date, due date, cancelled date and done date in this order
   - Task extras (link, edit button, postpone button) (span class="task-extras")
 - Tasks count (div class="tasks-count")

```

As can be seen above, the basic task `li` contains a checkbox and a content span. The content span contains a list of **component** spans: description, priority, recurrence, created date, start date, scheduled date, due date, cancelled date and done date in this order.
Each component span is marked with a **generic class** , which denotes the type of the component, and in some cases a **data attribute** that represents the component's content itself.
Within each component span there is an additional "internal" span, which is the one holding the actual component text. The reason for this additional internal span is that it allows CSS styles that closely wrap the text itself, rather than its container box, e.g. for the purpose of drawing a highlight or a box that is exactly in the size of the text.
### Sample HTML: Full mode 
To help visualise the structure above, below is the HTML for a sample Tasks search shown in full mode.
Note
In Reading Mode:
  * all the classes and data inside the `li` are available,
  * and none of the "Task extras" content is available.


Sample HTML: Full mode
### Sample HTML: Short mode 
Below is the same Tasks search in short mode.
Note
The differences from Full mode are:
  * the `ul` has an extra class `tasks-layout-short-mode`,
  * any text values after Tasks emoji are omitted,
  * the backlink is shorter and has an extra class `internal-link-short-mode`,
  * the postpone button has an extra class `tasks-postpone-short-mode`.


Sample HTML: Short mode
## Generic Classes and Data Attributes 
Released
Data attributes were introduced in Tasks 3.0.0.
Each rendered task component (description, priority, recurrence rule etc) includes a **generic class** that denotes this type of component. The generic classes are:
Styling


================================================================================

## 30. https://publish.obsidian.md/tasks/Getting+Started/Recurring+Tasks


```

# Recurring Tasks (Repetition) 
## Usage 
Tasks can be recurring. In order to specify a recurrence rule of a task, you must append the "recurrence signifier 🔁" followed by the recurrence rule. For example: `🔁 every weekday` means the task will repeat every week on Monday through Friday. Every recurrence rule has to start with the word `every`.
When you toggle the status of a recurring task to anything but "todo" (i.e. "done"), the original task that you wanted to toggle will be marked as done and get the done date appended to it, like any other task.
In addition, _a new task will be put one line above the original task_ by default.
See Order of the new task below, for how to change this behaviour and make the new task appear _on the line below the original task_.
The new task will have updated dates based off the original task.
Tip
If you only want the latest occurrence, and don't care to see the clutter of all the earlier tasks, check out the new On Completion facility, added in Tasks 7.8.0.
### Basic Example 
Recurring Tasks


================================================================================

## 31. https://publish.obsidian.md/tasks/Advanced/Notifications


```

# Getting Started 
## Finding tasks in your vault 
Tasks tracks your checklist items from your vault. The simplest way to create a new task is to create a new checklist item. The markdown syntax for checklist items is a list item that starts with spaced brackets:
```
- [ ] take out the trash

```

Now Tasks tracks that you need to take out the trash!
Info
You can write tasks using any of the following list styles:
```
- [ ] task starting with a hyphen
* [ ] task starting with an asterisk
+ [ ] task starting with a plus sign
1. [ ] a task in a numbered list with a `.` character
2) [ ] a task in a numbered list with a `)` character

```

Released
  * Support for tasks with `+` was introduced in Tasks 4.5.0.
  * Support for numbered lists with `)` was introduced in Tasks 7.18.5.


To list all open tasks in a markdown file, simply add a query as a tasks code block like so:
```
  ```tasks
  not done
  ```

```

Getting Started


================================================================================

## 33. https://publish.obsidian.md/tasks/Getting+Started/Installation


aliases:
 - Installation/Installation
 - Installation
```

# Installation 
Follow the steps below to install Tasks.
  1. Search for "Tasks" in Obsidian's community plugins browser
  2. Enable the plugin in your Obsidian settings (find "Tasks" under "Community plugins").
  3. Check the settings. It makes sense to set the global filter early on (if you want one).
  4. Replace the "Toggle Checkbox Status" hotkey with "Tasks: Toggle Done". 
     * I recommend you remove the original toggle checkbox hotkey and set the "Tasks" toggle to `Ctrl + Enter` (or `Cmd + Enter` on a mac).
  5. Optional: bind a hotkey to the command `Tasks: Create or edit` to have quick access to the Tasks modal.


Installation


================================================================================

## 34. https://publish.obsidian.md/tasks/Getting+Started/Obsidian+Properties


```

# Obsidian Properties 
Released
Use of Obsidian Properties was introduced in Tasks 7.7.0.
## What are Obsidian Properties? 
Obsidian offers a facility called Properties.
Properties allow you to organize information about a note. Properties contain structured data such as text, links, dates, checkboxes, and numbers.
This is an example property section, and it _must_ appear on the very first line of the markdown file:
```
---
name: value
---

```

In the Tasks documentation, we refer to these as Obsidian Properties, to distinguish them from Task and Query properties.
Background reading on Obsidian Properties:
Obsidian Properties


================================================================================

## 35. https://publish.obsidian.md/tasks/Getting+Started/Global+Filter


```

# Global Filter 
Tip
Since Tasks 3.5.0, a new Global Query facility has been added, which offers a lot more flexibility than the Global Filter.
## Optional Global Filter 
You can set a global filter in the settings so that Tasks only matches specific checklist items. For example, you could set it to `#task` to only track checklist items as task if they include the string `#task`. It doesn't have to be a tag. It can be any string. Leave it empty to regard all checklist items as tasks.
Example with global filter `#task`:
```
- [ ] #task take out the trash

```

If you don't have a global filter set, all regular checklist items will be considered a task:
```
- [ ] take out the trash

```

Warning
If you use a tag such as `#task` as the global filter, you cannot add sub-tags to that tag.
Global Filter


================================================================================

## 36. https://publish.obsidian.md/tasks/Queries/Comments


```

# Examples 
All open tasks that are due today:
```
```tasks
not done
due today
```

```

All open tasks that are due within the next two weeks, but are not overdue (due today or later):
```
```tasks
not done
due AFTER yesterday
due BEFORE in two weeks
```

```

Most query instructions can include capital letters, which are used here for emphasis.
All open tasks that are due within the next two weeks, and either have the `#inbox` tag, or are in an Inbox note:
Examples


================================================================================

## 39. https://publish.obsidian.md/tasks/Getting+Started/Statuses/Status+Types


```

# Statuses 
#feature/statuses
## Introduction 
Released
Custom Statuses were introduced in Tasks 1.23.0.
This page provides an overview of using Tasks with **Custom Statuses** , which some people refer to as Custom Checkboxes or Alternative/Alternate Checkboxes.
Here's the kind of thing that you can do:
!Selection of checkboxes from Minimal theme !Selection of checkboxes from ITS theme
### Related pages 
Once you're comfortable with the background information in this page, further information is available in the following related pages.
  * How to style custom statuses.
  * How to set up your custom statuses.
  * About Status Collections.
  * Check your Statuses.


## Do I need to set up statuses? 
If you are happy with all your tasks beginning with `[ ]` and `[x]`, then **no** , you can just ignore Tasks' Statuses facility.
## About Statuses 
### What IS a Status? 
Every task in the Tasks plugin now has a Status.
Status is just Tasks' name for:
  1. the character (`symbol`) between the `[` and `]` in a task line
  2. AND some options that you can customise, to tell tasks how to treat all your tasks with that character.


Some obsidian users call them other names, like 'Alternative Checkboxes', but that is more about how they are displayed, rather than about the actual _behaviour_ of tasks with particular statuses.
### What's IN a Status? 
These are the options that you can modify, for each status:
!Task Status modal
Here is some more detail.
  * **Status Symbol**
    * the single character in the `[]` at the start of the task.
    * this character will control what how tasks are rendered by your Theme or CSS Snippet.
  * **Status Name**
    * a name for the status.
    * this is flexible: for custom statuses, you can use any name you wish.
    * is searchable with `status.name`, for example `status.name includes My custom in-progress status`.
  * **Next Status Symbol**
    * the status symbol to use when the task is toggled.
  * **Status Type**
    * one of `TODO`, `IN_PROGRESS`, `DONE`, `CANCELLED`, `NON_TASK`.
    * Tasks needs to know the type of each status, so that it knows how to treat them when searching, and what to do when tasks with the status are toggled.
    * types are searchable with `status.type`, for example `status.type is IN_PROGRESS`.
    * Also available: 
      * `sort by status.type`
      * `group by status.type`
    * For more information, see Status Types


### Unknown Statuses 
What happens if Tasks reads a line with a status symbol that it does not know about?
All such tasks are given a status called `Unknown`, with these properties:
Property | Value  
---|---  
Status Symbol | The unrecognised character between the `[` and `]` in the task line  
Status Name | **Unknown**  
Next Status Symbol | `x`  
Status Type | `TODO`  
### Done date, Recurrence and Statuses 
It is the Task Status Type changing **to** `DONE` that controls when:
  * tasks **gain** their Done dates (if Done dates are enabled in settings),
  * new copies of recurring tasks are created.


It is the Task Status Type changing **from** `DONE` that controls when:
  * tasks **lose** their Done dates (if Done dates are enabled in settings).


See Recurring Tasks and Custom Statuses for a more thorough explanation of the above.
## What can Statuses do? 
Now we have seen what is in a Status, what can we do with them?
We can use them to control what Tasks does when a task's checkbox is clicked, or toggled.
The Example Statuses page has a variety of examples, for inspiration.
## More about Statuses 
### Core Statuses 
Core statuses represent conventional markdown tasks:
```
- [ ] I am a task that is not yet done
- [x] I am a task that has been done

```

They don't require any custom CSS styling or theming on order to display correctly in Tasks blocks or Live Preview.
Before Tasks 1.23.0, these were the only statuses that Tasks knew about.
See Core Statuses to find out more.
### Custom Statuses 
Custom statuses represent any non-standard markdown tasks.
Here are some tasks with example custom statuses, that is, with non-standard characters between the `[` and `]`:
```
- [X] Checked
- [-] A dropped/cancelled task
- [?] A question
- [/] A Half Done/In-progress task

```

They **require custom CSS styling or theming** on order to display correctly in Tasks blocks or Live Preview.
### What's the Big Deal? 
People have been using themes and CSS snippets to style custom checkboxes in Obsidian all along.
What Tasks' custom statuses allow you to do is to **also customise the behaviour of your tasks**.
### Setting up Custom Statuses 
Info
Broad steps to understand and set up Statuses (or "Alternate Checkboxes"):
  * Understand what Statuses are: 
    * Statuses
    * Custom Statuses
  * Choose your status styling scheme: this will determine the names and symbols for your custom statuses: 
    * Some common ones are shown in About Status Collections
  * Set up your status styling scheme 
    * How to style custom statuses.
  * Configure Tasks to use your custom statuses 
    * How to set up your custom statuses
    * Check your Statuses
  * Optionally, update your tasks searches to take advantage of the new flexibility 
    * Filters for Task Statuses


## Using Statuses 
### Editing your tasks 
The ‘Create or edit Task’ Modal allows you to change the status of a task.
### Related commands 
Info
There are not yet any new commands for applying custom statuses. We are tracking this in issue #1486 .
### Related searches 
  * `done` - matches tasks with status types `DONE`, `CANCELLED` and `NON_TASK`
  * `not done` - matches tasks with status types `TODO` and `IN_PROGRESS`
  * **Status Name**
    * `status.name` text search
    * `sort by status.name`
    * `group by status.name`
  * **Status Type**
    * `status.type` text search
    * `sort by status.type`
    * `group by status.type`


For details, see Filters for Task Statuses
Info
We envisage adding `status.symbol`. We are tracking this in issue #1630.
## Credit: Sytone and the 'Tasks SQL Powered' plugin 
This plugin's implementation of reading, searching and editing custom statuses was entirely made possible by the work of Sytone and his fork of Tasks called 'Tasks SQL Powered'. [[1]](https://publish.obsidian.md/tasks/Getting+Started/Statuses#fn-1-1559f1c5e9eff7c2)
Where code in Tasks has been copied from 'Tasks SQL Powered', Sytone has been specifically credited as a co-author, that is, joint author, and these commits can be seen on the GitHub site: Commits "Co-Authored-By: Sytone".
Subsequently, the custom statuses implementation in Tasks has diverged from the 'Tasks SQL Powered' significantly. However, none of the new features and fixes would have been possible without Sytone's foundation work, for which we are very grateful.
  1. 'Tasks SQL Powered' as of revision 2c0b659 on 2 August 2022↩︎



================================================================================

## 41. https://publish.obsidian.md/tasks/Getting+Started/Statuses/Status+Settings


```

# Status Settings 
#feature/statuses
## Overview 
This is what you see in the Tasks settings when you first look at the Task Statuses section:
!Initial Task Statuses Settings _Initial Task Statuses Settings_
There are two sections:
  1. **Core Statuses**
     * These are statuses that are built in to Tasks, and cannot be deleted.
     * They are the two task types that are built in to Obsidian and Tasks natively: `[ ]` and `[x]`.
     * Their status symbols cannot be changed.
     * All their other properties can be edited.
  2. **Custom Statuses**
     * These statuses are what many themes call 'custom checkboxes'.
     * You will need to choose and install a Theme or CSS Snippet that supports 'custom checkboxes'
     * Tasks automatically adds `[/]` and `[-]`
     * And this is where you can add your own custom statuses.


We also see that each status consists of:
  * **Status Symbol** (for example, `x` and `-`)
  * **Status Name** (for example, 'In Progress')
  * **Next Status Symbol** (for example, `x` and `space`)
  * **Status Type** (one of `TODO`, `DONE`, `IN_PROGRESS` or `CANCELLED`)


Status Settings


================================================================================

## 42. https://publish.obsidian.md/tasks/Getting+Started/Use+Filename+as+Default+Date


```

# Use Filename as Default Date 
## Automatic scheduled date 
Released
  * Introduced in Tasks 1.18.0.
  * Support for filenames exactly matching a custom format added in 7.6.0.


You can automatically set a scheduled date for tasks based on the name of their files. This feature can be enabled in the settings, via the option `Use filename as Scheduled date for undated tasks`. Changing this requires a restart of Obsidian.
This allows you, for instance, to make all the tasks in your daily notes be considered as scheduled. You can then query them using the `scheduled` and `happens` filters.
Example query :
```
```tasks
scheduled before today
group by scheduled
not done
```

```

Seeing implied dates
  * The task is not visually modified in any Obsidian views: the scheduled date is only implied, and not displayed.
  * It will however appear in the edit dialog.
  * It can also be examined by using the `group by scheduled` instruction in a tasks block.


## Rules 
Use Filename as Default Date


================================================================================

## 43. https://publish.obsidian.md/tasks/Queries/Filters


```

# Filters 
#feature/filters
## Contents 
This page is long. Here are some links to the main sections:
  * Custom Filters
  * Searching for dates
  * Text filters
  * Matching multiple filters
  * Filters for Task Statuses
  * Filters for Task Dependencies
  * Filters for Dates in Tasks
  * Filters for Other Task Properties
  * Filters for File Properties
  * Appendix: Tasks 2.0.0 improvements to date filters


## Custom Filters 
Released
`filter by function` was introduced in Tasks 4.2.0.
Tasks provides many built-in filtering options, but sometimes they don't quite do what is wanted by all users.
Filters


================================================================================

## 44. https://publish.obsidian.md/tasks/Getting+Started/Statuses/Recurring+Tasks+and+Custom+Statuses


```

# Custom Statuses 
#feature/statuses
## Introduction 
Released
Custom Statuses were introduced in Tasks 1.23.0.
Custom statuses represent any non-standard markdown tasks.
Here are some tasks with example custom statuses, that is, with non-standard characters between the `[` and `]`:
```
- [X] Checked
- [-] A dropped/cancelled task
- [?] A question
- [/] A Half Done/In-progress task

```

They **require custom CSS styling or theming** in order to display correctly in Tasks blocks or Live Preview.
Here's the kind of thing that you can do with custom statuses and styling:
Custom Statuses


================================================================================

## 49. https://publish.obsidian.md/tasks/How+To/Style+custom+statuses


alias:
- Backlink
- Getting Started/Backlinks
```

# Backlinks 
#feature/backlinks
## What are backlinks? 
In Tasks search results, by default each task is displayed with its filename, and the name of the previous heading, for example `(ACME > Steps to world domination)`. This is called a **backlink**.
This screenshot shows what this might look like, with some sample data:
!Tasks with vanilla backlink styles
If the filename and previous heading are identical, or if there is no previous heading, only the filename is shown.
## Using backlinks for navigation 
You can click on a backlink to navigate directly to the task's source line.
Tip
This honours the standard Obsidian keyboard modifiers used when clicking on internal links, to control how the note is opened (Navigate, New Tab, New Tab Group, New Window).
See the table in the Tabs section of the Obsidian 1.0.0 release notes.
Released
Navigating directly to the task line was introduced in Tasks 3.4.0.
## Support 
We use the label `scope: backlinks` to track feedback on backlinks:
  * Open Backlink-related Issues
  * Open Backlink-related Discussions


Backlinks


================================================================================

## 51. https://publish.obsidian.md/tasks/Getting+Started/Statuses/Check+your+Statuses


```

# Combining Filters 
## Summary 
Released
  * Introduced in Tasks 1.9.0.
  * Major improvements in Tasks 7.0.0: for details, see Appendix Changes to Boolean filters in Tasks 7.0.0.


The individual filters provided by Tasks can be combined together in powerful ways, by:
  1. wrapping each of them in delimiters such as `(` and `)`,
  2. then joining them with boolean operators such as `AND`, `OR` and `NOT`.


For example:
```
```tasks
not done
(due after yesterday) AND (due before in two weeks)
[tags include #inbox] OR [path includes Inbox] OR [heading includes Inbox]
```

```

Each of the 3 lines in the above tasks block represents an individual filter, and only tasks which match _all_ 3 of the filter lines will be displayed.
## Syntax 
Combining Filters


================================================================================

## 53. https://publish.obsidian.md/tasks/Getting+Started/Task+Dependencies


```

# Task Dependencies 
## Introduction 
Released
Task Dependencies were introduced in Tasks 6.1.0.
At a high level, task dependencies define the order in which you want to work on a set of tasks. This can be useful for mapping out projects, where one part needs to be completed before the other. By specifying these dependencies, Obsidian Tasks can streamline your workflow by displaying only the tasks that are actionable at any given moment.
Note
The Tasks plugin exclusively allows for 'Finish to start (FS)' dependencies, meaning Task A needs to be finished before you start on Task B. You can learn more about this concept on Wikipedia).
Tip
This page explains the dependencies facility and how to use it.
For an explanation of how to add and edit dependencies between tasks, see Create or edit Task > Dependencies.
## Sample dependency 
Here is an example dependency, to tell Tasks that the second task cannot be started until the first task is completed:
### Tasks Emoji format sample 
  * The first task has an **`id`**field with the value`abcdef`.
  * The second task has a **`dependsOn`**which is the same value`abcdef` , and is a reference or pointer to the first task.


```
flowchart BT
classDef TASK    stroke-width:3px,font-family:monospace;
2["\- [ ] do this first 🆔 abcdef"]:::TASK
1["\- [ ] do this after first ⛔ abcdef"]:::TASK
1-- depends on --> 2
linkStyle default stroke:gray

```

### Dataview format sample 
In Dataview format, the above would be written as:
```
flowchart BT
classDef TASK    stroke-width:3px,font-family:monospace;
2["\- [ ] do this first&nbsp;&nbsp;[id:: abcdef]"]:::TASK
1["\- [ ] do this after first&nbsp;&nbsp;[dependsOn:: abcdef]"]:::TASK
1-- depends on --> 2
linkStyle default stroke:gray

```

## Defining dependencies 
### `id`
Task `id` values consistent of **one or more of the following allowed characters** :
  * `abcdefghijklmnopqrstuvwxyz`
  * `ABCDEFGHIJKLMNOPQRSTUVWXYZ`
  * `0123456789`
  * underscore (`_`)
  * hyphen (`-`)


The following are examples of valid `id` values:
Task Dependencies


================================================================================

## 54. https://publish.obsidian.md/tasks/Getting+Started/Statuses/Core+Statuses


```

# Core Statuses 
#feature/statuses
## Overview 
Core statuses represent conventional markdown tasks:
```
- [ ] I am a task that is not yet done
- [x] I am a task that has been done

```

They don't require any custom CSS styling or theming on order to display correctly in Tasks blocks or Live Preview.
## Core Statuses in Settings 
This is what the Core Statuses look like initially in Tasks' settings:
!Core Statuses
Note that `Todo` is followed by `Done`, in order to preserve compatibility with earlier Tasks releases.
Info
You can edit the 'Todo' core status to make its Next Status Symbol be `/` and enable `Todo` -> `In Progress` -> `Done`, if you prefer.
Tip
Use the "Review and check your Statuses" button at any time to Check your Statuses and to visualise them.
## Editing core statuses 
The only restriction on editing core statuses is that you cannot change their Status Symbols.
You are free to rename them, change their next character, and even change their Status Type, should you wish.
## Details 
And this is how you can use them:
Status Symbol | Next Status Symbol | Status Name`status.name includes...``sort by status.name``group by status.name` | Status Type`status.type is...``sort by status.type``group by status.type` | Needs Custom Styling  
---|---|---|---|---  
`space` | `x` | Todo | `TODO` | No  
`x` | `space` | Done | `DONE` | No  

================================================================================

## 55. https://publish.obsidian.md/tasks/Queries/Explaining+Queries


```

# Explaining Queries 
## Overview: the 'explain' instruction 
Released
Introduced in Tasks 1.19.0.
The `explain` instruction adds some extra output at the start of the search results, when tasks blocks are viewed in Live Preview and Reading modes.
This has a number of benefits:
  * It is easy to understand date-based-filters: 
    * Any dates in filters are expanded, to show the actual dates used in the search.
  * Boolean query logic is clearer. 
    * Combinations of queries (via `AND`, `OR`, `NOT` etc) can be seen more clearly.
  * If there is a global filter enabled, it is included in the explanation. 
    * This often explains why tasks are missing from results.
  * If there is a global query enabled, it too is included in the explanation.
  * Any query file defaults-generated instructions are listed (since Tasks 7.15.0).
  * Any 'group by' instructions are listed (since Tasks 5.4.0).
  * Any 'sort by' instructions are listed (since Tasks 5.4.0).


## Examples 
### Dates in filters are expanded 
For example, when the following text is placed in a tasks query block:
```
starts after 2 years ago
scheduled after 1 week ago
due before tomorrow
explain

```

the results begin with the following, on `2022-10-21`:
```
Explanation of this Tasks code block query:
 starts after 2 years ago =>
  start date is after 2020-10-21 (Wednesday 21st October 2020) OR no start date
 scheduled after 1 week ago =>
  scheduled date is after 2022-10-14 (Friday 14th October 2022)
 due before tomorrow =>
  due date is before 2022-10-22 (Saturday 22nd October 2022)

```

Note how it shows the dates being searched for very clearly, including the day of the week.
It also shows that `starts` searches also match tasks with not start date.
### Regular Expressions are explained 
Released
Introduced in Tasks 4.3.0.
For example, when the following regular expression is placed in a tasks query block:
```
explain
path regex matches /^Root/Sub-Folder/Sample File\.md/i

```

the results begin with the following:
```
Explanation of this Tasks code block query:
 path regex matches /^Root/Sub-Folder/Sample File\.md/i =>
  using regex:   '^Root\/Sub-Folder\/Sample File\.md' with flag 'i'

```

### Boolean combinations are displayed 
Explaining Queries


================================================================================

## 56. https://publish.obsidian.md/tasks/Reference/Task+Formats/Dataview+Format


```

# Grouping 
#feature/grouping
## Contents 
This page is long. Here are some links to the main sections:
  * Basics
  * Custom Groups
  * Group by Task Statuses
  * Group by Task Dependencies
  * Group by Dates in Tasks
  * Group by Other Task Properties
  * Group by File Properties
  * Multiple groups
  * Refining groups
  * Notes
  * Screenshots
  * Examples


## Basics 
Released
Introduced in Tasks 1.6.0.
By default, Tasks displays tasks in a single list.
To divide the matching tasks up with headings, you can add `group by` lines to the query.
## Custom Groups 
Released
`group by function` was introduced in Tasks 4.0.0.
Tasks provides many built-in grouping options, but sometimes they don't quite do what is wanted by all users.
Now Tasks has a powerful mechanism for you to create your own **custom groups** , offering incredible flexibility.
There are many examples of the custom grouping instruction `group by function` in the documentation below, with explanations, for when the `group by` instructions built in to Tasks do not satisfy your preferences.
You can find out more about this very powerful facility in Custom Grouping.
## Group by Task Statuses 
For more information, including adding your own customised statuses, see Statuses.
### Status 
  * `group by status` (Done or Todo, which is capitalized for visibility in the headings) 
    * Note that the Done group is displayed before the Todo group, which differs from the Sorting ordering of this property. 
      * `Done` is used for tasks status types `DONE`, `CANCELLED` and `NON_TASK`
      * `Todo` is used for status types with type `TODO` and `IN_PROGRESS`


Since Tasks 4.0.0, **custom grouping by status** is now possible.
```
group by function task.isDone ? "Action Required" : "Nothing To Do"

```

  * Use JavaScript's ternary operator to choose what to do for true (after the ?) and false (after the :) values.


### Status Name 
  * `group by status.name`
    * This groups by the names you give to your custom statuses, in alphabetical order.


Released
`group by status.name` was introduced in Tasks 1.23.0.
Since Tasks 4.0.0, **custom grouping by status names** is now possible.
```
group by function task.status.name

```

  * Identical to "group by status.name".


```
group by function task.status.name.toUpperCase()

```

  * Convert the status names to capitals.


### Status Type 
  * `group by status.type`
    * This groups by the types you have given to your custom statuses.
    * The groups will appear in this order, and with these group names: 
      * `IN_PROGRESS`
      * `TODO`
      * `DONE`
      * `CANCELLED`
      * `NON_TASK`


Released
`group by status.type` was introduced in Tasks 1.23.0.
Since Tasks 4.0.0, **custom grouping by status types** is now possible.
`task.status.typeGroupText` was added in Tasks 4.9.0.
```
group by function task.status.type

```

  * Unlike "group by status.type", this sorts the status types in alphabetical order.


```
group by function task.status.typeGroupText

```

  * This sorts the status types in the same order as "group by status.type".


### Status Symbol 
There is no built-in instruction to group by status symbols.
Since Tasks 4.0.0, **custom grouping by status symbol** is now possible.
```
group by function "Status symbol: " + task.status.symbol.replace(" ", "space")

```

  * Group by the status symbol, making space characters visible.


### Next Status Symbol 
There is no built-in instruction to group by next status symbols.
Since Tasks 4.0.0, **custom grouping by next status symbol** is now possible.
```
group by function "Next status symbol: " + task.status.nextSymbol.replace(" ", "space")

```

  * Group by the next status symbol, making space characters visible.


## Group by Task Dependencies 
At a high level, task dependencies define the order in which you want to work on a set of tasks. You can read more about them in Task Dependencies.
Released
Task Dependencies were introduced in Tasks 6.1.0.
### Id 
  * `group by id`


For more information, see Task Dependencies.
Released
  * Task Id was introduced in Tasks 6.1.0.


Since Tasks 6.1.0, **custom grouping by Id** is now possible, using `task.id`.
```
group by function task.id

```

  * Group by task Ids, if any.
  * Note that currently there is no way to access any tasks that are blocked by these Ids.


### Depends On 
There is no built-in instruction to group by 'Depends On'.
For more information, see Task Dependencies.
Released
  * Task Depends On was introduced in Tasks 6.1.0.


Since Tasks 6.1.0, **custom grouping by Depends On** is now possible, using `task.dependsOn`.
```
group by function task.dependsOn

```

  * Group by the Ids of the tasks that each task depends on, if any.
  * If a task depends on more than one other task, it will be listed multiple times.
  * Note that currently there is no way to access the tasks being depended on.


## Group by Dates in Tasks 
### Due Date 
  * `group by due`
    * The due date of the task, including the week-day, or `Invalid due date` or `No due date`.


Released
  * `due` grouping option was introduced in Tasks 1.7.0.


Since Tasks 4.0.0, **custom grouping by due date** is now possible.
These examples all use `task.due` property, which is a `TasksDate` object. See Values in TasksDate Properties to explore its capabilities.
Some of these examples use the moment.js format characters.
```
group by function task.due.category.groupText

```

  * Group task due dates in to 5 broad categories: `Invalid date`, `Overdue`, `Today`, `Future` and `Undated`, displayed in that order.
  * Try this on a line before `group by due` if there are a lot of due date headings, and you would like them to be broken down in to some kind of structure.
  * The values `task.due.category.name` and `task.due.category.sortOrder` are also available.


```
group by function task.due.fromNow.groupText

```

  * Group by the time from now, for example `8 days ago`, `in 11 hours`.
  * It uses an empty string (so no heading) if there is no due date.
  * The values `task.due.fromNow.name` and `task.due.fromNow.sortOrder` are also available.


```
group by function task.due.format("YYYY-MM-DD dddd")

```

  * Like "group by due", except it uses no heading, instead of a heading "No due date", if there is no due date.


```
group by function task.due.formatAsDate()

```

  * Format date as YYYY-MM-DD or empty string (so no heading) if there is no due date.


```
group by function task.due.formatAsDateAndTime()

```

  * Format date as YYYY-MM-DD HH:mm or empty string if no due date.
  * Note: 
    * This is shown for demonstration purposes.
    * Currently the Tasks plugin does not support storing of times.
    * Do not add times to your tasks, as it will break the reading of task data.


```
group by function task.due.format("YYYY[%%]-MM[%%] MMM", "no due date")

```

  * Group by month, for example `2023%%-05%% May` ... 
    * ... which gets rendered by Obsidian as `2023 May`.
  * Or show a default heading "no due date" if no date.
  * The hidden month number is added, commented-out between two `%%` strings, to control the sort order of headings.
  * To escape characters in format strings, you can wrap the characters in square brackets (here, `[%%]`).


```
group by function task.due.format("YYYY[%%]-MM[%%] MMM [- Week] WW")

```

  * Group by month and week number, for example `2023%%-05%% May - Week 22` ... 
    * ... which gets rendered by Obsidian as `2023 May - Week 22`.
  * If the month number is not embedded, in some years the first or last week of the year is displayed in a non-logical order.


DON'T PANIC! For users who are comfortable with JavaScript, these more complicated examples may also be of interest:
```
group by function task.due.format("dddd")

```

  * Group by day of the week (Monday, Tuesday, etc).
  * The day names are sorted alphabetically.


```
group by function task.due.format("[%%]d[%%]dddd")

```

  * Group by day of the week (Sunday, Monday, Tuesday, etc).
  * The day names are sorted in date order, starting with Sunday.


```
group by function                  \
  const date = task.due;             \
  if (!date.moment) {               \
    return "Undated";              \
  }                        \
  if (date.moment.day() === 0) {         \
    {{! Put the Sunday group last: }}      \
    return date.format("[%%][8][%%]dddd");   \
  }                        \
  return date.format("[%%]d[%%]dddd");

```

  * Group by day of the week (Monday, Tuesday, etc).
  * The day names are sorted in date order, starting with Monday.
  * Tasks without due dates are displayed at the end, under a heading "Undated".
  * The key technique is to say that if the day is Sunday (`0`), then force it to be displayed as date number `8`, so it comes after the other days of the week.
  * To add comments, we can use `{{! ... }}`
  * To make the expression more readable, we put a `\` at the end of several lines, to continue the expression on the next line.


```
group by function \
  const date = task.due.moment; \
  return \
    (!date)              ? '%%4%% Undated' :   \
    !date.isValid()          ? '%%0%% Invalid date' : \
    date.isBefore(moment(), 'day')  ? '%%1%% Overdue' :   \
    date.isSame(moment(), 'day')   ? '%%2%% Today'  :   \
    '%%3%% Future';

```

  * This gives exactly the same output as `group by function task.due.category.groupText`, and is shown here in case you want to customise the behaviour in some way.
  * Group task due dates in to 5 broad categories: `Invalid date`, `Overdue`, `Today`, `Future` and `Undated`, displayed in that order.
  * Try this on a line before `group by due` if there are a lot of due date headings, and you would like them to be broken down in to some kind of structure.
  * Note that because we use variables to avoid repetition of values, we need to add `return`


```
group by function \
  const date = task.due.moment; \
  return \
    (!date)              ? '%%4%% ==Undated==' :   \
    !date.isValid()          ? '%%0%% ==Invalid date==' : \
    date.isBefore(moment(), 'day')  ? '%%1%% ==Overdue==' :   \
    date.isSame(moment(), 'day')   ? '%%2%% ==Today=='  :   \
    '%%3%% ==Future==';

```

  * As above, but the headings `Invalid date`, `Overdue`, `Today`, `Future` and `Undated` are highlighted.
  * See the sample screenshot below.


```
group by function \
  const date = task.due.moment; \
  const now = moment(); \
  const label = (order, name) => `%%${order}%% ==${name}==`; \
  if (!date)           return label(4, 'Undated'); \
  if (!date.isValid())      return label(0, 'Invalid date'); \
  if (date.isBefore(now, 'day')) return label(1, 'Overdue'); \
  if (date.isSame(now, 'day'))  return label(2, 'Today'); \
  return label(3, 'Future');

```

  * As above, but using a local function, and `if` statements.


```
group by function \
  const date = task.due.moment; \
  const tomorrow = moment().add(1,'days'); \
  const now = moment(); \
  const label = (order, name) => `%%${order}%% ==${name}==`; \
  if (!date)              return label(5, 'Undated'); \
  if (!date.isValid())         return label(0, 'Invalid date'); \
  if (date.isBefore(now, 'day'))    return label(1, 'Overdue'); \
  if (date.isSame(now, 'day'))     return label(2, 'Today'); \
  if (date.isSame(tomorrow, 'day'))  return label(3, 'Tomorrow'); \
  return label(4, 'Future');

```

  * As above, but adds a heading for Tomorrow.


!Tasks grouped by due date category, and then by due date
Sample image showing tasks grouped first by highlighted words `Overdue`, `Today`, `Future` and `Undated`, and then by individual due date.
### Done Date 
  * `group by done`
    * The done date of the task, including the week-day, or `Invalid done date` or `No done date`.


Released
  * `done` grouping option was introduced in Tasks 1.7.0.


Since Tasks 4.0.0, **custom grouping by done date** is now possible.
```
group by function task.done.format("YYYY-MM-DD dddd")

```

  * Like "group by done", except it uses an empty string instead of "No done date" if there is no done date.


For more examples, see Due Date.
### Scheduled Date 
  * `group by scheduled`
    * The scheduled date of the task, including the week-day, or `Invalid scheduled date` or `No scheduled date`.


Released
  * `scheduled` grouping option was introduced in Tasks 1.7.0.


Since Tasks 4.0.0, **custom grouping by scheduled date** is now possible.
```
group by function task.scheduled.format("YYYY-MM-DD dddd")

```

  * Like "group by scheduled", except it uses an empty string instead of "No scheduled date" if there is no scheduled date.


For more examples, see Due Date.
### Start Date 
  * `group by start`
    * The start date of the task, including the week-day, or `Invalid start date` or `No start date`.


Released
  * `start` grouping option was introduced in Tasks 1.7.0.


Since Tasks 4.0.0, **custom grouping by start date** is now possible.
```
group by function task.start.format("YYYY-MM-DD dddd")

```

  * Like "group by start", except it uses an empty string instead of "No start date" if there is no start date.


For more examples, see Due Date.
### Created Date 
  * `group by created`
    * The created date of the task, including the week-day, or `Invalid created date` or `No created date`.


Released
`created` grouping option was introduced in Tasks 2.0.0.
Since Tasks 4.0.0, **custom grouping by created date** is now possible.
```
group by function task.created.format("YYYY-MM-DD dddd")

```

  * Like "group by created", except it uses an empty string instead of "No created date" if there is no created date.


For more examples, see Due Date.
### Cancelled Date 
  * `group by cancelled`
    * The cancelled date of the task, including the week-day, or `Invalid cancelled date` or `No cancelled date`.


Released
`cancelled` grouping option was introduced in Tasks 5.5.0.
Since Tasks 5.5.0, **custom grouping by cancelled date** is now possible, using `task.cancelled`.
```
group by function task.cancelled.format("YYYY-MM-DD dddd")

```

  * Like "group by cancelled", except it uses an empty string instead of "No cancelled date" if there is no cancelled date.


For more examples, see Due Date.
### Happens 
  * `group by happens`
    * The earliest of start date, scheduled date, and due date, including the week-day, or `No happens date` if none of those are set.


Released
`happens` grouping option was introduced in Tasks 1.11.0.
Since Tasks 4.0.0, **custom grouping by happens date** is now possible.
```
group by function task.happens.format("YYYY-MM-DD dddd")

```

  * Like "group by happens", except it uses an empty string instead of "No happens date" if there is no happens date.


For more examples, see Due Date.
## Group by Other Task Properties 
As well as the date-related groups above, groups can be created from properties in individual tasks.
### Description 
There is no built-in instruction to group by description.
Since Tasks 4.0.0, **custom grouping by description** is now possible.
```
group by function task.description

```

  * group by description.
  * This might be useful for finding completed recurrences of the same task.


```
group by function task.description.toUpperCase()

```

  * Convert the description to capitals.


```
group by function task.description.slice(0, 25)

```

  * Truncate descriptions to at most their first 25 characters, and group by that string.


```
group by function task.description.replace('short', '==short==')

```

  * Highlight the word "short" in any group descriptions.


### Description without tags 
Since Tasks 4.2.0, it is possible to remove tags from the descriptions in custom groups, for use in **custom grouping**.
The value `task.descriptionWithoutTags` returns a copy of the description with all the tags removed, so that you can group together any tasks whose descriptions differ only by their tags.
```
group by function task.descriptionWithoutTags

```

  * Like `group by description`, but it removes any tags from the group headings.
  * This might be useful for finding completed recurrences of the same task, even if the tags differ in some recurrences.


### Priority 
  * `group by priority`
    * The priority of the task, namely one of: 
      * `Highest priority`
      * `High priority`
      * `Medium priority`
      * `Normal priority`
      * `Low priority`
      * `Lowest priority`


Released
  * `priority` grouping option was introduced in Tasks 1.11.0.


Since Tasks 4.0.0, **custom grouping by priority name and number** is now possible.
`task.priorityNameGroupText` was added in Tasks 4.9.0.
Using the priority name:
```
group by function task.priorityName

```

  * Group by the task's priority name.
  * The priority names are displayed in alphabetical order.
  * Note that the default priority is called 'Normal', as opposed to with `group by priority` which calls the default 'None'.


```
group by function task.priorityNameGroupText

```

  * Group by the task's priority name.
  * The priority names are displayed from highest to lowest priority.
  * Note that the default priority is called 'Normal', as opposed to with `group by priority` which calls the default 'None'.


Using the priority number:
```
group by function task.priorityNumber

```

  * Group by the task's priority number, where Highest is 0 and Lowest is 5.


### Urgency 
  * `group by urgency` (urgency) 
    * The groups run from the highest urgency to the lowest.
    * You can reverse this with `group by urgency reverse`.


Released
  * `urgency` grouping option was introduced in Tasks 3.6.0.
  * In Tasks 4.0.0 the order of `group by urgency` was reversed, to put most urgent tasks first. Add or remove the word `reverse` to get the original order.


Since Tasks 4.0.0, **custom grouping by urgency** is now possible.
```
group by function task.urgency.toFixed(3)

```

  * Show the urgency to 3 decimal places, unlike the built-in "group by urgency" which uses 2.


```
group by function task.urgency

```

  * Show non-integer urgency values to 5 decimal places, and integer ones to 0 decimal places.
  * Sorting of groups by name has been found to be unreliable with varying numbers of decimal places.
  * So to ensure consistent sorting, Tasks will round non-integer numbers to a fixed 5 decimal places, returning the value as a string.
  * This still sorts consistently even when some of the group's values are integers.


### Recurrence 
  * `group by recurring`
    * Whether the task is recurring: either `Recurring` or `Not Recurring`.
  * `group by recurrence`
    * The recurrence rule of the task, for example `every week on Sunday`, or `None` for non-recurring tasks.
    * Note that the text displayed is generated programmatically and standardised, and so may not exactly match the text in any manually typed tasks. For example, a task with `🔁 every Sunday` is grouped in `every week on Sunday`.


Released
  * `recurring` and `recurrence` grouping options were introduced in Tasks 1.11.0.


Since Tasks 4.0.0, **custom grouping by recurrence** is now possible.
```
group by function task.isRecurring ? "Recurring" : "Non-Recurring"

```

  * Use JavaScript's ternary operator to choose what to do for true (after the ?) and false (after the :) values.


```
group by function task.recurrenceRule.replace('when done', '==when done==')

```

  * Group by recurrence rule, highlighting any occurrences of the words "when done".


### Tags 
See Tags for important information about how tags behave in the Tasks plugin.
  * `group by tags`
    * The tags of the tasks or `(No tags)`. If the task has multiple tags, it will show up under every tag.


Released
  * `tags` grouping option was introduced in Tasks 1.10.0.


Since Tasks 4.0.0, **custom grouping by tags** is now possible.
```
group by function task.tags

```

  * Like "group by tags" except that tasks with no tags have no heading instead of "(No tags)".


```
group by function task.tags.join(", ")

```

  * Tasks with multiple tags are listed once, with a heading that combines all the tags.
  * Separating with commas means the tags are clickable in the headings.


```
group by function task.tags.sort().join(", ")

```

  * As above, but sorting the tags first ensures that the final headings are independent of order of tags in the tasks.


```
group by function task.tags.filter( (tag) => tag.includes("#context/") )

```

  * Only create headings for tags that contain "#context/".


```
group by function task.tags.filter( (tag) => ! tag.includes("#tag") )

```

  * Create headings for all tags that do not contain "#tag".


These are more complicated examples, which you might like to copy if you use tasks with nested tags and wish to group them at different tag nesting levels.
```
group by function task.tags.map( (tag) => tag.split('/')[0].replace('#', '') )

```

  * `#tag/subtag/sub-sub-tag` gives **`tag`**.


```
group by function task.tags.map( (tag) => tag.split('/')[1] ? tag.split('/').slice(1, 2) : '')

```

  * `#tag/subtag/sub-sub-tag` gives **`subtag`**.


```
group by function task.tags.map( (tag) => tag.split('/')[2] ? tag.split('/').slice(2, 3) : '')

```

  * `#tag/subtag/sub-sub-tag` gives **`sub-sub-tag`**.


```
group by function task.tags.map( (tag) => tag.split('/')[3] ? tag.split('/').slice(3, 4) : '')

```

  * `#tag/subtag/sub-sub-tag` gives no heading, as there is no value at the 4th level.


```
group by function task.tags.map( (tag) => tag.split('/')[0] )

```

  * `#tag/subtag/sub-sub-tag` gives **`#tag`**.


```
group by function task.tags.map( (tag) => tag.split('/')[1] ? tag.split('/').slice(0, 2).join('/') : '')

```

  * `#tag/subtag/sub-sub-tag` gives **`#tag/subtag`**.


```
group by function task.tags.map( (tag) => tag.split('/')[2] ? tag.split('/').slice(0, 3).join('/') : '')

```

  * `#tag/subtag/sub-sub-tag` gives **`#tag/subtag/sub-sub-tag`**.


```
group by function task.tags.map( (tag) => tag.split('/')[3] ? tag.split('/').slice(0, 4).join('/') : '')

```

  * `#tag/subtag/sub-sub-tag` gives no heading, as there is no value at the 4th level.


### Original Markdown 
There is no built-in instruction to group by the original markdown line.
Since Tasks 4.0.0, **custom grouping by original markdown line** is now possible.
For example, this could be used to extract information from `task.originalMarkdown` that Tasks does not parse, to use for grouping tasks.
```
group by function '``' + task.originalMarkdown + '``'

```

  * Group by the raw text of the task's original line in the MarkDown file as code.
  * Note the pairs of backtick characters ('`'), to preserve even single backtick characters in the task line.
  * It's important to prevent the task checkbox (for example, '[ ]') from being rendered in the heading, as it gets very confusing if there are checkboxes on both headings and tasks.


```
group by function task.originalMarkdown.replace(/^[^\[\]]+\[.\] */, '')

```

  * An alternative to formatting the markdown line as code is to remove everything up to the end of the checkbox.
  * Then render the rest of the task line as normal markdown.


### Line Number 
There is no built-in instruction to group by the task's line number.
Since Tasks 7.16.0, **custom grouping by the task's line number** is now possible, using `task.lineNumber`.
Tip
With `task.lineNumber`, the first line in the file is on line number `0` (zero), not `1` (one).
## Group by File Properties 
### File Path 
  * `group by path` (the path to the file that contains the task, that is, the folder and the filename)


Since Tasks 4.0.0, **custom grouping by file path** is now possible.
```
group by function task.file.path

```

  * Like 'group by path' but includes the file extension, and does not escape any Markdown formatting characters in the path.


```
group by function task.file.path.replace(query.file.folder, '')

```

  * Group by the task's file path, but remove the query's folder from the group.
  * For tasks in the query's folder or a sub-folder, this is a nice way of seeing shortened paths.
  * This is provided to give ideas: it's a bit of a lazy implementation, as it doesn't check that `query.file.folder` is at the start of the line.


Since Tasks 5.1.0, the query's file path can be used conveniently in custom groups.
  * `query.file.path` or
  * `query.file.pathWithoutExtension`
  * Useful reading: Query Properties.


### Root 
  * `group by root` (the top-level folder of the file that contains the task, that is, the first directory in the path, which will be `/` for files in root of the vault)


Released
`root` grouping option was introduced in Tasks 1.11.0.
Since Tasks 4.0.0, **custom grouping by root folder** is now possible.
```
group by function task.file.root

```

  * Like 'group by root' except that it does not escape any Markdown formatting characters in the root.


Since Tasks 5.1.0, the query's file root can be used conveniently in custom groups.
  * `query.file.root`
  * Useful reading: Query Properties.


### Folder 
  * `group by folder` (the folder to the file that contains the task, which always ends in `/` and will be exactly `/` for files in root of the vault)


Since Tasks 4.0.0, **custom grouping by folder** is now possible.
```
group by function task.file.folder

```

  * Like 'group by folder', except that it does not escape any Markdown formatting characters in the folder.


```
group by function task.file.folder.slice(0, -1).split('/').pop() + '/'

```

  * Group by the immediate parent folder of the file containing task.
  * Here's how it works: 
    * '.slice(0, -1)' removes the trailing slash ('/') from the original folder.
    * '.split('/')' divides the remaining path up in to an array of folder names.
    * '.pop()' returns the last folder name, that is, the parent of the file containing the task.
    * Then the trailing slash is added back, to ensure we do not get an empty string for files in the top level of the vault.


Since Tasks 5.1.0, the query's folder can be used conveniently in custom groups.
  * `query.file.folder`
  * Useful reading: Query Properties.


### File Name 
  * `group by filename` (the link to the file that contains the task, without the `.md` extension) 
    * Note that tasks from different notes with the same file name will be grouped together in the same group.


Since Tasks 4.0.0, **custom grouping by file name** is now possible.
```
group by function task.file.filename

```

  * Like 'group by filename' but does not link to the file.


```
group by function task.file.filenameWithoutExtension + (task.hasHeading ? (' > ' + task.heading) : '')

```

  * Like 'group by backlink' but does not link to the heading in the file.


Since Tasks 5.1.0, the query's file name can be used conveniently in custom groups.
  * `query.file.filename` or
  * `query.file.filenameWithoutExtension`
  * Useful reading: Query Properties.


### Backlink 
  * `group by backlink` (the text that would be shown in the task's backlink, combining the task's file name and heading, with a link)


### Heading 
  * `group by heading` (the heading preceding the task, or `(No heading)` if there are no headings in the file)


Since Tasks 4.0.0, **custom grouping by heading** is now possible.
Grouping


================================================================================

## 58. https://publish.obsidian.md/tasks/Reference/Status+Collections/Things+Theme


```

# Regular Expressions 
## Introduction 
Released
Introduced in Tasks 1.12.0.
Regular expression ("regex") searches are a powerful alternative to the simple `includes` and `does not include` searches.
### Take Care 
Warning
Regular expression (or 'regex') searching is a powerful but advanced feature that requires thorough knowledge in order to use successfully, and not miss intended search results.
It is easy to write a regular expression that looks like it is correct, but which uses a special character that completely changes the meaning of the search string.
For example, `\d` does **not** match the **two** characters `\d`, it matches any **one** of the following characters: `0123456789`.
This documentation gives only a brief overview of the facility, with a few motivating examples, and then links to other resources, for thorough treatment.
Regular Expressions


================================================================================

## 60. https://publish.obsidian.md/tasks/Queries/Line+Continuations


```

# Tasks Emoji Format 
#task-formats #task-format/tasks
These samples demonstrate all the fields supported by the Tasks plugin's parsing of its own emoji signifiers.
## Tasks Emoji Format for Dates 
```
- [ ] #task Has a created date ➕ 2023-04-13
- [ ] #task Has a scheduled date ⏳ 2023-04-14
- [ ] #task Has a start date 🛫 2023-04-15
- [ ] #task Has a due date 📅 2023-04-16
- [x] #task Has a done date ✅ 2023-04-17
- [-] #task Has a cancelled date ❌ 2023-04-18

```

For more information, see Dates.
Tasks Emoji Format


================================================================================

## 62. https://publish.obsidian.md/tasks/Reference/Status+Collections/LYT+Mode+Theme

- [ ] #task `space` Unchecked
- [x] #task `x` Checked
- [>] #task `>` Rescheduled
- [<] #task `<` Scheduled
- [!] #task `!` Important
- [-] #task `-` Cancelled
- [/] #task `/` In Progress
- [?] #task `?` Question
- [*] #task `*` Star
- [n] #task `n` Note
- [l] #task `l` Location
- [i] #task `i` Information
- [I] #task `I` Idea
- [S] #task `S` Amount
- [p] #task `p` Pro
- [c] #task `c` Con
- [b] #task `b` Bookmark
- [f] #task `f` Fire
- [k] #task `k` Key
- [w] #task `w` Win
- [u] #task `u` Up
- [d] #task `d` Down

```

## Tasks' one-click addition 
Tasks' setting pane has a one-click button to add the following information, representing the custom checkboxes in this plugin.
Status Symbol | Next Status Symbol | Status Name`status.name includes...``sort by status.name``group by status.name` | Status Type`status.type is...``sort by status.type``group by status.type` | Needs Custom Styling  
---|---|---|---|---  
`space` | `x` | Unchecked | `TODO` | No  
`x` | `space` | Checked | `DONE` | No  
`>` | `x` | Rescheduled | `TODO` | Yes  
`<` | `x` | Scheduled | `TODO` | Yes  
`!` | `x` | Important | `TODO` | Yes  
`-` | `space` | Cancelled | `CANCELLED` | Yes  
`/` | `x` | In Progress | `IN_PROGRESS` | Yes  
`?` | `x` | Question | `TODO` | Yes  
`*` | `x` | Star | `TODO` | Yes  
`n` | `x` | Note | `TODO` | Yes  
`l` | `x` | Location | `TODO` | Yes  
`i` | `x` | Information | `TODO` | Yes  
`I` | `x` | Idea | `TODO` | Yes  
`S` | `x` | Amount | `TODO` | Yes  
`p` | `x` | Pro | `TODO` | Yes  
`c` | `x` | Con | `TODO` | Yes  
`b` | `x` | Bookmark | `TODO` | Yes  
`f` | `x` | Fire | `TODO` | Yes  
`k` | `x` | Key | `TODO` | Yes  
`w` | `x` | Win | `TODO` | Yes  
`u` | `x` | Up | `TODO` | Yes  
`d` | `x` | Down | `TODO` | Yes  

================================================================================

## 63. https://publish.obsidian.md/tasks/Reference/Status+Collections/SlRvb's+Alternate+Checkboxes


```

# SlRvb's Alternate Checkboxes 
## Introduction 
This theme offers the same checkboxes as ITS Theme, but will work with other themes too, so is more flexible.
Location | Link  
---|---  
GitHub: |   
Obsidian Hub: | Alternate Checkboxes)  
Test note in Tasks-Demo vault: | Snippet - SlRvb's Alternate Checkboxes  
## Screenshot 
!Sample tasks show in Reading mode, with the SlRvb's Alternate Checkboxes Snippet
## Supported statuses 
```
- [ ] #task `space` Unchecked
- [x] #task `x` Regular
- [X] #task `X` Checked
- [-] #task `-` Dropped
- [>] #task `>` Forward
- [D] #task `D` Date
- [?] #task `?` Question
- [/] #task `/` Half Done
- [+] #task `+` Add
- [R] #task `R` Research
- [!] #task `!` Important
- [i] #task `i` Idea
- [B] #task `B` Brainstorm
- [P] #task `P` Pro
- [C] #task `C` Con
- [Q] #task `Q` Quote
- [N] #task `N` Note
- [b] #task `b` Bookmark
- [I] #task `I` Information
- [p] #task `p` Paraphrase
- [L] #task `L` Location
- [E] #task `E` Example
- [A] #task `A` Answer
- [r] #task `r` Reward
- [c] #task `c` Choice
- [d] #task `d` Doing
- [T] #task `T` Time
- [@] #task `@` Character / Person
- [t] #task `t` Talk
- [O] #task `O` Outline / Plot
- [~] #task `~` Conflict
- [W] #task `W` World
- [f] #task `f` Clue / Find
- [F] #task `F` Foreshadow
- [H] #task `H` Favorite / Health
- [&] #task `&` Symbolism
- [s] #task `s` Secret

```

## Tasks' one-click addition 
Tasks' setting pane has a one-click button to add the following information, representing the custom checkboxes in this plugin.
Status Symbol | Next Status Symbol | Status Name`status.name includes...``sort by status.name``group by status.name` | Status Type`status.type is...``sort by status.type``group by status.type` | Needs Custom Styling  
---|---|---|---|---  
`space` | `x` | Unchecked | `TODO` | No  
`x` | `space` | Regular | `DONE` | No  
`X` | `space` | Checked | `DONE` | Yes  
`-` | `space` | Dropped | `CANCELLED` | Yes  
`>` | `x` | Forward | `TODO` | Yes  
`D` | `x` | Date | `TODO` | Yes  
`?` | `x` | Question | `TODO` | Yes  
`/` | `x` | Half Done | `IN_PROGRESS` | Yes  
`+` | `x` | Add | `TODO` | Yes  
`R` | `x` | Research | `TODO` | Yes  
`!` | `x` | Important | `TODO` | Yes  
`i` | `x` | Idea | `TODO` | Yes  
`B` | `x` | Brainstorm | `TODO` | Yes  
`P` | `x` | Pro | `TODO` | Yes  
`C` | `x` | Con | `TODO` | Yes  
`Q` | `x` | Quote | `TODO` | Yes  
`N` | `x` | Note | `TODO` | Yes  
`b` | `x` | Bookmark | `TODO` | Yes  
`I` | `x` | Information | `TODO` | Yes  
`p` | `x` | Paraphrase | `TODO` | Yes  
`L` | `x` | Location | `TODO` | Yes  
`E` | `x` | Example | `TODO` | Yes  
`A` | `x` | Answer | `TODO` | Yes  
`r` | `x` | Reward | `TODO` | Yes  
`c` | `x` | Choice | `TODO` | Yes  
`d` | `x` | Doing | `IN_PROGRESS` | Yes  
`T` | `x` | Time | `TODO` | Yes  
`@` | `x` | Character / Person | `TODO` | Yes  
`t` | `x` | Talk | `TODO` | Yes  
`O` | `x` | Outline / Plot | `TODO` | Yes  
`~` | `x` | Conflict | `TODO` | Yes  
`W` | `x` | World | `TODO` | Yes  
`f` | `x` | Clue / Find | `TODO` | Yes  
`F` | `x` | Foreshadow | `TODO` | Yes  
`H` | `x` | Favorite / Health | `TODO` | Yes  
`&` | `x` | Symbolism | `TODO` | Yes  
`s` | `x` | Secret | `TODO` | Yes  
SlRvb's Alternate Checkboxes


================================================================================

## 64. https://publish.obsidian.md/tasks/Queries/Layout


```

# Layout commands 
## Hiding/Showing Elements 
You can hide and show individual elements of the rendered list with the "hide" and "show" commands together with the name of the element.
Released
The `show` commands were introduced in Tasks 1.14.0.
## Task Elements 
The following task elements exist:
  * `id`
  * `depends on`
  * `priority`
  * `cancelled date`
  * `created date`
  * `start date`
  * `scheduled date`
  * `due date`
  * `done date`
  * `recurrence rule`
  * `on completion`
  * `tags`


All of these task elements are shown by default, so you will use the command `hide` if you do not want to show any of them.
Layout


================================================================================

## 65. https://publish.obsidian.md/tasks/Reference/Status+Collections/ITS+Theme


```

# ITS Theme 
## Introduction 
This theme offers the same checkboxes as SlRvb's Alternate Checkboxes, which works in combination with other themes too, so is more flexible.
Location | Link  
---|---  
GitHub: |   
Obsidian Hub: | ITS Theme  
Test note in Tasks-Demo vault: | Theme - ITS Theme  
## Screenshot 
!Sample tasks show in Reading mode, with the ITS Theme
## Supported statuses 
```
- [ ] #task `space` Unchecked
- [x] #task `x` Regular
- [X] #task `X` Checked
- [-] #task `-` Dropped
- [>] #task `>` Forward
- [D] #task `D` Date
- [?] #task `?` Question
- [/] #task `/` Half Done
- [+] #task `+` Add
- [R] #task `R` Research
- [!] #task `!` Important
- [i] #task `i` Idea
- [B] #task `B` Brainstorm
- [P] #task `P` Pro
- [C] #task `C` Con
- [Q] #task `Q` Quote
- [N] #task `N` Note
- [b] #task `b` Bookmark
- [I] #task `I` Information
- [p] #task `p` Paraphrase
- [L] #task `L` Location
- [E] #task `E` Example
- [A] #task `A` Answer
- [r] #task `r` Reward
- [c] #task `c` Choice
- [d] #task `d` Doing
- [T] #task `T` Time
- [@] #task `@` Character / Person
- [t] #task `t` Talk
- [O] #task `O` Outline / Plot
- [~] #task `~` Conflict
- [W] #task `W` World
- [f] #task `f` Clue / Find
- [F] #task `F` Foreshadow
- [H] #task `H` Favorite / Health
- [&] #task `&` Symbolism
- [s] #task `s` Secret

```

ITS Theme


================================================================================

## 66. https://publish.obsidian.md/tasks/Reference/Status+Collections/AnuPpuccin+Theme


```

# AnuPpuccin Theme 
## Introduction 
Location | Link  
---|---  
GitHub: |   
Obsidian Hub: | AnuPpuccin Theme  
Test note in Tasks-Demo vault: | Theme - AnuPpuccin  
## Screenshot 
!Sample tasks show in Reading mode, with the AnuPpuccin Theme
## Supported statuses 
```
- [ ] #task `space` Unchecked
- [x] #task `x` Checked
- [>] #task `>` Rescheduled
- [<] #task `<` Scheduled
- [!] #task `!` Important
- [-] #task `-` Cancelled
- [/] #task `/` In Progress
- [?] #task `?` Question
- [*] #task `*` Star
- [n] #task `n` Note
- [l] #task `l` Location
- [i] #task `i` Information
- [I] #task `I` Idea
- [S] #task `S` Amount
- [p] #task `p` Pro
- [c] #task `c` Con
- [b] #task `b` Bookmark
- ["] #task `"` Quote
- [0] #task `0` Speech bubble 0
- [1] #task `1` Speech bubble 1
- [2] #task `2` Speech bubble 2
- [3] #task `3` Speech bubble 3
- [4] #task `4` Speech bubble 4
- [5] #task `5` Speech bubble 5
- [6] #task `6` Speech bubble 6
- [7] #task `7` Speech bubble 7
- [8] #task `8` Speech bubble 8
- [9] #task `9` Speech bubble 9

```

## Tasks' one-click addition 
Tasks' setting pane has a one-click button to add the following information, representing the custom checkboxes in this plugin.
Status Symbol | Next Status Symbol | Status Name`status.name includes...``sort by status.name``group by status.name` | Status Type`status.type is...``sort by status.type``group by status.type` | Needs Custom Styling  
---|---|---|---|---  
`space` | `x` | Unchecked | `TODO` | No  
`x` | `space` | Checked | `DONE` | No  
`>` | `x` | Rescheduled | `TODO` | Yes  
`<` | `x` | Scheduled | `TODO` | Yes  
`!` | `x` | Important | `TODO` | Yes  
`-` | `space` | Cancelled | `CANCELLED` | Yes  
`/` | `x` | In Progress | `IN_PROGRESS` | Yes  
`?` | `x` | Question | `TODO` | Yes  
`*` | `x` | Star | `TODO` | Yes  
`n` | `x` | Note | `TODO` | Yes  
`l` | `x` | Location | `TODO` | Yes  
`i` | `x` | Information | `TODO` | Yes  
`I` | `x` | Idea | `TODO` | Yes  
`S` | `x` | Amount | `TODO` | Yes  
`p` | `x` | Pro | `TODO` | Yes  
`c` | `x` | Con | `TODO` | Yes  
`b` | `x` | Bookmark | `TODO` | Yes  
`"` | `x` | Quote | `TODO` | Yes  
`0` | `0` | Speech bubble 0 | `NON_TASK` | Yes  
`1` | `1` | Speech bubble 1 | `NON_TASK` | Yes  
`2` | `2` | Speech bubble 2 | `NON_TASK` | Yes  
`3` | `3` | Speech bubble 3 | `NON_TASK` | Yes  
`4` | `4` | Speech bubble 4 | `NON_TASK` | Yes  
`5` | `5` | Speech bubble 5 | `NON_TASK` | Yes  
`6` | `6` | Speech bubble 6 | `NON_TASK` | Yes  
`7` | `7` | Speech bubble 7 | `NON_TASK` | Yes  
`8` | `8` | Speech bubble 8 | `NON_TASK` | Yes  
`9` | `9` | Speech bubble 9 | `NON_TASK` | Yes  

================================================================================

## 67. https://publish.obsidian.md/tasks/Queries/Sorting


```

# Sorting 
#feature/sorting
## Contents 
This page is long. Here are some links to the main sections:
  * Default sort order
  * Custom Sorting
  * Sort by Task Statuses
  * Sort by Task Dependencies
  * Sort by Dates in Tasks
  * Sort by Other Task Properties
  * Sort by File Properties
  * Multiple sort criteria
  * Notes
  * Reverse sorting
  * Examples


## Default sort order 
The following instructions are the default sort order, and they are **automatically appended to the end of _every_ Tasks search**:
Sorting


================================================================================

## 68. https://publish.obsidian.md/tasks/Queries/Global+Query


```

# Global Query 
## Summary 
Released
The Global Query setting was added in Tasks 3.5.0.
Global Query is a powerful and flexible alternative to the Global Filter.
You can set a global query in the settings that Tasks will add to the start of all the Queries in your vault.
Example
With a global query set to `path includes /tasks`, the following task block:
```
```tasks
tags include work
```

```

will run as if it were:
```
```tasks
path includes /tasks
tags include work
```

```

## Ignoring the global query 
If you need to ignore the Global Query in a given Tasks block you may add `ignore global query` instruction to any place of the block.
For example, this allows you to have your task searches ignore certain folders by default. And then in a few searches, you can enable searching for tasks in those folders.
Global Query


================================================================================

## 69. https://publish.obsidian.md/tasks/Reference/Status+Collections/Aura+Theme


```

# Aura Theme 
## Introduction 
Location | Link  
---|---  
GitHub: |   
Obsidian Hub: | Aura Theme  
Test note in Tasks-Demo vault: | Theme - Aura Theme  
Notes: |   
## Screenshot 
!Sample tasks show in Reading mode, with the Aura Theme
## Supported statuses 
```
- [ ] #task `space` incomplete
- [x] #task `x` complete / done
- [-] #task `-` cancelled
- [>] #task `>` deferred
- [/] #task `/` in progress, or half-done
- [!] #task `!` Important
- [?] #task `?` question
- [R] #task `R` review
- [+] #task `+` Inbox / task that should be processed later
- [b] #task `b` bookmark
- [B] #task `B` brainstorm
- [D] #task `D` deferred or scheduled
- [I] #task `I` Info
- [i] #task `i` idea
- [N] #task `N` note
- [Q] #task `Q` quote
- [W] #task `W` win / success / reward
- [P] #task `P` pro
- [C] #task `C` con

```

## Tasks' one-click addition 
Tasks' setting pane has a one-click button to add the following information, representing the custom checkboxes in this plugin.
Status Symbol | Next Status Symbol | Status Name`status.name includes...``sort by status.name``group by status.name` | Status Type`status.type is...``sort by status.type``group by status.type` | Needs Custom Styling  
---|---|---|---|---  
`space` | `x` | incomplete | `TODO` | No  
`x` | `space` | complete / done | `DONE` | No  
`-` | `space` | cancelled | `CANCELLED` | Yes  
`>` | `x` | deferred | `TODO` | Yes  
`/` | `x` | in progress, or half-done | `IN_PROGRESS` | Yes  
`!` | `x` | Important | `TODO` | Yes  
`?` | `x` | question | `TODO` | Yes  
`R` | `x` | review | `TODO` | Yes  
`+` | `x` | Inbox / task that should be processed later | `TODO` | Yes  
`b` | `x` | bookmark | `TODO` | Yes  
`B` | `x` | brainstorm | `TODO` | Yes  
`D` | `x` | deferred or scheduled | `TODO` | Yes  
`I` | `x` | Info | `TODO` | Yes  
`i` | `x` | idea | `TODO` | Yes  
`N` | `x` | note | `TODO` | Yes  
`Q` | `x` | quote | `TODO` | Yes  
`W` | `x` | win / success / reward | `TODO` | Yes  
`P` | `x` | pro | `TODO` | Yes  
`C` | `x` | con | `TODO` | Yes  

================================================================================

## 70. https://publish.obsidian.md/tasks/Reference/Status+Collections/Border+Theme


```

# Border Theme 
## Introduction 
Location | Link  
---|---  
GitHub: |   
Obsidian Hub: | Border Theme  
Test note in Tasks-Demo vault: | Theme - Border Theme  
Notes: |   
## Screenshot 
!Sample tasks show in Reading mode, with the Border Theme
## Supported statuses 
```
- [ ] #task `space` To Do
- [/] #task `/` In Progress
- [x] #task `x` Done
- [-] #task `-` Cancelled
- [>] #task `>` Rescheduled
- [<] #task `<` Scheduled
- [!] #task `!` Important
- [?] #task `?` Question
- [i] #task `i` Infomation
- [S] #task `S` Amount
- [*] #task `*` Star
- [b] #task `b` Bookmark
- [“] #task `“` Quote
- [n] #task `n` Note
- [l] #task `l` Location
- [I] #task `I` Idea
- [p] #task `p` Pro
- [c] #task `c` Con
- [u] #task `u` Up
- [d] #task `d` Down

```

Border Theme


================================================================================

## 71. https://publish.obsidian.md/tasks/Queries/Limiting


```

# Limiting 
## Limit total number of tasks 
You can limit the total number of tasks to show as query results.
Use the query string `limit to <number> tasks`. This will only list the first `<number>` results of the query (after sorting).
Shorthand is `limit <number>`.
## Limit number of tasks in each group 
You can also limit the allowed number of tasks in each group, if grouping is used. Otherwise this limit is ignored.
Use the query string `limit groups to <number> tasks`. This will only list the first `<number>` tasks in each group from the results of the query.
Shorthand is `limit groups <number>`.
Limiting


================================================================================

## 72. https://publish.obsidian.md/tasks/Reference/Status+Collections/Ebullientworks+Theme


```

# Ebullientworks Theme 
## Introduction 
Location | Link  
---|---  
GitHub: |   
Obsidian Hub: | Ebullientworks Theme  
Test note in Tasks-Demo vault: | Theme - Ebullientworks  
## Screenshot 
!Sample tasks show in Reading mode, with the Ebullientworks Theme
## Supported statuses 
```
- [ ] #task `space` Unchecked
- [x] #task `x` Checked
- [-] #task `-` Cancelled
- [/] #task `/` In Progress
- [>] #task `>` Deferred
- [!] #task `!` Important
- [?] #task `?` Question
- [r] #task `r` Review

```

Ebullientworks Theme


================================================================================

## 73. https://publish.obsidian.md/tasks/Queries/Query+File+Defaults


```

# Query File Defaults 
Released
Introduced in Tasks 7.15.0.
## Benefits 
This is a somewhat specialised facility that enables you to:
  1. **Modifylayout options in a Tasks Query without editing the `tasks` code block source.**
     * This could save you switching repeatedly between Reading and Editing modes.
     * Perhaps you usually like to see your Tasks search results with certain Layout options, but sometimes it is nice to see more detail, perhaps turning `show tree` on and off, depending on your mood.
  2. **Automatically insert one or more instructions in to all the`tasks` code blocks in a file.**
     * You have multiple Tasks queries in a Markdown file, and they have a lot of text in common.
     * You would like to avoid repeating those common instructions in each one, because keeping them consistent is tedious and error-prone.
  3. **Remind yourself what all`tasks` code blocks in a file do.**
     * Quickly turn explain on and off, for when you need a reminder, or are wondering why some tasks are not included in a search.


## Summary 
**Query File Defaults** are like the Global Query only more specific:
  * The Global Query: 
    * applies to **all queries in the vault** ,
    * is defined in the **Tasks Settings**.
  * Query File Defaults: 
    * apply to **all queries in a file** ,
    * is defined in **one or more standardnamed properties at the start of the file**.


Structure of this page:
  * This page uses examples to demonstrate the mechanism.
  * It then shows how to easily adjust a file's Query File Defaults using the Obsidian-native user interface and a Meta Bind user interface.
  * Finally, it gives technical details and records limitations.


## Examples 
These examples are provided to demonstrate how Query File Defaults work, so that all the supported values (listed below) should make sense.
### Add extra instructions 
Any number of Tasks instructions can be inserted at the start of all queries in a file, using the `TQ_extra_instructions` property:
```
---
TQ_extra_instructions: |-
 not done
 group by filename
---

```

When editing `TQ_extra_instructions` in Obsidian's File properties editor, you can press `<Shift> + <Return>` to insert a new line.
Tip
  * `TQ_extra_instructions` is especially useful when you have more than one Tasks search block in a file, and you want the same instructions to be present in all the searches.
  * Before this feature, if those standard instructions changed, you had to remember to update every search.
  * Now you can put those standard instructions in `TQ_extra_instructions`, and only update them in one place.


Note
The `TQ_extra_instructions` property isn't an array. It's a single string value, and the `|-` allows it to span multiple lines.
### Short or full mode 
Suppose the file containing our query begins with the following:
```
---
TQ_short_mode: true
---

```

Any Tasks code blocks in that file will then have this content inserted at the start:
```
short mode

```

All possible behaviours of `TQ_short_mode`:
`TQ_short_mode` value | Generated instruction  
---|---  
`true` | `short mode`  
`false` | `full mode`  
_no value_ | _no instruction_  
### Show or hide tree 
Suppose the file containing our query begins with the following:
```
---
TQ_show_tree: true
---

```

Any Tasks code blocks in that file will then have this content inserted at the start:
```
show tree

```

All possible behaviours of `TQ_show_tree`:
`TQ_show_tree` value | Generated instruction  
---|---  
`true` | `show tree`  
`false` | `hide tree`  
_no value_ | _no instruction_  
## Applying instructions to every Tasks search in a file 
### Obsidian-native User Interface 
You can use the Obsidian **File properties** view to customise Tasks searches:
!Obsidian's 'File properties' widget, with checkboxes and a text box to modify query file defaults for a file containing Tasks searches. Obsidian's **File properties** widget, with checkboxes and a text box to modify query file defaults for a file containing Tasks searches. See Widening property names in Obsidian for the CSS snippet used to widen property names.
To try this out:
  1. Show the `File properties` panel: 
     * Enable the Obsidian core Properties view plugin: `Settings` > `Core plugins` > turn on `Properties view`
     * Switch to Reading or Live Preview modes.
     * Run the `Properties view: Show file properties` command.
  2. Add one or more `TQ_*` properties to the file 
     * Click on `Add property`.
     * Start typing `TQ_`, or any part of the property names list in Supported Query File Defaults property values below.
     * Press `<Return>` or `<Enter>` to add the property.
  3. Now you can modify these `TQ_*` properties to change the behaviour of all the Tasks searches in this file.


Tip
Use the command **Tasks: Add all Query File Defaults properties** to add all the available `TQ_*` properties to the active note in one simple step.
#### Widening property names in Obsidian 
By default, the property names are very narrow in Obsidian.
You can make them wider with the following CSS Snippet.
```
/* Make property labels wider, to fit the names of Tasks-specific properties */
.metadata-content {
  --metadata-label-width: 14em;
}

```

The Obsidian user guide shows how to use CSS snippets in Obsidian.
### Meta Bind User Interface 
See Make a query user interface for how to use Query File Defaults with the Meta Bind Plugin to create a User Interface to easily customise many aspects of your Tasks searches:
!Meta Bind widgets to edit Query File Defaults Meta Bind widgets to edit Query File Defaults
## Technical details 
### Supported Query File Defaults property values 
These are all the properties currently supported by Tasks, as Query File Defaults.
```
---
TQ_explain:
TQ_extra_instructions:
TQ_short_mode:
TQ_show_backlink:
TQ_show_cancelled_date:
TQ_show_created_date:
TQ_show_depends_on:
TQ_show_done_date:
TQ_show_due_date:
TQ_show_edit_button:
TQ_show_id:
TQ_show_on_completion:
TQ_show_postpone_button:
TQ_show_priority:
TQ_show_recurrence_rule:
TQ_show_scheduled_date:
TQ_show_start_date:
TQ_show_tags:
TQ_show_task_count:
TQ_show_tree:
TQ_show_urgency:
---

```

### Command: Add all Query File Defaults properties 
Tip
Use the command **Tasks: Add all Query File Defaults properties** to add all these properties to the active note.
### Types of Query File Defaults property values 
These are all the types of properties currently supported by Tasks, as Query File Defaults.
The `type` values are explained in the Property types section of Obsidian Help.
Tip
The Tasks plugin automatically adds these properties to the Obsidian vault.
```
{
 "types": {
  "TQ_explain": "checkbox",
  "TQ_extra_instructions": "text",
  "TQ_short_mode": "checkbox",
  "TQ_show_backlink": "checkbox",
  "TQ_show_cancelled_date": "checkbox",
  "TQ_show_created_date": "checkbox",
  "TQ_show_depends_on": "checkbox",
  "TQ_show_done_date": "checkbox",
  "TQ_show_due_date": "checkbox",
  "TQ_show_edit_button": "checkbox",
  "TQ_show_id": "checkbox",
  "TQ_show_on_completion": "checkbox",
  "TQ_show_postpone_button": "checkbox",
  "TQ_show_priority": "checkbox",
  "TQ_show_recurrence_rule": "checkbox",
  "TQ_show_scheduled_date": "checkbox",
  "TQ_show_start_date": "checkbox",
  "TQ_show_tags": "checkbox",
  "TQ_show_task_count": "checkbox",
  "TQ_show_tree": "checkbox",
  "TQ_show_urgency": "checkbox"
 }
}

```

## Limitations of Query File Defaults 
  * Tasks searches in **Canvas cards** cannot use Query File Defaults, because the Canvas format does not support frontmatter/properties. 
    * The workaround is to use the Canvas Convert to file facility to convert cards which contain Tasks queries to a separate Markdown note, embedded in the canvas.
    * You can then add Query File Defaults to the new note.
  * The property `TQ_extra_instructions` can contain any kind of Tasks instruction, including placeholders. 
    * But it does not work with Line Continuations.
    * The workaround is to write any long instructions all on one line when placed in `TQ_extra_instructions`.



================================================================================

## 74. https://publish.obsidian.md/tasks/Reference/Status+Collections/Minimal+Theme


```

# Minimal Theme 
## Introduction 
Location | Link  
---|---  
GitHub: |   
Obsidian Hub: | Minimal Theme  
Test note in Tasks-Demo vault: | Theme - Minimal Theme  
## Screenshot 
!Sample tasks show in Reading mode, with the Minimal Theme
## Supported statuses 
```
- [ ] #task `space` to-do
- [/] #task `/` incomplete
- [x] #task `x` done
- [-] #task `-` canceled
- [>] #task `>` forwarded
- [<] #task `<` scheduling
- [?] #task `?` question
- [!] #task `!` important
- [*] #task `*` star
- ["] #task `"` quote
- [l] #task `l` location
- [b] #task `b` bookmark
- [i] #task `i` information
- [S] #task `S` savings
- [I] #task `I` idea
- [p] #task `p` pros
- [c] #task `c` cons
- [f] #task `f` fire
- [k] #task `k` key
- [w] #task `w` win
- [u] #task `u` up
- [d] #task `d` down

```

## Tasks' one-click addition 
Tasks' setting pane has a one-click button to add the following information, representing the custom checkboxes in this plugin.
Status Symbol | Next Status Symbol | Status Name`status.name includes...``sort by status.name``group by status.name` | Status Type`status.type is...``sort by status.type``group by status.type` | Needs Custom Styling  
---|---|---|---|---  
`space` | `x` | to-do | `TODO` | No  
`/` | `x` | incomplete | `IN_PROGRESS` | Yes  
`x` | `space` | done | `DONE` | No  
`-` | `space` | canceled | `CANCELLED` | Yes  
`>` | `x` | forwarded | `TODO` | Yes  
`<` | `x` | scheduling | `TODO` | Yes  
`?` | `x` | question | `TODO` | Yes  
`!` | `x` | important | `TODO` | Yes  
`*` | `x` | star | `TODO` | Yes  
`"` | `x` | quote | `TODO` | Yes  
`l` | `x` | location | `TODO` | Yes  
`b` | `x` | bookmark | `TODO` | Yes  
`i` | `x` | information | `TODO` | Yes  
`S` | `x` | savings | `TODO` | Yes  
`I` | `x` | idea | `TODO` | Yes  
`p` | `x` | pros | `TODO` | Yes  
`c` | `x` | cons | `TODO` | Yes  
`f` | `x` | fire | `TODO` | Yes  
`k` | `x` | key | `TODO` | Yes  
`w` | `x` | win | `TODO` | Yes  
`u` | `x` | up | `TODO` | Yes  
`d` | `x` | down | `TODO` | Yes  

================================================================================

## 75. https://publish.obsidian.md/tasks/Scripting/Custom+Grouping


```

# Task Properties 
#feature/scripting
Released
Task Properties were introduced in Tasks 4.0.0.
## Introduction 
In a growing number of locations, Tasks allows programmatic/scripting access to values in your Tasks:
  * Grouping > Custom Groups
  * Sorting > Custom Sorting
  * Filters > Custom Filters


This page documents all the available pieces of information in Tasks that you can access.
## Values for Task Statuses 
For more information, including adding your own customised statuses, see Statuses.
Field | Type 1 | Example 1 | Type 2 | Example 2  
---|---|---|---|---  
`task.isDone` | `boolean` | `false` | `boolean` | `false`  
`task.status.name` | `string` | `'Todo'` | `string` | `'In Progress'`  
`task.status.type` | `string` | `'TODO'` | `string` | `'IN_PROGRESS'`  
`task.status.typeGroupText` | `string` | `'%%2%%TODO'` [[1]](https://publish.obsidian.md/tasks/Scripting/Task+Properties#fn-1-03124d0146aa703c) | `string` | `'%%1%%IN_PROGRESS'` [[1-1]](https://publish.obsidian.md/tasks/Scripting/Task+Properties#fn-1-03124d0146aa703c)  
`task.status.symbol` | `string` | `' '` | `string` | `'/'`  
`task.status.nextSymbol` | `string` | `'x'` | `string` | `'x'`  
  1. `task.status.typeGroupText` (added in Tasks 4.9.0) is a convenient way to sort status types in to a natural order in custom grouping functions.


## Values for Dates in Tasks 
Field | Type 1 | Example 1 | Type 2 | Example 2  
---|---|---|---|---  
`task.created` | `TasksDate` | `2023-07-01 00:00` | `TasksDate` | ``  
`task.start` | `TasksDate` | `2023-07-02 00:00` | `TasksDate` | ``  
`task.scheduled` | `TasksDate` | `2023-07-03 00:00` | `TasksDate` | ``  
`task.due` | `TasksDate` | `2023-07-04 00:00` | `TasksDate` | ``  
`task.cancelled` | `TasksDate` | `2023-07-06 00:00` | `TasksDate` | ``  
`task.done` | `TasksDate` | `2023-07-05 00:00` | `TasksDate` | ``  
`task.happens` | `TasksDate` | `2023-07-02 00:00` | `TasksDate` | ``  
  1. Each of these values is a `TasksDate` object. The Values in TasksDate Properties section below shows what can be done with them.
  2. Note that currently all stored dates have no time, or rather, their time is midnight at the start of the day, local time.
  3. For example uses of date properties, see Filters > Due Date and Grouping > Due Date.
  4. `task.happens` is the earlier of `task.due`, `task.scheduled` and `task.start`.
  5. `task.cancelled` was added in Tasks 5.5.0.


## Values in TasksDate Properties 
Field | Type 1 | Example 1 | Type 2 | Example 2  
---|---|---|---|---  
`task.due` | `TasksDate` | `2023-07-04 00:00` | `TasksDate` | ``  
`task.due.moment` | `Moment` | `moment('2023-07-04 00:00')` | `null` | `null`  
`task.due.formatAsDate()` | `string` | `'2023-07-04'` | `string` | `''`  
`task.due.formatAsDate('no date')` | `string` | `'2023-07-04'` | `string` | `'no date'`  
`task.due.formatAsDateAndTime()` | `string` | `'2023-07-04 00:00'` | `string` | `''`  
`task.due.formatAsDateAndTime('no date')` | `string` | `'2023-07-04 00:00'` | `string` | `'no date'`  
`task.due.format('dddd')` | `string` | `'Tuesday'` | `string` | `''`  
`task.due.format('dddd', 'no date')` | `string` | `'Tuesday'` | `string` | `'no date'`  
`task.due.toISOString()` | `string` | `'2023-07-04T00:00:00.000Z'` | `string` | `''`  
`task.due.toISOString(true)` | `string` | `'2023-07-04T00:00:00.000+00:00'` | `string` | `''`  
`task.due.category.name` | `string` | `'Future'` | `string` | `'Undated'`  
`task.due.category.sortOrder` | `number` | `3` | `number` | `4`  
`task.due.category.groupText` | `string` | `'%%3%% Future'` [[1-2]](https://publish.obsidian.md/tasks/Scripting/Task+Properties#fn-1-03124d0146aa703c) | `string` | `'%%4%% Undated'` [[1-3]](https://publish.obsidian.md/tasks/Scripting/Task+Properties#fn-1-03124d0146aa703c)  
`task.due.fromNow.name` | `string` | `'in 22 days'` | `string` | `''`  
`task.due.fromNow.sortOrder` | `number` | `320230704` | `number` | `0`  
`task.due.fromNow.groupText` | `string` | `'%%320230704%% in 22 days'` [[1-4]](https://publish.obsidian.md/tasks/Scripting/Task+Properties#fn-1-03124d0146aa703c) | `string` | `''`  
  1. These examples refer to `task.due`, but they can be used on any of the date properties show in the section Values for Dates in Tasks above.
  2. The `TasksDate` formatting methods use the moment.js format characters.
  3. The `TasksDate` formatting methods all take an optional `fallBackText` string value, which is the value to use when there is no date. The `fallBackText` value can be any of: 
     * a fixed string, such as `'no date'`,
     * an expression, such as `task.priorityName` or `task.priorityNameGroupText`,
     * an empty string `''` or `""`, meaning 'do not add a heading for tasks missing this date property'.
  4. You can see the current TasksDate source code, to explore its implementation.
  5. `task.due.toISOString(true)` prevents UTC conversion - see the moment documentation
  6. `category` divides dates in to 5 named groups: 
     * `Invalid date`
     * `Overdue`
     * `Today`
     * `Future`
     * `Undated`
     * And they are numbered 0, 1, 2, 3 and 4, in the order listed above.
  7. `fromNow` groups dates by the time from now, for example: 
     * `2 months ago`
     * `8 days ago`
     * `in 11 hours`
     * `in 5 days`
     * `in 3 months`
     * `in a year`
  8. The `category` properties were added in Tasks 4.9.0. 
     * The `Invalid date` category was added in Tasks 6.0.0.
  9. The `fromNow` properties were added in Tasks 4.9.0.


## Values for Task Dependencies 
Field | Type 1 | Example 1 | Type 2 | Example 2  
---|---|---|---|---  
`task.id` | `string` | `'abcdef'` | `string` | `''`  
`task.dependsOn` | `string[]` | `['123456', 'abc123']` | `any[]` | `[]`  
`task.isBlocked(query.allTasks)` | `boolean` | `false` | `boolean` | `false`  
`task.isBlocking(query.allTasks)` | `boolean` | `false` | `boolean` | `false`  
  1. See the page Task Dependencies, which explains the dependencies facility.
  2. `Task.isBlocked()` behaves the same as `is blocked`: see Filters > Blocked Tasks.
  3. `Task.isBlocking()` behaves the same as `is blocking`: see Filters > Blocking Tasks.
  4. Task Dependencies were released in Tasks 6.1.0.


## Values for Other Task Properties 
Field | Type 1 | Example 1 | Type 2 | Example 2  
---|---|---|---|---  
`task.description` | `string` | `'Do exercises #todo #health'` | `string` | `'minimal task'`  
`task.descriptionWithoutTags` | `string` | `'Do exercises'` | `string` | `'minimal task'`  
`task.priorityNumber` | `number` | `2` | `number` | `3`  
`task.priorityName` | `string` | `'Medium'` | `string` | `'Normal'`  
`task.priorityNameGroupText` | `string` | `'%%2%%Medium priority'` [[1-5]](https://publish.obsidian.md/tasks/Scripting/Task+Properties#fn-1-03124d0146aa703c) | `string` | `'%%3%%Normal priority'` [[1-6]](https://publish.obsidian.md/tasks/Scripting/Task+Properties#fn-1-03124d0146aa703c)  
`task.urgency` | `number` | `3.3000000000000007` | `number` | `1.9500000000000002`  
`task.isRecurring` | `boolean` | `true` | `boolean` | `false`  
`task.recurrenceRule` | `string` | `'every day when done'` | `string` | `''`  
`task.onCompletion` | `string` | `'delete'` | `string` | `''`  
`task.tags` | `string[]` | `['#todo', '#health']` | `any[]` | `[]`  
`task.originalMarkdown` | `string` | `' - [ ] Do exercises #todo #health 🆔 abcdef ⛔ 123456,abc123 🔼 🔁 every day when done 🏁 delete ➕ 2023-07-01 🛫 2023-07-02 ⏳ 2023-07-03 📅 2023-07-04 ❌ 2023-07-06 ✅ 2023-07-05 ^dcf64c'` | `string` | `'- [/] minimal task'`  
`task.lineNumber` | `number` | `17` | `number` | `0`  
  1. `task.description` has spaces at the start and end stripped off.
  2. `task.description` includes any tags.
  3. `task.priorityName` and `task.priorityNumber` values are: 
     * 'Highest': 0
     * 'High': 1
     * 'Medium': 2
     * 'Normal': 3
     * 'Low': 4
     * 'Lowest': 5
  4. `task.priorityNameGroupText` (added in Tasks 4.9.0) is a convenient way to sort priority names in to a natural order in custom grouping functions.
  5. `task.isRecurring` is: 
     * `true` if the Task has a **valid** recurrence rule,
     * `false` if: 
       * **either** it does not have a recurrence rule
       * **or** the recurrence rule is invalid (such as `🔁 every seven weeks`, for example).
  6. `task.recurrenceRule` is: 
     * **either** the standardised text of the recurrence rule if the Task has a **valid** recurrence rule 
       * An example might be `every 7 weeks`.
       * Note that this text is generated programmatically and standardised, and so may not exactly match the text in any manually typed tasks.
       * For example, a task with `🔁 every Sunday` will have a `task.recurrenceRule` value of `every week on Sunday`.
     * **or** an empty string (`''`) if: 
       * **either** it does not have a recurrence rule,
       * **or** the recurrence rule is invalid (such as `🔁 every seven weeks`, for example).
  7. `task.onCompletion` (added in Tasks 7.8.0) will have one of these values: 
     * `delete`
     * `keep`
     * `` (empty string), which is the default, when the task has no On Completion action specified.
  8. Note that if there is a Global Filter enabled in settings, and the filter is a tag, it will be removed from `task.tags`.


## Values for File Properties 
Field | Type 1 | Example 1 | Type 2 | Example 2  
---|---|---|---|---  
`task.file.path` | `string` | `'some/folder/fileName.md'` | `string` | `''`  
`task.file.pathWithoutExtension` | `string` | `'some/folder/fileName'` | `string` | `''`  
`task.file.root` | `string` | `'some/'` | `string` | `'/'`  
`task.file.folder` | `string` | `'some/folder/'` | `string` | `'/'`  
`task.file.filename` | `string` | `'fileName.md'` | `string` | `''`  
`task.file.filenameWithoutExtension` | `string` | `'fileName'` | `string` | `''`  
`task.hasHeading` | `boolean` | `true` | `boolean` | `false`  
`task.heading` | `string` | `'My Header'` | `null` | `null`  
  1. `task.file` is a `TasksFile` object.
  2. You can see the current TasksFile source code, to explore its capabilities.
  3. The presence of `.md` filename extensions is chosen to match the existing conventions in the Tasks filter instructions path and filename.
  4. `task.file.pathWithoutExtension` was added in Tasks 4.8.0.
  5. `task.file.filenameWithoutExtension` was added in Tasks 4.8.0.


## Values for Obsidian Properties 
Released
Access to the Obsidian Properties was introduced in Tasks 7.7.0.
These are described in full in Obsidian Properties.
Field | Type 1 | Example 1  
---|---|---  
`task.file.hasProperty('creation date')` | `boolean` | `true`  
`task.file.property('creation date')` | `string` | `'2024-05-25T15:17:00'`  
`task.file.property('sample_checkbox_property')` | `boolean` | `true`  
`task.file.property('sample_date_property')` | `string` | `'2024-07-21'`  
`task.file.property('sample_date_and_time_property')` | `string` | `'2024-07-21T12:37:00'`  
`task.file.property('sample_list_property')` | `string[]` | `['Sample', 'List', 'Value']`  
`task.file.property('sample_number_property')` | `number` | `246`  
`task.file.property('sample_text_property')` | `string` | `'Sample Text Value'`  
`task.file.property('sample_text_multiline_property')` | `string` | `'Sample\nText\nValue\n'`  
`task.file.property('sample_link_property')` | `string` | `'[[yaml_all_property_types_populated]]'`  
`task.file.property('sample_link_list_property')` | `string[]` | `['[[yaml_all_property_types_populated]]', '[[yaml_all_property_types_empty]]']`  
`task.file.property('tags')` | `string[]` | `['#tag-from-file-properties']`  
  1. `task.file.hasProperty()` and `task.file.property()` were added in Tasks 7.7.0
  2. `task.file.hasProperty('property name')` returns true if the property `'property name'` is both present in the file and has a non-`null` value.
  3. `task.file.property('property name')` returns either the value in the file, or `null` if there is no value.


  1. Text inside `%% ... %%` comments is hidden from view. It is used to control the order that group headings are sorted in.↩︎↩︎↩︎↩︎↩︎↩︎↩︎



================================================================================

## 77. https://publish.obsidian.md/tasks/Other+Plugins/Meta+Bind+Plugin


```

# How to make a query user interface 
#plugin/meta-bind
## Meta Bind Tasks User Interface to Query File Defaults 
Released
Query File Defaults were introduced in Tasks 7.15.0.
The Meta Bind Plugin allows Obsidian users to make their notes interactive with inline input fields, metadata displays, and buttons.
We can combine:
  1. The Tasks plugin's Query File Defaults facility, based on specific properties named `TQ_*`,
  2. The Meta Bind plugin's ability to create widgets to modify note properties.


... to create a User Interface to easily adjust your Tasks searches, that can:
  * show and hide each of the task properties,
  * enable or disable other search features, such as nested tasks, short mode, backlink and buttons,
  * and allow arbitrary extra instructions to be added:


Make a query user interface


================================================================================

## 79. https://publish.obsidian.md/tasks/Support+and+Help/Known+Limitations


```

# Query Properties 
#feature/scripting
Released
  * Query Properties were introduced in Tasks 4.7.0.
  * Their direct use in Custom Filters and Custom Groups, without the use of Placeholders, was introduced in Tasks 5.1.0.


## Introduction 
In a growing number of locations, Tasks allows programmatic/scripting access to properties of the file containing the search query:
  * Placeholders
  * Custom Filters
  * Custom Sorting
  * Custom Grouping


This page documents all the available pieces of information in Queries that you can access.
## Values for Query File Properties 
Query Properties


================================================================================


---

## 📊 Resumo da Extração

- **Total de páginas**: 80
- **Estratégia**: BFS
- **Data**: 28/05/2025 21:35:52
- **Gerado por**: Crawl4AI - Madrev Edition
