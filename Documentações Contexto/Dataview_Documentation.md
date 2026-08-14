# Documentação Extraída - blacksmithgu.github.io

**URL Original**: https://blacksmithgu.github.io/obsidian-dataview/
**Data de Extração**: 28/05/2025 16:52:09
**Tipo de Extração**: Deep Crawl
**Estratégia**: BFS
**Máx. Páginas**: 50
**Profundidade**: 4
**Filtro de Domínio**: https://blacksmithgu.github.io
**Extraído com**: Crawl4AI - Madrev Edition

---


## 2. Https: >  > Blacksmithgu.Github.Io > Obsidian Dataview

# Overview
Dataview is a live index and query engine over your personal knowledge base. You can **add metadata** to your notes and **query** them with the **Dataview Query Language** to list, filter, sort or group your data. Dataview keeps your queries always up to date and makes data aggregation a breeze.
You could
  * Track your sleep by recording it in daily notes, and automatically create weekly tables of your sleep schedule.
  * Automatically collect links to books in your notes, and render them all sorted by rating.
  * Automatically collect pages associated with today's date and show them in your daily note.
  * Find pages with no tags for follow-up, or show pretty views of specifically-tagged pages.
  * Create dynamic views which show upcoming birthdays or events recorded in your notes


and many more things.
Dataview gives you a fast way to search, display and operate on indexed data in your vault!
Dataview is highly generic and high performance, scaling up to hundreds of thousands of annotated notes without issue. 
If the built in query language is insufficient for your purpose, you can run arbitrary JavaScript against the dataview API and build whatever utility you might need yourself, right in your notes.
Dataview is about displaying, not editing
Dataview is meant for displaying and calculating data. It is not meant to edit your notes/metadata and will always leave them untouched (... except if you're checking a Task through Dataview.)
## How to Use Dataview
Dataview consists of two big building blocks: **Data Indexing** and **Data Querying**. 
More details on the linked documentation pages
The following sections should give you a general overview about what you can do with dataview and how. Be sure to visit the linked pages to find out more about the individual parts.
### Data Indexing
Dataview operates on metadata in your Markdown files. It cannot read everything in your vault, but only specific data. Some of your content, like tags and bullet points (including tasks), are available automatically in Dataview. You can add other data through **fields** , either on top of your file per YAML Frontmatter or in the middle of your content with Inline Fields via the `[key:: value]` syntax. Dataview _indexes_ these data to make it available for you to query. 
Dataview indexes certain information like tags and list items and the data you add via fields. Only indexed data is available in a Dataview query!
For example, a file might look like this:
```
---
author: "Edgar Allan Poe"
published: 1845
tags: poems
---
# The Raven
Once upon a midnight dreary, while I pondered, weak and weary,
Over many a quaint and curious volume of forgotten lore—

```

Or like this:
```
#poems
# The Raven
From [author:: Edgar Allan Poe], written in (published:: 1845)
Once upon a midnight dreary, while I pondered, weak and weary,
Over many a quaint and curious volume of forgotten lore—

```

In terms of indexed metadata (or what you can query), they are identical, and only differ in their annotation style. How you want to annotate your metadata is up to you and your personal preference. With this file, you'd have the **metadata field** `author` available and everything Dataview provides you automatically as implicit fields, like the tag or note title. 
Data needs to be indexed
In the above example, you _do not_ have the poem itself available in Dataview: It is a paragraph, not a metadata field and not something Dataview indexes automatically. It is not part of Dataviews index, so you won't be able to query it.
### Data Querying
You can access **indexed data** with the help of **Queries**.
There are **three different ways** you can write a Query: With help of the Dataview Query Language, as an inline statement or in the most flexible but most complex way: as a Javascript Query. 
The **Dataview Query Language** (**DQL**) gives you a broad and powerful toolbelt to query, display and operate on your data. An **inline query** gives you the possibility to display exactly one indexed value anywhere in your note. You can also do calculations this way. With **DQL** at your hands, you'll be probably fine without any Javascript through your data journey.
A DQL Query consists of several parts:
  * Exactly one **Query Type** that determines what your Query Output looks like
  * None or one **FROM statement** to pick a specific tag or folder (or another source) to look at
  * None to multiple **other Data Commands** that help you filter, group and sort your wanted output


For example, a Query can look like this:
```
```dataview
LIST
```

```

which list all files in your vault. 
Everything but the Query Type is optional
The only thing you need for a valid DQL Query is the Query Type (and on CALENDARs, a date field.)
A more restricted Query might look like this:
```
```dataview
LIST
FROM #poems
WHERE author = "Edgar Allan Poe"
```

```

which lists all files in your vault that have the tag `#poems` and a field named `author` with the value `Edgar Allan Poe`. This query would find our example page from above. 
`LIST` is only one out of four Query Types you can use. For example, with a `TABLE`, we could add some more information to our output: 
```
```dataview
TABLE author, published, file.inlinks AS "Mentions"
FROM #poems
```

```

This'll give you back a result like:
File (3) | author | published | Mentions  
---|---|---|---  
The Bells | Edgar Allan Poe | 1849 |   
The New Colossus | Emma Lazarus | 1883 | - [[Favorite Poems]]  
The Raven | Edgar Allan Poe | 1845 | - [[Favorite Poems]]  
That's not where the capabilities of dataview end, though. You can also **operate on your data** with help of **functions**. Mind that these operations are only made inside your query - your **data in your files stays untouched**.
```
```dataview
TABLE author, date(now).year - published AS "Age in Yrs", length(file.inlinks) AS "Counts of Mentions"
FROM #poems
```

```

gives you back
File (3) | author | Age in Yrs | Count of Mentions  
---|---|---|---  
The Bells | Edgar Allan Poe | 173 | 0  
The New Colossus | Emma Lazarus | 139 | 1  
The Raven | Edgar Allan Poe | 177 | 1  
Find more examples here.
As you can see, dataview doesn't only allow you to aggregate your data swiftly and always up to date, it also can help you with operations to give you new insights on your dataset. Browse through the documentation to find out more on how to interact with your data.
Have fun exploring your vault in new ways! 
## Resources and Help
This documentation is not the only place that can help you out on your data journey. Take a look at Resources and Support for a list of helpful pages and videos.



================================================================================

## 3. Changelog




# 0.5.68
  * Many fixes to the documentation
  * # 2318 & co: Various fixes related to _live preview_ rendering of lists
  * New/documented functions for `unique()`, `display()`, `firstvalue()`
  * Added DOM information related to standalone inline fields


This is the first release done by @holroy, so thanks to him for further developing of _Dataview_. Thank you also to all the people having contributed through PRs and issues.
# 0.5.67
Includes several documentation fixes and several community-contributed bug fixes.
  * @reply2za: Fixed inline rendering in the reading view.
  * @carlesalbasboix: Adds sum(), avg(), min(), and max() to data arrays.
  * @mnaoumov: Adds code mirror configuration which code highlights dataviewjs!


# 0.5.66
Bugfix for version comparisons to fix some other plugins having broken interactions with Dataview.
# 0.5.65
A maintenance update which fixes some issues with rendering embeds in Dataviews and adds a few new functions.
  * Adds the `hash()` function for generating consistent uniformly-distributed values given arbitrary inputs. Primarily useful for creating "random" views which remain consistent across page refreshes. Thanks to @holroy.
  * Adds the `slice()` function for slicing arrays, similar to Javascript's `Array.slice`. Thanks to @holroy.
  * Fixes several issues with rendering embeds inside dataviews. Thanks to @GottZ.
  * Several documentation improvements around tasks - thanks to @holroy and @RaviOnline.


# 0.5.64
More bug fixes for inline field rendering.
# 0.5.63
  * More bugfixes from @RyotaUshio for rendering Markdown paragraphs and other blocks in DataviewJS.


# 0.5.62
Several more inline field fixes from @RyotaUshio, including more configuration options, fixing inline fields being rendered inside codeblocks, and more. Thanks!
# 0.5.61
  * @RyotaUshio: Fix several bugs related to the new inline field rendering, including source mode and fixing date formatting.


# 0.5.60
  * @RyotaUshio: Add explicit rendering of inline fields in live preview. They are much more visually distinct now!
  * @MarioRicalde: Adds `PluginApi#evaluateInline(expression, path)` to the plugin API, which evaluate expressions as if you were on the given page.


# 0.5.59
  * Fix an issue with the plugin failing to run on iOS due to an esoteric regex issue.


# 0.5.58
  * Negative durations will now be properly rendered.


# 0.5.57
Maintenance patch which bumps many internal dependency versions and which includes approximately ~20 community-contributed PRs which add some new functions, fix some Dataview interactions with properties, and more!
# Unreleased
  * DQL: Adds new `durationformat(duration, string)` function.
  * DQL: New math rounding functions, `trunc(number)`, `floor(number)`, `ceil(number)`.


# 0.5.56
  * Includes some performance fixes on recent versions of Obsidian 1.3+ due to some API changes. Thanks @kometenstaub.
  * Documentation cleanups and improvements by @mocsa, @protofarer, @seanlzx, and @somidad.
  * Adds the new `flat(array)` method for flattening nested arrays, as well as parsing dates using arbitrary formats using `date(text, "format")`. Thanks @holroy!


# 0.5.55
  * Durations are now internationalized using luxon's new internationalization support.
  * Dataviews should now properly render inside Canvas and some other contexts. Thanks @GamerGirlandCo!


# 0.5.54
  * Regular list items are now also clickable in task views, not just task lines! Thanks to @LilaRest.


# 0.5.53
  * Fix some documentation issues causing docs to not be updated.


# 0.5.52
Substantial documentation improvements thanks to @s-blu and @AB1908!
  * For people concerned about dataviewjs code execution from copy-pasting, @eyuelt has made it possible to change the dataviewjs codeblock prefix.
  * @sohanglal has added some documentation for `task.visual` for changing the visual text of a task.
  * @Chouffy and @Daryl-Horton have fixed some bad documentation links!
  * @vrtmrz swapped the regex used for parsing tags to better match Obsidian's own parser.
  * @alexfertel has added `regextest`, which allows for matching parts of a string instead of the whole thing.
  * @iamrecursion has added more metadata to file links, so they now include section metadata. This may cause some slight visual changes in link views.


# 0.5.51 (Beta)
  * Allow disabling regular Dataview inline queries via configuration option.


# 0.5.50 (Beta)
  * Expose dataview EXPRESSION and QUERY parsing to the dataview npm plugin, so others can parse dataview ASTs.
  * Fix documentation issue with `join`.


# 0.5.49 (Beta)
  * Add the `average` function to compute averages of lists (`average([list of things])`).
  * Added documentation for `average`, `min`, `max`, `minby`, and `maxby` functions.
  * Fixed the broken `nonnull` function and documented it.


# 0.5.48 (Beta)
We're back to more regular beta releases while I trial out new functionality!
  * Fixed broken list behavior for `dv.markdownTaskList`.
  * @GamerGirlandCo: Better handling of block IDs when checking off tasks!
  * @s-blu and @AB1908: Lots of big documentation upgrades! Nice!
  * @leoccyao: More block ID task checking fixes. Should work after this one.
  * Add expression/query parsing to the dataview NPM package.
  * @charleshan: Fix a missing header level in the dataview `dv.header` example.


# 0.5.47
Improves `date + duration` behavior when either the date or duration are null.
# 0.5.46
  * Fix #1412: Fix bad `file.cday` and `file.ctime` comparisons due to wrong timezone being set. Ugh.


# 0.5.45
  * # 1400: Properly use the group by field for the group name.
  * Fix bad table highlighting in some themes.


# 0.5.44
  * # 1404: Fixed dates in non-local timezones parsing incorrectly.
  * Fixed some build non-determinism issues.
  * Swapped to pull requests for adding new functionality, and added some more internal tests.


# 0.5.43
  * Fix #1366: Better handling of calendar emoji (used as due dates in tasks).


# 0.5.42
It's been over a month since the last release! Anyway, this release bundles several nice user-contributed features:
  * @AB1908: Tag queries are now case insensitive.
  * @AB1908: Shift-clicking a link/task to open in a new tab now works properly on Mac.
  * @AB1908: Numerous documentation fixes for clarity and more examples.
  * @AnnaKornfeldSimpson: Additional emoji shorthands for more task fields (finished, due).
  * @ooker777: Documentation improvements for some DataviewJS functions, and the ability to use inline emoji for the completion tracking feature.
  * @mt-krainski: Custom date formats for task completions.
  * @gentlegiantJGC: Better support for nested inline fields (i.e., less crashy).


# 0.5.41
  * Fix a bad regex doing escaping in markdown tables.
  * Improve async documentation.


# 0.5.40
Adds some more documentation about the new markdown functionality.
# 0.5.39
  * Fixed an issue where checking a task in a task view would check the wrong box visually.
  * Added experimental plugin APIs for querying dataview directly as markdown, and converting dataview results to properly formatted markdown.


# 0.5.38
  * Some minor documentation improvements.
  * Fix an issue with inline fields rendering out of order. That was a weird bug.


# 0.5.37
Fixes inline field rendering to once again work for highlighting/links, as well as some other rendering quirks with inline queries in codeblocks.
# 0.5.36
  * Fix a bug when checking if an element is an HTMLElement.
  * Properly include the nice improvements to the file count in tables and lists.


# 0.5.35
  * Fix #1196, #1176: Re-enable HTML values. This was never a featured I advertised since it was just for some internal hackery, but it appears people just discovered it in DataviewJS queries.
  * Improved initial time to popular queries that use `file.starred`.


# 0.5.34
  * Fix #1174: Fix indexing with a variable.
  * Fix an issue with the experimental calendar view.


# 0.5.33
  * Fix a bug with inline views that was introduced in 0.5.32.


# 0.5.32
The Dataview API has been noticeably revamped - there are now approximately twice as many functions available on the plugin API as there were before, and some additional utilities have been added to both the plugin and inline API. I will be finishing up the associated new "extension" functionality shortly, which will allow:
  1. For custom Dataview + DataviewJS functions to be added via plugins.
  2. For custom renderable objects (progress bars, embedded task lists, embedded tables) to be added to any Dataview view via plugins.
  3. For plugins to provide alternative behavior for some dataview functionality (such as integrating task plugins with the dataview task query).


As part of the API revamp, it is now possible to programmatically execute Dataview and DataviewJS queries - either for using the existing Dataview query language in your own plugin, or for embedding dataview. The Dataview npm library also now exposes many useful internal Dataview types, including the AST structure for all dataview queries.
I am hoping that cleaning up the Dataview API and making it much more extensible will allow for Dataview to integrate much better with existing plugins, and to provide the full power of the in-memory index for plugins. I have been very carefully watching index performance in recent weeks to ensure smooth frontend performance for anyone using the API (with a goal of <10ms for most queries).
# 0.5.31
Tasks now have an `outlinks` list field which includes all links in the task; this can be used for finding tasks with links in them.
# 0.5.30
  * Added the `typeof(any)` function in Dataview, which obtains the type of any value for comparison: 
```
typeof("text")="string"
typeof(1)="number"
typeof([1,2,3])="array"

```

  * Added the modulo operator (`%`) for doing integer division remainder. I.e., `14 % 2 = 0` and `14 % 3 = 2`.
  * Fixed some minor spacing issues with lists in tables.


# 0.5.29
Fix another subtle incompatibility between 0.4.26 and 0.5.29 - if you frequently used empty inline fields (like `Key::` with no value), the 0.5+ behavior is now the same as 0.4 behavior and will map such fields to null instead of an empty string.
This may fix a broad variety of "subtly wrong" queries that you may have seen after the upgrade.
# 0.5.28
  * Fix a bug with some more string concatenations and null handling.


# 0.5.27
More performance + correctness bugfixes.
  * The parser has been made a little more robust to prevent major indexing issues (or at least recover from them quickly).
  * Several new strange tag variants are now supported.
  * Markdown links are now properly indexed again.


Some DataviewJS performance issues should be resolved now, especially for external plugins using Dataview. This fix does involve a slight API break w.r.t. what types are wrapped into Dataview Arrays (which provide functions like `.where()`). Generally, only Dataview-provided implicits are wrapped in data arrays now; frontmatter and inline fields are always now regular JS arrays - use `dv.array()` to explicitly make a data array if you want the advanced querying.
# 0.5.26
More small bugfixes:
  * Fix a few small link rendering issues.
  * Tag extraction from tasks now handles punctuation properly.
  * Upgrade luxon (which is embedded in DataviewJS) to 2.4.0.


# 0.5.25
  * Fix #1147: Fix there being a `#null` tag for files with an empty `tag` or `tags` frontmatter.


# 0.5.24
Several bugfixes:
  * Nulls are now sorted first rather than last; it's generally good practice to explicitly check for nulls in your queries to avoid strange behavior.
  * Dataview now properly parses space-delimited tags (like `tags: abc def ghi`).
  * Dataview now supports dropping the entire file cache in case of bugs.


# 0.5.23
  * Fix #1140: Force API objects to be arrays if they are iterables.


# 0.5.22
  * Fix #1135: Use 'x' instead of 'X' for checkboxes.


# 0.5.21
A long-overdue swap from the beta branch to the stable branch. The beta branch should not include any (intended) breaking changes, and has some nice performance improvements that come along with it! Here are the major changes:
  * Most views now use React and no longer flicker when updating; this is not the case yet for DataviewJS, which will be getting equivalent treatment in the future.
  * Dataview now caches metadata, so Dataview loads are very fast after the first time you open your vault. Dataview still needs to visit every file when you update the plugin version, so that should be the only times you experience slower load times.
  * A brand new task view backend and query which allows you to filter per-task, rather than per-page! Check the documentation for details, but this broadly means `WHERE` statements now use task properties instead of page properties.
  * Some additional metadata is now available for use - `file.starred`, `file.lists`, and more metadata in `file.tasks`.


There have been some moderate documentation touch-ups to keep things up to date; I'm still working on a walkthrough for common Dataview use cases. This review also includes about ~30-40 bugfixes; some new bugs may arise due to internal changes, so please flag them if you encounter them.
# 0.5.20 (Beta)
Slight fix to hopefully improve some strange reported cases of bad indexing at startup.
# 0.5.19 (Beta)
Dataview now uses IndexedDB to cache file metadata, reducing startup time to virtually nothing if you've opened the vault before; if you have a small vault (<1000 notes), you may notice a slight improvement, but large vaults and mobile devices will notice a very significant performance improvement to "first valid paint". Some other performance parameters have been tuned to hopefully make the default experience better.
A few small bugs related to rendering have also been squashed, including an issue with images being scaled wrongly.
# 0.5.18 (Beta)
  * Tasks in task views now support alternative task status characters like '!' and '/'; thanks @ebullient.
  * A few documentation nit fixes.
  * Added `DataArray#sortInPlace` for a more efficient mutable sort for niche use cases.


# 0.5.17 (Beta)
  * Improved behavior when clicking on tasks in the task view; will now properly scroll to the relevant line in long files!
  * Fixed a bug with incorrect counts being displayed in task views.
  * Added `tags` as a field available on task items, so you can now do things like `TASK WHERE contains(tags, "#tag")`.


# 0.5.16 (Beta)
Dataview now tracks initialization and will report when all files have been indexed in the console; you can programmatically see this via `dataview:index-ready`, or by checking `api.index.initialized`.
# 0.5.15 (Beta)
  * Add hover highlights to tables to make seeing rows a little easier.
  * Tables and task lists now include counts of the number of results in the headers.
  * Further improved task selection in the task view.


# 0.5.14 (Beta)
  * Fix task highlighting when not grouping.
  * Remove some spurious console logging.
  * Slightly improve task highlighting behavior when clicking on a task.


# 0.5.13 (Beta)
Several smaller bugfixes!
  * Fix #997: Use the group by field name in the table name.
  * Prevent tons of errors if you incorrectly set the inline query prefix.


# 0.5.12 (Beta)
Improve error messages for queries somewhat and get rid of some ugly output.
# 0.5.11 (Beta)
Add detection of tasks inside of block quotes, as well as correctly implement automatic checking and unchecking of these tasks.
# 0.5.10 (Beta)
Adds the `Dataview: Force Refresh Views` Command (accessible via the Ctrl+P command view) to force current views to refresh immediately.
# 0.5.9 (Beta)
Another fix for due-date related emoji in tasks. I hate emoji.
# 0.5.8 (Beta)
Fix some issues with infinite loops of tasks due to bad Obsidian metadata (potentially due to being out of date?).
# 0.5.7 (Beta)
Fix issues with parsing '🗓️2021-08-29' due-date annotations on tasks, as well as an issue with properly extracting due/completed/completed times for use in queries.
# 0.5.6 (Beta)
Proper release of 0.5.5 plus one additional small improvement:
  * Add `duration * number` and `duration / number` operations for manipulation durations numerically.


# 0.5.5 (Beta)
More small features:
  * Fix issues with task sorting not doing anything. Sort away!
  * Table headers can now be arbitrary markdown. So you can put things like links in your headers: `TABLE (1 + 2) AS "[[File]]".
  * You can now specify the size of an image embed by providing WxH in it's display property: `![[image.png|50x50]]`.


# 0.5.4 (Beta)
Improved image rendering for some link types, and adds the `embed(link)` and `embed(link, false)` options to convert links to/from their embedded equivalents.
# 0.5.3 (Beta)
Iterative beta which adds a few nice QoL features and fixes some more bugs:
  * Internally swapped to a React-based renderer; this should not have a noticeable perf or usability impact, but makes it easier for me to implement complex table/list behaviors.
  * Naming your fields with `AS "Name"` is now optional; Dataview will infer the name from the expression automatically. For example, `TABLE 8 + 4, 3 + 6 FROM ...` is now a valid table expression, and the columns will be named `8 + 4` and `3 + 6` respectively.
  * Some issues with array and object rendering were corrected.
  * Error messages on empty dataview results were improved and now show up for all views.


Inline images are now rendered correctly in Dataview tables and lists - no more hacky `app://local/` shenanigans!
# 0.5.2 (Beta)
  * Fix #971: Objects now work properly inside DataviewQL evaluation.


# 0.5.1 (Beta)
  * Temporarily revert the new task metadata behavior: inline fields in sublists of tasks are added to the page, instead of the task. This behavior is not good, but is compatible with legacy usages of task metadata, which should not break some existing queries.
    * This behavior will be removed in the future behind a flag.
  * Added the 'visual' field to tasks - if set, tasks render 'visual' instead of their regular text.
  * Fixed `DataArray#mutate()`.


# 0.5.0 (Beta)
Re-release of broken release 0.4.23, now hopefully with fixes that make it work on (most) machines. I'll be doing beta releases for a little while until I can confirm the new version is stable; use BRAT (https://github.com/TfTHacker/obsidian42-brat) to easily track Dataview beta versions if you are interested in cutting edge features.
# 0.4.25
Fix #867: Create a container div per taskList to allow for multiple task views.
# 0.4.24
Re-release of 0.4.23f since Obsidian does not automatically update between non-semver versions.
# 0.4.23f
Remove some code which attempted to make tag queries case-insensitive; I'll reimplement this more generally later (it conflicts with existing queries which check tags via `contains(file.tags, "#Tag")` and similar).
# 0.4.23e
More task bugfixes / improvements, and a fix that caused task metadata to be duplicated.
# 0.4.23d
More inline field list parsing bug fixes. Hopefully we're back to a nice working order!
# 0.4.23c
Bugfix which adds support for '1)' style lists, as well as a very annoying null issue due to JavaScript being a very sad, very sad language.
# 0.4.23b
Bugfix for bad inlink/outlink computations; links were not being normalized properly so reverse lookups were not working.
# 0.4.23
The Task Update! This release reworks how dataview handles tasks and list items so that they should be much more intuitive to use and interact with:
  1. **Subtask Support** : Queries now search over all list items, instead of only over root elements. This should make task filtering much more usable, especially if you tend to put tasks under other list items or care specifically about subtasks.
  2. **Multiline Support** : Dataview now understands multi-line tasks and renders/updates them correctly.
  3. **Immediately Navigate to Task** : The new task view, aside from looking a little cleaner than previous views, now immediately navigates to the task in it's original file on click and selects it.
  4. **Grouping Support** : For DataviewJS users, `dv.taskList` now supports grouping (as produced by `groupBy` and the new `groupIn`) natively.


For DataviewJS users, the task and list representation has changed: `file.tasks` (and the new `file.lists`) contain every single task (including subtasks) in the file, instead of only the root elements. You can return to previous behavior by filtering out tasks with a non-null parent - i.e., `file.tasks.where(task => !task.parent)`. `dv.taskList` will intelligently deal with properly nesting and de-duplicating tasks, so just filter to the tasks you want to render and the API will do the rest.
This release also includes general backend improvements as we prepare for live-editing in Dataview views, as well as several community-contributed API improvements:
  * `DataArray#groupIn`: For grouping already grouped data, you can now use `array.groupIn(v => ...)`, which will group the innermost (original) data in the array instead of the top level groups. This allows for more easily grouping recursively, such as `dv.pages().groupBy(page => page.file.folder).groupIn(page => page.title)` producing a grouping of folders, then page titles.
  * `substring(string, start[, end])`: The last major missing string function is now available! Take slices of strings.
  * Improved `dv.el()` and other HTML functions - thanks @vitaly.
  * null and undefined entries sort at the end instead of the beginning by default; sorry to those whose code sorts wrong because of this, but it is a better default for most people's use cases.
  * All links are now properly normalized to their full paths, fixing many link comparison edge cases in DataviewJS.


Documentation additions for the new task functionality will be coming out in the next few days. The next release 0.4.24 is currently targeting expanded `FROM` query support, basic table view improvements, and general exporting functionality for Dataview. See you then!
# 0.4.22
The @pjeby update! This includes several performance improvements suggested by @pjeby to dramatically improve background Dataview performance as well as reduce some memory pressure. It also includes some minor bug-fixes and preliminary functionality:
  * Target ES2018 for better Promise support
  * Allow parsing shorthands in `dv.date()`.
  * Add additional metadata to inline field rendering which can be styled.
  * Cleanup events & workers on plugin uninstall, improving the Dataview uninstall/disable/reload experience.
  * Add preliminary `CALENDAR` queries - rendering similar to the obsidian-calendar plugin, see the documentation!


Dataview should perform much better on startup and when you have lots of tabs open - thanks again to @pjeby.
# 0.4.21
Bugfix release which primarily fixes issues that Dataview had with the live preview mode in upcoming Obsidian versions; Dataview live preview should now be functional. Also includes a number of smaller bugfixes.
  * Fix #646: Add `date(yesterday)` to create a date 24 hours ago.
  * Fix #618: Luxon is now available on the dataview API (`dv.luxon`).
  * Fix #510: Add `dv.duration()` for parsing durations.
  * Fix #647: All HTML functions in the DataviewJS API now return their rendered objects.
  * Fix #652: Fix parsing of invalid dates.
  * Fix #629: Fix block link parsing.
  * Fix #601: Timezones are now rendered properly and parsed properly in Dataview dates.
  * PR #637: Add `meta(link)` which allows you to access various metadata about a link itself.
  * Various minor null safety fixes.
  * Dataview now reports it's exact version and build time in logs.


# 0.4.20
Some feature work (mostly by other contributors) while I while away at section metadata. May also fix a few bugs!
  * Fix #448: You can now use the "Task Completion Tracking" option to automatically add completion metadata to tasks which are checked/unchecked through Dataview. Thanks to @sheeley.
  * Add a search bar to documentation. Thanks to @tzhou.
  * Add new date expressions for the start of the week (`date(sow)`), and the end of the week (`date(eow)`). Thanks @Jeamee and @v_mujunma.


Small minor bugfix / security releases may follow in the near future; otherwise, the next major release will include section and object metadata.
# 0.4.19
Bugfix release which corrects emoji parsing & localization issues.
  * Add `DataArray#into`, which lets you index into objects without flattening.
  * Renamed 'header' to 'section' in task metadata; 'header' will remain around for a few major releases to let people naturally migrate.
  * Fix #487: You no longer need spaces around '*' in expressions.
  * Fix #559: Fix unicode issues in variable canonicalization which was causing problems with non-Latin inline field keys.


## Duration Parsing
You can now include multiple units in durations: `dur(8 minutes, 4 seconds)` or `dur(2yr8mo12d)`. You can separate durations by commas, or use the abbreviated syntax with/without spaces.
# 0.4.18
Bugfix release which fixes bad inline field highlighting if '[' and '(' are mixed on the same line in particular orders.
# 0.4.17
Minor feature release to patch up more implementation holes.
## Single File Queries
You can now query from a specific file (instead of just folders and tags) by specifying the full file path:
```
TASK FROM "dataview/Test"
...

```

This is primarily useful for task queries, but will soon be useful for section and object queries in the near future as well.
## Better Inline Field Highlighting
The CSS for inline field highlighting has been fixed and some compatibility issues improved, so it should work on all themes now instead of only a few.
## dv.el()
DataviewJS now has `dv.el()`, which is like existing functions like `dv.paragraph` and `dv.span` but can create any HTML element type; for example:
```
dv.el("b","Text!");
dv.el("i",18);

```

# 0.4.16
Small performance release which substantially reduces the impact Dataview has on vault loading times (by spreading out file loading). The Dataview Index is now also eagerly initialized, so plugin consumers of the API can immediately start using it instead of waiting for the `dataview:api-ready` event.
# 0.4.15
A simple fix for #537 which properly 'awaits' value rendering in `dv.view()`. Fixes issues with values rendering out of order.
# 0.4.14
Small bugfix release.
  * Fixes inline field evaluation when using the new fancy highlighting.
  * You can now configure whether task links should show up at the beginning or end of the task (or just disable them) in the "Task Link Location" setting.
  * Most setting updates will immediately be applied to existing Dataviews.


# 0.4.13
Bugfix release which adds fancy rendering to inline-inline fields and includes a few bugfixes.
## Pretty Inline Fields
Inline fields of the form `[key:: value]` will now be rendered with fancy new HTML! By default, they are rendered with both the key and value. You can only render the value using parenthesis instead: `(key:: value)`. You can disable this feature in the configuration.
Full-line inline fields (that Dataview has supported for a long time) will gain similar rendering support soon; in the meanwhile, give the new syntax a try!
### Task Linking
Tasks now render with a link to the page/section that they are defined in, making `GROUP BY` and custom task editing easier to do:
  * A Task. 🔗
  * Another Task. 🔗
    * Some Random Subtask. 🔗


You can configure the symbol for the link or disable it altogether.
### Improving DataviewJS Posture
I am currently actively looking into improving DataviewJS sandboxing and general security posture. As a first small step in this, I have made DataviewJS opt-in instead of opt-out, and added a separate control for Inline DataviewJS. You may need to re-enable it in your settings if you use it.
More improvements and better JavaScript sandboxing will follow.
# 0.4.12-hotfix1
Re-release of 0.4.12 that fixes an important indexing issue.
  * Fix #505: Use `completion` instead of `completed` when setting task completion time.
  * Fix #509: Add `startswith` / `endswith` string functions.
  * Fix #488: Add `padleft` and `padright`, and `string`.
  * Fix #506, #512: Fix date comparisons due to a bizarre date zone issue.


# 0.4.12
Bugfix release following up 0.4.11 which includes a few minor function additions.
  * Fix #512: Strange zone issue causing dates to not be equal.
  * Fix #506: Same as #512.
  * Fix #488: Add `padleft` / `padright` functions.
  * Fix #509: Add `startswith` and `endswith` functions.
  * Fix #505: Correctly read completion dates for tasks from `completion`.


This release also includes improved testing thanks to mocking Obsidian plugin APIs!
# 0.4.11
Fixes task behavior and adds "truly inline" fields!
## Improved Task Behavior
Task queries are now much improved from their primitive foundations - you can now filter, sort, and group them! The FROM block is still page-based, sadly, though you can simply use `WHERE` instead if desired. For example, you can now access task fields like `text`, `line`, or `completed`:
```
TASK WHERE contains(text, "#tag")
WHERE !completed
GROUP BY file.folder

```

The full list of all available task metadata can be found here; tasks include all the information needed to uniquely identify them, and automatically inherit all of the metadata from their parent file as well (so you can access `file.name`, for example). You can also annotate tasks with inline fields, as described in the section below.
There is some additional UX work to be done - primarily on more easily allowing you to navigate to where the task is defined, as well as render tasks in views other than the `TASK` view. The semantics of how grouping works (to make it more intuitive/useful than it currently is) will likely also be revisited.
## Inline Inline Fields
Early support for truly inline fields have been added, where you can add metadata in the middle of a sentence. It looks similar to existing inline field syntax, but with brackets or parenthesis:
```
I would rate this a [rating:: 6]. It was (thoughts:: acceptable).

```

Improved rendering for all inline fields is coming in an upcoming update to improve the visual look of these inline fields.
## Issues
  * Fix #496: Fix task `SORT` functionality to do something.
  * Fix #492: Tasks now properly annotated with parent file information.
  * Fix #498: Fix task checking/unchecking logic (which broke due to a change in the task regex...).


# Initial
Start of the automatic changelog.



================================================================================

## 4. Annotation > Metadata Tasks





# Metadata on Tasks and Lists
Just like pages, you can also add **fields** on list item and task level to bind it to a specific task as context. For this you need to use the inline field syntax:
```
- [ ] Hello, this is some [metadata:: value]!
- [X] I finished this on [completion:: 2021-08-15].

```

Tasks and list items are the same data wise, so all your bullet points have all the information described here available, too.
## Field Shorthands
The Tasks plugin introduced a different notation by using Emoji to configure the different dates related to a task. In the context of Dataview, this notation is called `Field Shorthands`. The current version of Dataview only support the dates shorthands as shown below. The priorities and recurrence shorthands are not supported.
Example Example
  * Due this Saturday 🗓️2021-08-29
  * Completed last Saturday ✅2021-08-22
  * I made this on ➕1990-06-14
  * Task I can start this weekend 🛫2021-08-29
  * Task I finished ahead of schedule ⏳2021-08-29 ✅2021-08-22


There are two specifics to these emoji-shorthands. First, they omit the inline field syntax (no `[🗓️:: YYYY-MM-DD]` needed) and secondly, they map to a **textual** field name data-wise:
Field name | Short hand syntax  
---|---  
due | `🗓️YYYY-MM-DD`  
completion | `✅YYYY-MM-DD`  
created | `➕YYYY-MM-DD`  
start | `🛫YYYY-MM-DD`  
scheduled | `⏳YYYY-MM-DD`  
This means if you want to query for all tasks that are completed 2021-08-22, you'll write:
```
```dataview
TASK
WHERE completion = date("2021-08-22")
```

```

Which will list both variants - shorthands and textual annotation:
```
- [x] Completed last Saturday ✅2021-08-22
- [x] Some Done Task [completion:: 2021-08-22]

```

## Implicit Fields
As with pages, Dataview adds a number of implicit fields to each task or list item:
Inheritance of Fields
Tasks inherit _all fields_ from their parent page - so if you have a `rating` field in your page, you can also access it on your task in a `TASK` Query.
Field name | Data Type | Description  
---|---|---  
`status` | Text | The completion status of this task, as determined by the character inside the `[ ]` brackets. Generally a space `" "` for incomplete tasks and an `"x"` for completed tasks, but allows for plugins which support alternative task statuses.  
`checked` | Boolean | Whether or not this task's status is **not** empty, meaning it has some `status` character (which may or may not be `"x"`) instead of a space in its `[ ]` brackets.  
`completed` | Boolean | Whether or not this _specific_ task has been completed; this does not consider the completion or non-completion of any child tasks. A task is explicitly considered "completed" if it has been marked with an `"x"`. If you use a custom status, e.g. `[-]`, `checked` will be true, whereas `completed` will be false.  
`fullyCompleted` | Boolean | Whether or not this task and **all** of its subtasks are completed.  
`text` | Text | The plain text of this task, including any metadata field annotations.  
`visual` | Text | The text of this task, which is rendered by Dataview. This field can be overridden in DataviewJS to allow for different task text to be rendered than the regular task text, while still allowing the task to be checked (since Dataview validation logic normally checks the text against the text in-file).  
`line` | Number | The line of the file this task shows up on.  
`lineCount` | Number | The number of Markdown lines that this task takes up.  
`path` | Text | The full path of the file this task is in. Equals to `file.path` for pages.  
`section` | Link | Link to the section this task is contained in.  
`tags` | List | Any tags inside the task text.  
`outlinks` | List | Any links defined in this task.  
`link` | Link | Link to the closest linkable block near this task; useful for making links which go to the task.  
`children` | List | Any subtasks or sublists of this task.  
`task` | Boolean | If true, this is a task; otherwise, it is a regular list element.  
`annotated` | Boolean | True if the task text contains any metadata fields, false otherwise.  
`parent` | Number | The line number of the task above this task, if present; will be null if this is a root-level task.  
`blockId` | Text | The block ID of this task / list element, if one has been defined with the `^blockId` syntax; otherwise null.  
With usage of the shorthand syntax, following additional properties may be available:
  * `completion`: The date a task was completed.
  * `due`: The date a task is due, if it has one.
  * `created`: The date a task was created.
  * `start`: The date a task can be started.
  * `scheduled`: The date a task is scheduled to work on.


### Accessing Implicit Fields in Queries
If you're using a TASK Query, your tasks are the top level information and can be used without any prefix:
```
```dataview
TASK
WHERE !fullyCompleted
```

```

For every other Query type, you first need to access the implicit field `file.lists` or `file.tasks` to check for these list item specific implicit fields:
```
```dataview
LIST
WHERE any(file.tasks, (t) => !t.fullyCompleted)
```

```

This will give you back all the file links that have unfinished tasks inside. We get back a list of tasks on page level and thus need to use a list function to look at each element.



================================================================================

## 5. Api > Code Reference





# Codeblock Reference
Dataview JavaScript Codeblocks are created using the `dataviewjs` language specification for a codeblock:
```
```dataviewjs
dv.table([], ...)
```

```

The API is available through the implicitly provided `dv` (or `dataview`) variable, through which you can query for information, render HTML, and configure the view.
Asynchronous API calls are marked with `⌛`.
## Query
Query methods allow you to query the Dataview index for page metadata; to render this data, use the methods in the render section.
### `dv.current()`
Get page information (via `dv.page()`) for the page the script is currently executing on.
### `dv.pages(source)`
Take a single string argument, `source`, which is the same form as a query language source. Return a data array of page objects, which are plain objects with all of the page fields as values.
```
dv.pages()=>allpagesinyourvault
dv.pages("#books")=>allpageswithtag'books'
dv.pages('"folder"')=>allpagesfromfolder"folder"
dv.pages("#yes or -#no")=>allpageswithtag#yes,orwhichDON'T have tag #no
dv.pages('"folder"or#tag')=>allpageswithtag#tag,orfromfolder"folder"

```

Note that folders need to be double-quoted inside the string (i.e., `dv.pages("folder")` does not work, but `dv.pages('"folder"')` does) - this is to exactly match how sources are written in the query language.
### `dv.pagePaths(source)`
As with `dv.pages`, but just returns a data array of paths of pages that match the given source.
```
dv.pagePaths("#books")=>thepathsofpageswithtag'books'

```

### `dv.page(path)`
Map a simple path or link to the full page object, which includes all of the pages fields. Automatically does link resolution, and will figure out the extension automatically if not present.
```
dv.page("Index")=>Thepageobjectfor/Index
dv.page("books/The Raisin.md")=>Thepageobjectfor/books/The Raisin.md

```

## Render
### `dv.el(element, text)`
Render arbitrary text in the given html element. 
```
dv.el("b","This is some bold text");

```

You can specify custom classes to add to the element via `cls`, and additional attributes via `attr`:
```
dv.el("b","This is some text",{cls:"dataview dataview-class",attr:{alt:"Nice!"}});

```

### `dv.header(level, text)`
Render a header of level 1 - 6 with the given text.
```
dv.header(1,"Big!");
dv.header(6,"Tiny");

```

### `dv.paragraph(text)`
Render arbitrary text in a paragraph.
```
dv.paragraph("This is some text");

```

### `dv.span(text)`
Render arbitrary text in a span (no padding above/below, unlike a paragraph).
```
dv.span("This is some text");

```

### `dv.execute(source)`
Execute an arbitrary dataview query and embed the view into the current page.
```
dv.execute("LIST FROM #tag");
dv.execute("TABLE field1, field2 FROM #thing");

```

### `dv.executeJs(source)`
Execute an arbitrary DataviewJS query and embed the view into the current page.
```
dv.executeJs("dv.list([1, 2, 3])");

```

### `dv.view(path, input)`
Complex function which allows for custom views. Will attempt to load a JavaScript file at the given path, passing it `dv` and `input` and allowing it to execute. This allows for you to re-use custom view code across multiple pages. Note that this is an asynchronous function since it involves file I/O - make sure to `await` the result!
```
awaitdv.view("views/custom",{arg1:...,arg2:...});

```

If you want to also include custom CSS in your view, you can instead pass a path to a folder containing `view.js` and `view.css`; the CSS will be added to the view automatically:
```
views/custom
 -> view.js
 -> view.css

```

View scripts have access to the `dv` object (the API object), and an `input` object which is exactly whatever the second argument of `dv.view()` was.
Bear in mind, `dv.view()` cannot read from directories starting with a dot, like `.views`. Example of an incorrect usage:
```
awaitdv.view(".views/view1",{arg1:'a',arg2:'b'});

```

Attempting this will yield the following exception: 
```
Dataview: custom view not found for '.views/view1/view.js' or '.views/view1.js'.

```

Also note, directory paths always originate from the vault root.
#### Example
In this example, we have a custom script file named `view1.js` in the `scripts` directory. 
**File:** `scripts/view1.js`
```
console.log(`Loading view1`);
functionfoo(...args){
console.log('foo is called with args',...args);
}
foo(input)

```

And we have an Obsidian document located under `projects`. We'll call `dv.view()` from this document using the `scripts/view1.js` path.
**Document:** `projects/customViews.md`
```
awaitdv.view("scripts/view1",{arg1:'a',arg2:'b'})

```

When the above script is executed, it will print the following:
```
Loading view1
foo is called with args {arg1: 'a', arg2: 'b'}

```

## Dataviews
### `dv.list(elements)`
Render a dataview list of elements; accept both vanilla arrays and data arrays.
```
dv.list([1,2,3])=>listof1,2,3
dv.list(dv.pages().file.name)=>listofallfilenames
dv.list(dv.pages().file.link)=>listofallfilelinks
dv.list(dv.pages("#book").where(p=>p.rating>7))=>listofallbookswithratinggreaterthan7

```

### `dv.taskList(tasks, groupByFile)`
Render a dataview list of `Task` objects, as obtained by `page.file.tasks`. By default, this view will automatically group the tasks by their origin file. If you provide `false` as a second argument explicitly, it will instead render them as a single unified list.
```
// List all tasks from pages marked '#project'
dv.taskList(dv.pages("#project").file.tasks)
// List all *uncompleted* tasks from pages marked #project
dv.taskList(dv.pages("#project").file.tasks
.where(t=>!t.completed))
// List all tasks tagged with '#tag' from pages marked #project
dv.taskList(dv.pages("#project").file.tasks
.where(t=>t.text.includes("#tag")))
// List all tasks from pages marked '#project', without grouping.
dv.taskList(dv.pages("#project").file.tasks,false)

```

### `dv.table(headers, elements)`
Renders a dataview table. `headers` is an array of column headers. `elements` is an array of rows. Each row is itself an array of columns. Inside a row, every column which is an array will be rendered with bullet points.
```
dv.table(
["Col1","Col2","Col3"],
[
["Row1","Dummy","Dummy"],
["Row2",
["Bullet1",
"Bullet2",
"Bullet3"],
"Dummy"],
["Row3","Dummy","Dummy"]
]
);

```

An example of how to render a simple table of book info sorted by rating.
```
dv.table(["File","Genre","Time Read","Rating"],dv.pages("#book")
.sort(b=>b.rating)
.map(b=>[b.file.link,b.genre,b["time-read"],b.rating]))

```

## Markdown Dataviews
Functions which render to plain Markdown strings which you can then render or manipulate as desired.
### `dv.markdownTable(headers, values)`
Equivalent to `dv.table()`, which renders a table with the given list of headers and 2D array of elements, but returns plain Markdown.
```
// Render a simple table of book info sorted by rating.
consttable=dv.markdownTable(["File","Genre","Time Read","Rating"],dv.pages("#book")
.sort(b=>b.rating)
.map(b=>[b.file.link,b.genre,b["time-read"],b.rating]))
dv.paragraph(table);

```

### `dv.markdownList(values)`
Equivalent to `dv.list()`, which renders a list of the given elements, but returns plain Markdown.
```
constmarkdown=dv.markdownList([1,2,3]);
dv.paragraph(markdown);

```

### `dv.markdownTaskList(tasks)`
Equivalent to `dv.taskList()`, which renders a task list, but returns plain Markdown.
```
constmarkdown=dv.markdownTaskList(dv.pages("#project").file.tasks);
dv.paragraph(markdown);

```

## Utility
### `dv.array(value)`
Convert a given value or array into a Dataview data array. If the value is already a data array, returns it unchanged.
```
dv.array([1,2,3])=>dataviewdataarray[1,2,3]

```

### `dv.isArray(value)`
Returns true if the given value is an array or dataview array.
```
dv.isArray(dv.array([1,2,3]))=>true
dv.isArray([1,2,3])=>true
dv.isArray({x:1})=>false

```

### `dv.fileLink(path, [embed?], [display-name])`
Converts a textual path into a Dataview `Link` object; you can optionally also specify if the link is embedded as well as it's display name.
```
dv.fileLink("2021-08-08")=>linktofilenamed"2021-08-08"
dv.fileLink("book/The Raisin",true)=>embedlinkto"The Raisin"
dv.fileLink("Test",false,"Test File")=>linktofile"Test"withdisplayname"Test File"

```

### `dv.sectionLink(path, section, [embed?], [display?])`
Converts a textual path + section name into a Dataview `Link` object; you can optionally also specify if the link is embedded and it's display name.
```
dv.sectionLink("Index","Books")=>[[Index#Books]]
dv.sectionLink("Index","Books",false,"My Books")=>[[Index#Books|MyBooks]]

```

### `dv.blockLink(path, blockId, [embed?], [display?])`
Converts a textual path + block ID into a Dataview `Link` object; you can optionally also specify if the link is embedded and it's display name.
```
dv.blockLink("Notes","12gdhjg3")=>[[Index#^12gdhjg3]]

```

### `dv.date(text)`
Coerce text and links to luxon `DateTime`; if provided with a `DateTime`, return it unchanged.
```
dv.date("2021-08-08")=>DateTimeforAugust8th,2021
dv.date(dv.fileLink("2021-08-07"))=>dateTimeforAugust8th,2021

```

### `dv.duration(text)`
Coerce text to a luxon `Duration`; uses the same parsing rules as Dataview duration types.
```
dv.duration("8 minutes")=>Duration{8minutes}
dv.duration("9 hours, 2 minutes, 3 seconds")=>Duration{9hours,2minutes,3seconds}

```

### `dv.compare(a, b)`
Compare two arbitrary JavaScript values according to dataview's default comparison rules; useful if you are writing a custom comparator and want to fall back to the default behavior. Returns a negative value if `a < b`, 0 if `a = b`, and a positive value if `a > b`.
```
dv.compare(1,2)=-1
dv.compare("yes","no")=1
dv.compare({what:0},{what:0})=0

```

### `dv.equal(a, b)`
Compare two arbitrary JavaScript values and return true if they are equal according to Dataview's default comparison rules.
```
dv.equal(1,2)=false
dv.equal(1,1)=true

```

### `dv.clone(value)`
Deep clone any Dataview value, including dates, arrays, and links.
```
dv.clone(1)=1
dv.clone({a:1})={a:1}

```

### `dv.parse(value)`
Parse an arbitrary string object into a complex Dataview type (mainly supporting links, dates, and durations).
```
dv.parse("[[01 - COMANDO/1.1 Missões/3. Ativos/Viajante do Tempo/Conteúdos/Viagens/A Fé no Coliseu - A Grande Perseguição (303 d.C)/03 - Conteúdo para Instagram/Carrousels/A Escalada do Terror Como Roma Tentou Apagar o Cristianismo em 4 Decretos/A]]")=Link{path:A}
dv.parse("2020-08-14")=DateTime{2020-08-14}
dv.parse("9 seconds")=Duration{9seconds}

```

## File I/O
These utility methods are all contained in the `dv.io` sub-API, and are all _asynchronous_ (marked by ⌛).
### ⌛ `dv.io.csv(path, [origin-file])`
Load a CSV from the given path (a link or string). Relative paths will be resolved relative to the optional origin file (defaulting to the current file if not provided). Return a dataview array, each element containing an object of the CSV values; if the file does not exist, return `undefined`.
```
awaitdv.io.csv("hello.csv")=>[{column1:...,column2:...},...]

```

### ⌛ `dv.io.load(path, [origin-file])`
Load the contents of the given path (a link or string) asynchronously. Relative paths will be resolved relative to the optional origin file (defaulting to the current file if not provided). Returns the string contents of the file, or `undefined` if the file does not exist.
```
awaitdv.io.load("File")=>"# File\nThis is an example file..."

```

### `dv.io.normalize(path, [origin-file])`
Convert a relative link or path into an absolute path. If `origin-file` is provided, then the resolution is doing as if you were resolving the link from that file; if not, the path is resolved relative to the current file.
```
dv.io.normalize("Test")=>"dataview/test/Test.md",ifinside"dataview/test"
dv.io.normalize("Test","dataview/test2/Index.md")=>"dataview/test2/Test.md",irrespectiveofthecurrentfile

```

## Query Evaluation
### ⌛ `dv.query(source, [file, settings])`
Execute a Dataview query and return the results as a structured return. The return type of this function varies by the query type being executed, though will always be an object with a `type` denoting the return type. This version of `query` returns a result type - you may want `tryQuery`, which instead throws an error on failed query execution.
```
awaitdv.query("LIST FROM #tag")=>
{successful:true,value:{type:"list",values:[value1,value2,...]}}
awaitdv.query(`TABLE WITHOUT ID file.name, value FROM "path"`)=>
{successful:true,value:{type:"table",headers:["file.name","value"],values:[["A",1],["B",2]]}}
awaitdv.query("TASK WHERE due")=>
{successful:true,value:{type:"task",values:[task1,task2,...]}}

```

`dv.query` accepts two additional, optional arguments: 1. `file`: The file path to resolve the query from (in case of references to `this`). Defaults to the current file. 2. `settings`: Execution settings for running the query. This is largely an advanced use case (where I recommend you directly check the API implementation to see all available options).
### ⌛ `dv.tryQuery(source, [file, settings])`
Exactly the same as `dv.query`, but more convenient in short scripts as execution failures will be raised as JavaScript exceptions instead of a result type.
### ⌛ `dv.queryMarkdown(source, [file], [settings])`
Equivalent to `dv.query()`, but returns rendered Markdown.
```
awaitdv.queryMarkdown("LIST FROM #tag")=>
{successful:true,value:{"- [[Page 1]]\n- [[Page 2]]"}}

```

### ⌛ `dv.tryQueryMarkdown(source, [file], [settings])`
Exactly the same as `dv.queryMarkdown()`, but throws an error on parse failure.
### `dv.tryEvaluate(expression, [context])`
Evaluate an arbitrary dataview expression (like `2 + 2` or `link("text")` or `x * 9`); throws an `Error` on parse or evaluation failure. `this` is an always-available implicit variable which refers to the current file.
```
dv.tryEvaluate("2 + 2")=>4
dv.tryEvaluate("x + 2",{x:3})=>5
dv.tryEvaluate("length(this.file.tasks)")=>numberoftasksinthecurrentfile

```

### `dv.evaluate(expression, [context])`
Evaluate an arbitrary dataview expression (like `2 + 2` or `link("text")` or `x * 9`), returning a `Result` object of the result. You can unwrap the result type by checking `result.successful` (and then fetching either `result.value` or `result.error`). If you want a simpler API that throws an error on a failed evaluation, use `dv.tryEvaluate`.
```
dv.evaluate("2 + 2")=>Successful{value:4}
dv.evaluate("2 +")=>Failure{error:"Failed to parse ... "}

```




================================================================================

## 6. Annotation > Types Of Metadata


# Field Types
All fields in dataview have a **type** , which determines how dataview will render, sort, and operate on that field. Read more about how to create fields on "Adding metadata" and which information you have automatically available on metadata on pages and metadata on tasks and lists.
## Why does the type matter?
Dataview provides functions you can use to modify your metadata and allows you to write all sorts of complex queries. Specific functions need specific data types to work correctly. That means the data type of your field determines which functions you can use on these fields and how the functions behave. Furthermore, depending on the type, the output dataview renders can be different.
Most of the time you do not need to worry too much about the type of your fields, but if you want to perform calculations and other magical operations on your data, you should be aware of them.
Different rendering based on type
If you have this file: 
```
date1::2021-02-26T15:15
date2::2021-04-17 18:00
```dataview
TABLE date1, date2
WHERE file = this.file
```

```

You'll see the following output (depending on your Date + Time Format Setting for dataview): 
File (1) | date1 | date2  
---|---|---  
Untitled 2 | 3:15 PM - February 26, 2021 | 2021-04-17 18:00  
`date1` is recognized as a **Date** while `date2` is a normal **Text** to dataview, that's why `date1` is parsed differently for you. Find out more on Dates below. 
## Available Field Types
Dataview knows several field types to cover common use cases.
### Text
The default catch-all. If a field doesn't match a more specific type, it is plain text.
```
Example:: This is some normal text.

```

Multiline text
Multiline text as a value is only possible via YAML Frontmatter and the pipe operator: 
```
---
poem:|
Because I could not stop for Death,
He kindly stopped for me;
The carriage held but just ourselves
And Immortality.
author:"[[EmilyDickinson]]"
title:"BecauseIcouldnotstopforDeath"
---

```

For inline fields, a line break means the end of the value. 
### Number
Numbers like '6' and '3.6'. 
```
Example:: 6
Example:: 2.4
Example:: -80

```

In YAML Frontmatter, you write a number without surrounding quotes: 
```
---
rating:8
description:"Anicelittlehorrormovie"
---

```

### Boolean
Boolean only knows two values: true or false, as the programming concept.
```
Example:: true
Example:: false

```

### Date
Text that matches the ISO8601 notation will be automatically transformed into a date object. ISO8601 follows the format `YYYY-MM[-DDTHH:mm:ss.nnn+ZZ]`. Everything after the month is optional.
```
Example:: 2021-04 
Example:: 2021-04-18
Example:: 2021-04-18T04:19:35.000
Example:: 2021-04-18T04:19:35.000+06:30

```

When querying for these dates, you can access properties that give you a certain portion of your date back:
  * field.year
  * field.month
  * field.weekyear
  * field.week
  * field.weekday
  * field.day
  * field.hour
  * field.minute
  * field.second
  * field.millisecond


For example, if you're interested in which month your date lies, you can access it via `datefield.month`:
```
birthday:: 2001-06-11
```dataview
LIST birthday
WHERE birthday.month = date(now).month
```

```

gives you back all birthdays happening this month. Curious about `date(now)`? Read more about it under literals.
Displaying of date objects
Dataview renders date objects in a human readable format, i.e. `3:15 PM - February 26, 2021`. You can adjust how this format looks like in Dataview's Setting under "General" with "Date Format" and "Date + Time Format". If you want to adjust the format in a specific query only, use the dateformat function.
### Duration
Durations are text of the form `<time> <unit>`, like `6 hours` or `4 minutes`. Common English abbreviations like `6hrs` or `2m` are accepted. You can specify multiple units in one field, i.e. `6hr 4min`, optionally with comma separator: `6 hours, 4 minutes`
```
Example:: 7 hours
Example:: 16days
Example:: 4min
Example:: 6hr7min
Example:: 9 years, 8 months, 4 days, 16 hours, 2 minutes
Example:: 9 yrs 8 min

```

Find the complete list of values that are recognized as a duration on literals. 
Calculations with dates and durations
Date and Duration types are compatible with each other. This means you can, for example, add durations to a date to produce a new date: 
```
departure:: 2022-10-07T15:15
length of travel:: 1 day, 3 hours
**Arrival**: `= this.departure + this.length-of-travel`

```

and you get back a duration when calculating with dates: 
```
release-date:: 2023-02-14T12:00
`= this.release-date - date(now)` until release!!

```

Curious about `date(now)`? Read more about it under literals.
### Link
Obsidian links like `[[Page]]` or `[[Page|Page Display]]`.
```
Example:: [[A Page]]
Example:: [[Some Other Page|Render Text]]

```

Links in YAML Frontmatter
If you reference a link in frontmatter, you need to quote it, as so: `key: "[[Link]]"`. This is default Obsidian-supported behavior. Unquoted links lead to a invalid YAML frontmatter that cannot be parsed anymore. 
```
---
parent:"[[parentPage]]"
---

```

Please be aware that this is only a link for dataview, but not for Obsidian anymore - that means it won't show up in the outgoing links, won't be displayed on graph view and won't be updated on i.e. a rename. 
### List
Lists are multi-value fields. In YAML, these are defined as normal YAML lists: 
```
---
key3:[one,two,three]
key4:
-four
-five
-six
---

```

In inline fields, they are comma-separated lists values:
```
Example1:: 1, 2, 3
Example2:: "yes", "or", "no"

```

Please be aware that in Inline fields, you need to wrap **text values into quotes** to be recognized as a list (see `Example2`). `yes, or, no` is recognized as plain text.
Duplicated metadata keys in the same file lead to lists
If you're using a metadata key twice or more in the same note, dataview will collect all values and give you a list. For example 
```
grocery:: flour
[...]
grocery:: soap
```dataview
LIST grocery
WHERE file = this.file
```

```

will give you a **list** out of `flour` and `soap` back. 
Arrays are lists
In some places of this documentation, you'll read the term "array". Array is the term for lists in Javascript - Lists and Arrays are the same. A function that needs an array as argument needs a list as argument.
### Object
Objects are a map of multiple fields under one parent field. These can only be defined in YAML frontmatter, using the YAML object syntax: 
```
---
obj:
key1:"Val"
key2:3
key3:
-"List1"
-"List2"
-"List3"
---

```

In queries, you can then access these child values via `obj.key1` etc:
```
```dataview
TABLE obj.key1, obj.key2, obj.key3
WHERE file = this.file
```

```




================================================================================

## 7. Api > Data Array





# Data Arrays
The general representation of result lists in Dataview is the `DataArray`, which is a proxied version of the JavaScript array with expanded functionality. Data arrays support indexing and iteration (via `for` and `for ... of` loops), like normal arrays do, but also include many data manipulation operators like `sort`, `groupBy`, `distinct`, `where`, and so on to make manipulating tabular data easier.
## Creation
Data arrays are returned by most Dataview APIs that can return multiple results, such as `dv.pages()`. You can also explicitly convert a normal JavaScript array into a Dataview array using `dv.array(<array>)`. If you want to convert a Data array back to a normal array, use `DataArray#array()`.
## Indexing and Swizzling
Data arrays support regular indexing just like normal arrays (like `array[0]`), but importantly, they also support query-language-style "swizzling": if you index into a data array with a field name (like `array.field`), it automatically maps every element in the array to `field`, flattening `field` if it itself is also an array.
For example, `dv.pages().file.name` will return a data array of all file names in your vault; `dv.pages("#books").genres` will return a flattened list of all genres in your books.
## Raw Interface
The full interface for the data array implementation is provided below for reference:
```
/** A function which maps an array element to some value. */
exporttypeArrayFunc<T,O>=(elem:T,index:number,arr:T[])=>O;
/** A function which compares two types. */
exporttypeArrayComparator<T>=(a:T,b:T)=>number;
/**
 * Proxied interface which allows manipulating array-based data. All functions on a data array produce a NEW array
 * (i.e., the arrays are immutable).
 */
exportinterfaceDataArray<T>{
/** The total number of elements in the array. */
length:number;
/** Filter the data array down to just elements which match the given predicate. */
where(predicate:ArrayFunc<T,boolean>):DataArray<T>;
/** Alias for 'where' for people who want array semantics. */
filter(predicate:ArrayFunc<T,boolean>):DataArray<T>;
/** Map elements in the data array by applying a function to each. */
map<U>(f:ArrayFunc<T,U>):DataArray<U>;
/** Map elements in the data array by applying a function to each, then flatten the results to produce a new array. */
flatMap<U>(f:ArrayFunc<T,U[]>):DataArray<U>;
/** Mutably change each value in the array, returning the same array which you can further chain off of. */
mutate(f:ArrayFunc<T,any>):DataArray<any>;
/** Limit the total number of entries in the array to the given value. */
limit(count:number):DataArray<T>;
/**
   * Take a slice of the array. If `start` is undefined, it is assumed to be 0; if `end` is undefined, it is assumed
   * to be the end of the array.
   */
slice(start?:number,end?:number):DataArray<T>;
/** Concatenate the values in this data array with those of another iterable / data array / array. */
concat(other:Iterable<T>):DataArray<T>;
/** Return the first index of the given (optionally starting the search) */
indexOf(element:T,fromIndex?:number):number;
/** Return the first element that satisfies the given predicate. */
find(pred:ArrayFunc<T,boolean>):T|undefined;
/** Find the index of the first element that satisfies the given predicate. Returns -1 if nothing was found. */
findIndex(pred:ArrayFunc<T,boolean>,fromIndex?:number):number;
/** Returns true if the array contains the given element, and false otherwise. */
includes(element:T):boolean;
/**
   * Return a string obtained by converting each element in the array to a string, and joining it with the
   * given separator (which defaults to ', ').
   */
join(sep?:string):string;
/**
   * Return a sorted array sorted by the given key; an optional comparator can be provided, which will
   * be used to compare the keys in lieu of the default dataview comparator.
   */
sort<U>(key:ArrayFunc<T,U>,direction?:"asc"|"desc",comparator?:ArrayComparator<U>):DataArray<T>;
/**
   * Return an array where elements are grouped by the given key; the resulting array will have objects of the form
   * { key: <key value>, rows: DataArray }.
   */
groupBy<U>(key:ArrayFunc<T,U>,comparator?:ArrayComparator<U>):DataArray<{key:U;rows:DataArray<T>}>;
/**
   * Return distinct entries. If a key is provided, then rows with distinct keys are returned.
   */
distinct<U>(key?:ArrayFunc<T,U>,comparator?:ArrayComparator<U>):DataArray<T>;
/** Return true if the predicate is true for all values. */
every(f:ArrayFunc<T,boolean>):boolean;
/** Return true if the predicate is true for at least one value. */
some(f:ArrayFunc<T,boolean>):boolean;
/** Return true if the predicate is FALSE for all values. */
none(f:ArrayFunc<T,boolean>):boolean;
/** Return the first element in the data array. Returns undefined if the array is empty. */
first():T;
/** Return the last element in the data array. Returns undefined if the array is empty. */
last():T;
/** Map every element in this data array to the given key, and then flatten it.*/
to(key:string):DataArray<any>;
/**
   * Recursively expand the given key, flattening a tree structure based on the key into a flat array. Useful for handling
   * hierarchical data like tasks with 'subtasks'.
   */
expand(key:string):DataArray<any>;
/** Run a lambda on each element in the array. */
forEach(f:ArrayFunc<T,void>):void;
/** Calculate the sum of the elements in the array. */
sum():number;
/** Calculate the average of the elements in the array. */
avg():number;
/** Calculate the minimum of the elements in the array. */
min():number;
/** Calculate the maximum of the elements in the array. */
max():number;
/** Convert this to a plain javascript array. */
array():T[];
/** Allow iterating directly over the array. */
[Symbol.iterator]():Iterator<T>;
/** Map indexes to values. */
[index:number]:any;
/** Automatic flattening of fields. Equivalent to implicitly calling `array.to("field")` */
[field:string]:any;
}

```




================================================================================

## 8. Annotation > Metadata Pages





# Metadata on Pages
You can add fields to a markdown page (a note) in three different ways - via Frontmatter, Inline fields and Implicit fields. Read more about the first two possibilities in "how to add metadata".
## Implicit Fields
Dataview automatically adds a large amount of metadata to each page. These implicit and automatically added fields are collected under the field `file`. Following are available:
Field Name | Data Type | Description  
---|---|---  
`file.name` | Text | The file name as seen in Obsidians sidebar.  
`file.folder` | Text | The path of the folder this file belongs to.  
`file.path` | Text | The full file path, including the files name.  
`file.ext` | Text | The extension of the file type; generally `md`.  
`file.link` | Link | A link to the file.  
`file.size` | Number | The size (in bytes) of the file.  
`file.ctime` | Date with Time | The date that the file was created.  
`file.cday` | Date | The date that the file was created.  
`file.mtime` | Date with Time | The date that the file was last modified.  
`file.mday` | Date | The date that the file was last modified.  
`file.tags` | List | A list of all unique tags in the note. Subtags are broken down by each level, so `#Tag/1/A` will be stored in the list as `[#Tag, #Tag/1, #Tag/1/A]`.  
`file.etags` | List | A list of all explicit tags in the note; unlike `file.tags`, does not break subtags down, i.e. `[#Tag/1/A]`  
`file.inlinks` | List | A list of all incoming links to this file, meaning all files that contain a link to this file.  
`file.outlinks` | List | A list of all outgoing links from this file, meaning all links the file contains.  
`file.aliases` | List | A list of all aliases for the note as defined via the YAML frontmatter.  
`file.tasks` | List | A list of all tasks (I.e., `| [ ] some task`) in this file.  
`file.lists` | List | A list of all list elements in the file (including tasks); these elements are effectively tasks and can be rendered in task views.  
`file.frontmatter` | List | Contains the raw values of all frontmatter in form of `key | value` text values; mainly useful for checking raw frontmatter values or for dynamically listing frontmatter keys.  
`file.day` | Date | Only available if the file has a date inside its file name (of form `yyyy-mm-dd` or `yyyymmdd`), or has a `Date` field/inline field.  
`file.starred` | Boolean | If this file has been bookmarked via the Obsidian Core Plugin "Bookmarks".  
## Example page
This is a small Markdown page which includes both user-defined ways to add metadata:
```
---
genre: "action"
reviewed: false
---
# Movie X
#movies
**Thoughts**:: It was decent.
**Rating**:: 6
[mood:: okay] | [length:: 2 hours]

```

In addition to the values you see here, the page has also all keys listed above available.
### Example Query
You can query part of the above information with following query, for example:
```
```dataview
TABLE file.ctime, length, rating, reviewed
FROM#movies
```

```




================================================================================

## 9. Api > Code Examples





# Codeblock Examples
## Grouped Books
Group your books by genre, then create a table for each sorted by rating via a straightforward usage of the dataview rendering API:
```
for(letgroupofdv.pages("#book").groupBy(p=>p.genre)){
dv.header(3,group.key);
dv.table(["Name","Time Read","Rating"],
group.rows
.sort(k=>k.rating,'desc')
.map(k=>[k.file.link,k["time-read"],k.rating]))
}

```

!Grouped Books Example
## Find All Direct And Indirectly Linked Pages
Use a simple set + stack depth first search to find all notes linked to the current note, or a note of your choosing:
```
letpage=dv.current().file.path;
letpages=newSet();
letstack=[page];
while(stack.length>0){
letelem=stack.pop();
letmeta=dv.page(elem);
if(!meta)continue;
for(letinlinkofmeta.file.inlinks.concat(meta.file.outlinks).array()){
console.log(inlink);
if(pages.has(inlink.path))continue;
pages.add(inlink.path);
stack.push(inlink.path);
}
}
// Data is now the file metadata for every page that directly OR indirectly links to the current page.
letdata=dv.array(Array.from(pages)).map(p=>dv.page(p));

```




================================================================================

## 10. Api > Intro





# Overview
The Dataview JavaScript API allows for executing arbitrary JavaScript with access to the dataview indices and query engine, which is good for complex views or interop with other plugins. The API comes in two flavors: plugin facing, and user facing (or 'inline API usage').
## Inline Access
You can create a "DataviewJS" block via:
```
```dataviewjs
dv.pages("#thing")...
```

```

Code executed in such codeblocks have access to the `dv` variable, which provides the entirety of the codeblock-relevant dataview API (like `dv.table()`, `dv.pages()`, and so on). For more information, check out the codeblock API reference.
## Plugin Access
You can access the Dataview Plugin API (from other plugins or the console) through `app.plugins.plugins.dataview.api`; this API is similar to the codeblock reference, with slightly different arguments due to the lack of an implicit file to execute the queries in. For more information, check out the Plugin API reference.



================================================================================

## 11. Annotation > Add Metadata





# Adding Metadata to your Pages
Dataview cannot query all content of your vault. In order to be able to search, filter and display content, this content needs to be **indexed**. Some content is indexed automatically, like bullet points or task lists - so called **Implicit fields** , more on that below - and other data needs to be saved in a metadata **field** to be accessible through dataview. 
## What is a "field"?
A metadata field is a pair of a **key** and a **value**. The _value_ of a field has a data type (more on that here) that determines how this field will behave when querying it. 
You can add any number of fields to a **note** , a **list item** or a **task**. 
## How do I add fields?
You can add fields to a **note** in three different ways. How a field look like depends on the way you add it.
On **tasks or list items** , you will have YAML Frontmatter information available, but won't be able to add them to a specific list item. If you want to add metadata to one list item or task only, use Inline Fields.
### Frontmatter
Frontmatter is a common Markdown extension which allows for YAML metadata to be added to the top of a page. It is natively supported by Obsidian and explained in its official documentation. All YAML Frontmatter fields will be automatically available as Dataview fields.
```
---
alias:"document"
last-reviewed:2021-08-17
thoughts:
rating:8
reviewable:false
---

```

With this your note has metadata fields named `alias`, `last-reviewed`, and `thoughts`. Each of these have different **data types** :
  * `alias` is a text, because its wrapped in ""
  * `last-reviewed` is a date, because it follows the ISO date format
  * `thoughts` is a object field, because it uses the YAML Frontmatter object syntax


You could query for this note with the following query:
```
```dataview
LIST
WHERE thoughts.rating = 8
```

```

### Inline Fields
For those wanting a more natural-looking annotation, Dataview supports "inline" fields via a `Key:: Value` syntax that you can use everywhere in your file. This allows you to write your queryable data right where you need it - for example in the middle of a sentence. 
If your inline field has an own line, without any content beforehand, you can write it like this: 
```
# Markdown Page
Basic Field:: Some random Value
**Bold Field**:: Nice!

```

All content after the `::` is the value of the field until the next line break.
Mind the `::`
Note that you need to use a double colon `::` between key and value when using inline fields, contrary to YAML Frontmatter fields where one colon is enough. 
If you want to embed metadata inside sentences, or multiple fields on the same line, you can use the bracket syntax and wrap your field in square brackets:
```
I would rate this a [rating:: 9]! It was [mood:: acceptable].

```

Fields on list items and tasks
When you want to annotate a list item, e.g. a task, with metadata, you always need to use the bracket syntax (because the field is not the only information in this line) 
```
- [ ] Send an mail to David about the deadline [due:: 2022-04-05].

```

Bracketed inline fields are the only way to explicitly add fields to specific list items, YAML frontmatter always applies to the whole page (but is also available in context of list items.) 
There is also the alternative parenthesis syntax, which hides the key when rendered in Reader mode:
```
This will not show the (longKeyIDontNeedWhenReading:: key).

```

will render to:
```
This will not show the key.

```

You can use YAML Frontmatter and Inline fields with all syntax variants together in one file. You do not need to decide for one and can mix them to fit your workflow.
## Field names
Imagine you used all the examples for Inline fields you see above in one note, then following metadata would be available to you:
Metadata Key | Sanitized Metadata key | Value | Data Type of Value  
---|---|---|---  
`Basic Field` | `basic-field` | Some random Value | Text  
`Bold Field` | `bold-field` | Nice! | Text  
`rating` | - | 9 | Number  
`mood` | - | acceptable | Text  
`due` | - | Date Object for 2022-04-05 | Date  
`longKeyIDontNeedWhenReading` | `longkeyidontneedwhenreading` | key | Text  
Like you can see in the table, if you are using **spaces or capitalized letters** in your metadata key name, dataview will provide you with a **sanitized version** of the key. 
**Keys with spaces** cannot be used in a query as-is. You have two possibilities here: Either use the sanitized name, that is always all lowercase and with dashes instead of spaces or use the **row** variable syntax. Find out more in the FAQ.
**Keys with capitalized letters** can be used as-is, if you wish. The sanitized version allows you to query for a key independent of its capitalization and makes it easier to use: You can query the same field that's, for example, in one file named `someMetadata` and in another `someMetaData` when using the sanitized key `somemetadata`. 
In addition, the **bold field key is missing its formatting tokens**. Even though the `**` used to make it appear bold are part of the key name in the file, they are left out when indexing your note. The same goes for all other built-in formatting, like strike through or italic. This means formatted keys can only be queried without their formatting. This allows you to format the key in context of the note without worrying that you might create different keys for the same type of information. 
### Usage of emojis and non-latin characters
You are not limited to latin characters when naming your metadata fields. You can use all characters available in UTF-8:
```
Noël:: Un jeu de console
クリスマス:: 家庭用ゲーム機
[🎅:: a console game]
[xmas🎄:: a console game]

```

**Using emojis as metadata keys** is possible, but it comes with some limitations. When using emojis in field names, you need to put them into square brackets so that dataview recognize them correctly. Also, please be aware when switching the OS (i.e. from Windows to Android), the same emoji could use another character code and you might not find your metadata when querying it.
Task Field Shorthands
An exception to this are the shorthand syntax in Tasks. You can use shorthands without bracketing. Please mind though that this only counts for listed shorthands - every other field (if with emojis or not) need to use the `[key:: value]` syntax.
## Implicit fields
Even if you do not add any metadata explicitly to your note, dataview provides you with a big amount of indexed data out of the box. Some examples for implicit fields are:
  * day the file was created (`file.cday`)
  * links in the file (`file.outlinks`)
  * tags in the file (`file.etags`)
  * all list items in the file (`file.lists` and `file.tasks`)


and many more. Available implicit fields differ depending if you look at a page or a list item. Find the full list of available implicit fields on Metadata on pages and Metadata on Tasks and Lists.



================================================================================

## 12. Friends




# Friends of Dataview
A list of plugins which may be helpful for Dataview related workflows:
  * MetaEdit - Add or update yaml properties and Dataview fields easily


Another non-exhaustive list of plugins which use Dataview for some of the heavy-lifting required for their features:
  * Kanban - Create markdown-backed Kanban boards in Obsidian
  * Breadcrumbs - Gives you a way to visualize a custom-built hierarchy in your Obsidian vault
  * Supercharged Links - Allows you to style links in your Obsidian vault based on note metadata


A full list can be found using GitHub's Dependents feature.



================================================================================

## 13. Queries > Data Commands





# Data Commands
The different commands that dataview queries can be made up of. Commands are executed in order, and you can have duplicate commands (so multiple `WHERE` blocks or multiple `GROUP BY` blocks, for example).
## FROM
The `FROM` statement determines what pages will initially be collected and passed onto the other commands for further filtering. You can select from any source, which currently means by folder, by tag, or by incoming/outgoing links.
  * **Tags** : To select from a tag (and all its subtags), use `FROM #tag`.
  * **Folders** : To select from a folder (and all its subfolders), use `FROM "folder"`.
  * **Single Files** : To select from a single file, use `FROM "path/to/file"`.
  * **Links** : You can either select links TO a file, or all links FROM a file.
  * To obtain all pages which link TO `[[note]]`, use `FROM [[note]]`.
  * To obtain all pages which link FROM `[[note]]` (i.e., all the links in that file), use `FROM outgoing([[note]])`.


You can compose these filters in order to get more advanced sources using `and` and `or`.
  * For example, `#tag and "folder"` will return all pages in `folder` and with `#tag`.
  * `[[Food]] or [[Exercise]]` will give any pages which link to `[[Food]]` OR `[[Exercise]]`.


You can also "negate" sources to obtain anything that does NOT match a source using `-`:
  * `-#tag` will exclude files which have the given tag.
  * `#tag and -"folder"` will only include files tagged `#tag` which are NOT in `"folder"`.


## WHERE
Filter pages on fields. Only pages where the clause evaluates to `true` will be yielded.
```
WHERE <clause>

```

  1. Obtain all files which were modified in the last 24 hours:
```
LISTWHEREfile.mtime>=date(today)-dur(1day)

```

  2. Find all projects which are not marked complete and are more than a month old:
```
LISTFROM#projects
WHERE!completedANDfile.ctime<=date(today)-dur(1month)

```



## SORT
Sorts all results by one or more fields.
```
SORT date [ASCENDING/DESCENDING/ASC/DESC]

```

You can also give multiple fields to sort by. Sorting will be done based on the first field. Then, if a tie occurs, the second field will be used to sort the tied fields. If there is still a tie, the third sort will resolve it, and so on.
```
SORT field1 [ASCENDING/DESCENDING/ASC/DESC], ..., fieldN [ASC/DESC]

```

## GROUP BY
Group all results on a field. Yields one row per unique field value, which has 2 properties: one corresponding to the field being grouped on, and a `rows` array field which contains all of the pages that matched.
```
GROUP BY field
GROUP BY (computed_field) AS name

```

In order to make working with the `rows` array easier, Dataview supports field "swizzling". If you want the field `test` from every object in the `rows` array, then `rows.test` will automatically fetch the `test` field from every object in `rows`, yielding a new array. You can then apply aggregation operators like `sum()` or `flat()` over the resulting array.
## FLATTEN
Flatten an array in every row, yielding one result row per entry in the array.
```
FLATTEN field
FLATTEN (computed_field) AS name

```

For example, flatten the `authors` field in each literature note to give one row per author:
Query
```
TABLEauthorsFROM#LiteratureNote
FLATTENauthors

```

Output
File | authors  
---|---  
stegEnvironmentalPsychologyIntroduction2018 SN | Steg, L.  
stegEnvironmentalPsychologyIntroduction2018 SN | Van den Berg, A. E.  
stegEnvironmentalPsychologyIntroduction2018 SN | De Groot, J. I. M.  
Soap Dragons SN | Robert Lamb  
Soap Dragons SN | Joe McCormick  
smithPainAssaultSelf2007 SN | Jonathan A. Smith  
smithPainAssaultSelf2007 SN | Mike Osborn  
A good use of this would be when there is a deeply nested list that you want to use more easily. For example, `file.lists` or `file.tasks`. Note the simpler query though the end results are slightly different (grouped vs non-grouped). You can use a `GROUP BY file.link` to achieve identical results but would need to use `rows.T.text` as described earlier.
```
table T.text as "Task Text"
from "Scratchpad"
flatten file.tasks as T
where T.text

```

```
table filter(file.tasks.text, (t) => t) as "Task Text"
from "Scratchpad"
where file.tasks.text

```

`FLATTEN` makes it easier to operate on nested lists since you can then use simpler where conditions on them as opposed to using functions like `map()` or `filter()`.
## LIMIT
Restrict the results to at most N values.
```
LIMIT 5

```

Commands are processed in the order they are written, so the following sorts the results _after_ they have already been limited:
```
LIMIT 5
SORT date ASCENDING

```




================================================================================

## 14. Queries > Differences To Sql





# Dataview Query Language (DQL) and SQL
If you are familiar with SQL and experienced in writing SQL queries, you might approach writing a DQL query in a similar way. However, DQL is significantly different from SQL.
A DQL query is **executed from top to bottom** , line-by-line. It is more like a computer program than a typical SQL query.
When a line is evaluated, it produces a result set and **passes the whole set on to the next DQL line** which will manipulate the set that it received from the previous line. This is why in DQL it is possible, for example, to have multiple WHERE clauses. But in DQL it is not a 'clause' but a 'data command'. Every line of a DQL query (except the 1st and 2nd lines) is a 'data command'.
## Anatomy of a DQL query
Instead of starting with SELECT, a DQL query starts with a word determining the Query Type, which determines how your final result will be rendered on screen (a table, a list, a task list, or a calendar). Then follows the list of fields, which is actually very similar to the column list you put after a SELECT statement.
The next line starts with FROM which is not followed by a table name but by a complex expression, similar to an SQL WHERE clause. Here you can filter on many things, like tags in files, file names, path names, etc. In the background, this command already produces a result set which will be our initial set for further data manipulation by 'data commands' on subsequent lines.
You can have as many following lines as you want. Each will start with a data command and will re-shape the result set it received from the previous line. For example:
  * The WHERE data command will only keep those lines from the result set which match a given condition. This means that, unless all data in the result set matches the condition, this command will pass on a smaller result set to the next line than it received from the previous line. Unlike in SQL, you can have as many WHERE commands as you like.
  * The FLATTEN data command is not found in common SQL but in DQL you can use it to reduce the depth of the result set.
  * DQL, similarly to SQL, has a GROUP BY command but this can also be used multiple times, which is not possible in common SQL. You can even do several SORT or GROUP BY commands one after the other.





================================================================================

## 15. Reference > Functions





# Functions
Dataview functions provide more advanced ways to manipulate data. You can use functions **indata commands** (except FROM) to filter or group or use them **asadditional information** like TABLE columns or extra output for LIST queries to see your data in a new light.
## How functions work
Functions are another form of expression and can be used everywhere you can use an expression. A function always gives you back a new value and follows this format:
```
functionname(parameter1, parameter2)

```

Parameters are again expressions and you can use literals, meta data fields, or even another function as parameter. You'll find out which data type your parameters need to have on the documentation of this page. Pay attention to the information inside the function brackets. Parameters in square brackets, i.e. `link(path, [display])` means they are _optional_ and can be omitted. Find out more about the default behavior of each function on their explanation.
## Calling functions on lists of values
Most functions can be applied either to single values (like `number`, `string`, `date`, etc.) OR to lists of those values. If a function is applied to a list, it also returns a list after the function is applied to each element in the list. For example:
```
lower("YES")="yes"
lower(["YES","NO"])=["yes","no"]
replace("yes","e","a")="yas"
replace(["yes","ree"],"e","a")=["yas","raa"]

```

This so-called "function vectorization" will not be mentioned explicitly on the following definitions and is possible for a wide range of these functionalities implicitly.
## Constructors
Constructors which create values.
### `object(key1, value1, ...)`
Creates a new object with the given keys and values. Keys and values should alternate in the call, and keys should always be strings/text.
```
object()=>emptyobject
object("a",6)=>objectwhichmaps"a"to6
object("a",4,"c","yes")=>objectwhichmapsato4,andcto"yes"

```

### `list(value1, value2, ...)`
Creates a new list with the given values in it. `array` can be used an alias for `list`.
```
list()=>emptylist
list(1,2,3)=>listwith1,2,and3
array("a","b","c")=>listwith"a","b",and"c"

```

### `date(any)`
Parses a date from the provided string, date, or link object, if possible, returning null otherwise.
```
date("2020-04-18")=<dateobjectrepresentingApril18th,2020>
date([[2021-04-16]])=<dateobjectforthegivenpage,referringtofile.day>

```

### `date(text, format)`
Parses a date from text to luxon `DateTime` with the specified format. Note localized formats might not work. Uses Luxon tokens.
```
date("12/31/2022","MM/dd/yyyy")=>DateTimeforDecember31th,2022
date("210313","yyMMdd")=>DateTimeforMarch13th,2021
date("946778645000","x")=>DateTimefor"2000-01-02T03:04:05"

```

### `dur(any)`
Parses a duration from the provided string or duration, returning null on failure.
```
dur(8minutes)=<8minutes>
dur("8 minutes, 4 seconds")=<8minutes,4seconds>
dur(dur(8minutes))=dur(8minutes)=<8minutes>

```

### `number(string)`
Pulls the first number out of the given string, returning it if possible. Returns null if there are no numbers in the string.
```
number("18 years")=18
number(34)=34
number("hmm")=null

```

### `string(any)`
Converts any value into a "reasonable" string representation. This sometimes produces less pretty results than just directly using the value in a query - it is mostly useful for coercing dates, durations, numbers, and so on into strings for manipulation.
```
string(18)="18"
string(dur(8hours))="8 hours"
string(date(2021-08-15))="August 15th, 2021"

```

### `link(path, [display])`
Construct a link object from the given file path or name. If provided with two arguments, the second argument is the display name for the link.
```
link("Hello")=>linktopagenamed'Hello'
link("Hello","Goodbye")=>linktopagenamed'Hello',displaysas'Goodbye'

```

### `embed(link, [embed?])`
Convert a link object into an embedded link; support for embedded links is somewhat spotty in Dataview views, though embedding of images should work.
```
embed(link("Hello.png"))=>embeddedlinktothe"Hello.png"image,whichwillrenderasanactualimage.

```

### `elink(url, [display])`
Construct a link to an external url (like `www.google.com`). If provided with two arguments, the second argument is the display name for the link.
```
elink("www.google.com")=>linkelementtogoogle.com
elink("www.google.com","Google")=>linkelementtogoogle.com,displaysas"Google"

```

### `typeof(any)`
Get the type of any object for inspection. Can be used in conjunction with other operators to change behavior based on type.
```
typeof(8)=>"number"
typeof("text")=>"string"
typeof([1,2,3])=>"array"
typeof({a:1,b:2})=>"object"
typeof(date(2020-01-01))=>"date"
typeof(dur(8minutes))=>"duration"

```

## Numeric Operations
### `round(number, [digits])`
Round a number to a given number of digits. If the second argument is not specified, rounds to the nearest whole number; otherwise, rounds to the given number of digits.
```
round(16.555555)=17
round(16.555555,2)=16.56

```

### `trunc(number)`
Truncates ("cuts off") the decimal point from a number.
```
trunc(12.937)=12
trunc(-93.33333)=-93
trunc(-0.837764)=0

```

### `floor(number)`
Always rounds down and returns the largest integer less than or equal to a given number. This means that negative numbers become more negative.
```
floor(12.937)=12
floor(-93.33333)=-94
floor(-0.837764)=-1

```

### `ceil(number)`
Always rounds up and returns the smallest integer greater than or equal to a given number. This means negative numbers become less negative.
```
ceil(12.937)=13
ceil(-93.33333)=-93
ceil(-0.837764)=0

```

### `min(a, b, ..)`
Compute the minimum value of a list of arguments, or an array.
```
min(1,2,3)=1
min([1,2,3])=1
min("a","ab","abc")="a"

```

### `max(a, b, ...)`
Compute the maximum value of a list of arguments, or an array.
```
max(1,2,3)=3
max([1,2,3])=3
max("a","ab","abc")="abc"

```

### `sum(array)`
Sums all numeric values in the array. If you have null values in your sum, you can eliminate them via the `nonnull` function.
```
sum([1,2,3])=6
sum([])=null
sum(nonnull([null,1,8]))=9

```

### `product(array)`
Calculates the product of a list of numbers. If you have null values in your average, you can eliminate them via the `nonnull` function.
```
product([1,2,3])=6
product([])=null
product(nonnull([null,1,2,4]))=8

```

### `reduce(array, operand)`
A generic function to reduce a list into a single value, valid operands are `"+"`, `"-"`, `"*"`, `"/"` and the boolean operands `"&"` and `"|"`. Note that using `"+"` and `"*"` equals the `sum()` and `product()` functions, and using `"&"` and `"|"` matches `all()` and `any()`.
```
reduce([100,20,3],"-")=77
reduce([200,10,2],"/")=10
reduce(values,"*")=Multiplieseveryelementofvalues,sameasproduct(values)
reduce(values,this.operand)=Appliesthelocalfieldoperandtoeachofthevalues
reduce(["⭐",3],"*")="⭐⭐⭐",sameas"⭐"*3
reduce([1]),"+")=1,hasthesideeffectofreducingthelistintoasingleelement

```

### `average(array)`
Computes the numeric average of numeric values. If you have null values in your average, you can eliminate them via the `nonnull` function.
```
average([1,2,3])=2
average([])=null
average(nonnull([null,1,2]))=1.5

```

### `minby(array, function)`
Compute the minimum value of an array, using the provided function.
```
minby([1,2,3],(k)=>k)=1
minby([1,2,3],(k)=>0-k)=>3
minby(this.file.tasks,(k)=>k.due)=>(earliestdue)

```

### `maxby(array, function)`
Compute the maximum value of an array, using the provided function.
```
maxby([1,2,3],(k)=>k)=3
maxby([1,2,3],(k)=>0-k)=>1
maxby(this.file.tasks,(k)=>k.due)=>(latestdue)

```

--
## Objects, Arrays, and String Operations
Operations that manipulate values inside of container objects.
### `contains()` and friends
For a quick summary, here are some examples:
```
contains("Hello","Lo")=false
contains("Hello","lo")=true
icontains("Hello","Lo")=true
icontains("Hello","lo")=true
econtains("Hello","Lo")=false
econtains("Hello","lo")=true
econtains(["this","is","example"],"ex")=false
econtains(["this","is","example"],"is")=true

```

#### `contains(object|list|string, value)`
Checks if the given container type has the given value in it. This function behave slightly differently based on whether the first argument is an object, a list, or a string. This function is case-sensitive.
  * For objects, checks if the object has a key with the given name. For example, 
```
contains(file, "ctime") = true
contains(file, "day") = true (if file has a date in its title, false otherwise)

```

  * For lists, checks if any of the array elements equals the given value. For example, 
```
contains(list(1, 2, 3), 3) = true
contains(list(), 1) = false

```

  * For strings, checks if the given value is a substring (i.e., inside) the string. 
```
contains("hello", "lo") = true
contains("yes", "no") = false

```



#### `icontains(object|list|string, value)`
Case insensitive version of `contains()`.
#### `econtains(object|list|string, value)`
"Exact contains" checks if the exact match is found in the string/list. This function is case sensitive.
  * For strings, it behaves exactly like `contains()`. 
```
econtains("Hello", "Lo") = false
econtains("Hello", "lo") = true

```

  * For lists, it checks if the exact word is in the list. 
```
econtains(["These", "are", "words"], "word") = false
econtains(["These", "are", "words"], "words") = true

```

  * For objects, it checks if the exact key name is present in the object. It does **not** do recursive checks. 
```
econtains({key:"value", pairs:"here"}, "here") = false
econtains({key:"value", pairs:"here"}, "key") = true
econtains({key:"value", recur:{recurkey: "val"}}, "value") = false
econtains({key:"value", recur:{recurkey: "val"}}, "Recur") = false
econtains({key:"value", recur:{recurkey: "val"}}, "recurkey") = false

```



### `containsword(list|string, value)`
Checks if `value` has an exact word match in `string` or `list`. This is case insensitive. The outputs are different for different types of input, see examples.
  * For strings, it checks if the word is present in the given string. 
```
containsword("word", "word") = true
containsword("word", "Word") = true
containsword("words", "Word") = false
containsword("Hello there!", "hello") = true
containsword("Hello there!", "HeLLo") = true
containsword("Hello there chaps!", "chap") = false
containsword("Hello there chaps!", "chaps") = true

```

  * For lists, it returns a list of booleans indicating if the word's exact case insensitive match was found. 
```
containsword(["I have no words.", "words"], "Word") = [false, false]
containsword(["word", "Words"], "Word") = [true, false]
containsword(["Word", "Words in word"], "WORD") = [true, true]

```



### `extract(object, key1, key2, ...)`
Pulls multiple fields out of an object, creating a new object with just those fields.
```
extract(file, "ctime", "mtime") = object("ctime", file.ctime, "mtime", file.mtime)
extract(object("test", 1)) = object()

```

### `sort(list)`
Sorts a list, returning a new list in sorted order.
```
sort(list(3, 2, 1)) = list(1, 2, 3)
sort(list("a", "b", "aa")) = list("a", "aa", "b")

```

### `reverse(list)`
Reverses a list, returning a new list in reversed order.
```
reverse(list(1, 2, 3)) = list(3, 2, 1)
reverse(list("a", "b", "c")) = list("c", "b", "a")

```

### `length(object|array)`
Returns the number of fields in an object, or the number of entries in an array.
```
length([]) = 0
length([1, 2, 3]) = 3
length(object("hello", 1, "goodbye", 2)) = 2

```

### `nonnull(array)`
Return a new array with all null values removed.
```
nonnull([]) = []
nonnull([null, false]) = [false]
nonnull([1, 2, 3]) = [1, 2, 3]

```

### `firstvalue(array)`
Return the first non-null value from the array, as a single element. This can be used to pick the first defined field in the children of a task/list item, like in `firstvalue(children.myField)`.
```
firstvalue([null,1,2])=>1
firstvalue(children.myField)=>Ifchildren.myFieldequals[null,null,"myValue",null],itwouldreturn"myValue"

```

### `all(array)`
Returns `true` only if ALL values in the array are truthy. You can also pass multiple arguments to this function, in which case it returns `true` only if all arguments are truthy.
```
all([1, 2, 3]) = true
all([true, false]) = false
all(true, false) = false
all(true, true, true) = true

```

You can pass a function as second argument to return only true if all elements in the array matches the predicate.
```
all([1, 2, 3], (x) => x > 0) = true
all([1, 2, 3], (x) => x > 1) = false
all(["apple", "pie", 3], (x) => typeof(x) = "string") = false

```

### `any(array)`
Returns `true` if ANY of the values in the array are truthy. You can also pass multiple arguments to this function, in which case it returns `true` if any of the arguments are truthy.
```
any(list(1, 2, 3)) = true
any(list(true, false)) = true
any(list(false, false, false)) = false
any(true, false) = true
any(false, false) = false

```

You can pass a function as second argument to return only true if any element in the array matches the predicate.
```
any(list(1, 2, 3), (x) => x > 2) = true
any(list(1, 2, 3), (x) => x = 0) = false

```

### `none(array)`
Returns `true` if NONE of the values in the array are truthy.
```
none([]) = true
none([false, false]) = true
none([false, true]) = false
none([1, 2, 3]) = false

```

You can pass a function as second argument to return only true if none of the elements in the array matches the predicate.
```
none([1, 2, 3], (x) => x = 0) = true
none([true, true], (x) => x = false) = true
none(["Apple", "Pi", "Banana"], (x) => startswith(x, "A")) = false

```

### `join(array, [delimiter])`
Joins elements in an array into a single string (i.e., rendering them all on the same line). If provided with a second argument, then each element will be separated by the given separator.
```
join(list(1, 2, 3)) = "1, 2, 3"
join(list(1, 2, 3), " ") = "1 2 3"
join(6) = "6"
join(list()) = ""

```

### `filter(array, predicate)`
Filters elements in an array according to the predicate, returning a new list of the elements which matched.
```
filter([1,2,3],(x)=>x>=2)=[2,3]
filter(["yes","no","yas"],(x)=>startswith(x,"y"))=["yes","yas"]

```

### `unique(array)`
Creates a new array with only unique values. 
```
unique([1,3,7,3,1])=>[1,3,7]

```

### `map(array, func)`
Applies the function to each element in the array, returning a list of the mapped results.
```
map([1,2,3],(x)=>x+2)=[3,4,5]
map(["yes","no"],(x)=>x+"?")=["yes?","no?"]

```

### `flat(array, [depth])`
Concatenates sub-levels of the array to the desired depth. Default is 1 level, but it can concatenate multiple levels. E.g. Can be used to reduce array depth on `rows` lists after doing `GROUP BY`.
```
flat(list(1,2,3,list(4,5),6))=>list(1,2,3,4,5,6)
flat(list(1,list(21,22),list(list(311,312,313))),4)=>list(1,21,22,311,312,313)
flat(rows.file.outlinks))=>Allthefileoutlinksatfirstlevelinoutput

```

### `slice(array, [start, [end]])`
Returns a shallow copy of a portion of an array into a new array object selected from `start` to `end` (`end` not included) where `start` and `end` represents the index of items in that array.
```
slice([1,2,3,4,5],3)=[4,5]=>Allitemsfromgivenposition,0asfirst
slice(["ant","bison","camel","duck","elephant"],0,2)=["ant","bison"]=>Firsttwoitems
slice([1,2,3,4,5],-2)=[4,5]=>countsfromtheend,lasttwoitems
slice(someArray)=>acopyofsomeArray

```

## String Operations
### `regextest(pattern, string)`
Checks if the given regex pattern can be found in the string (using the JavaScript regex engine).
```
regextest("\w+","hello")=true
regextest(".","a")=true
regextest("yes|no","maybe")=false
regextest("what","what's up dog?")=true

```

### `regexmatch(pattern, string)`
Checks if the given regex pattern matches the _entire_ string, using the JavaScript regex engine. This differs from `regextest` in that regextest can match just parts of the text.
```
regexmatch("\w+","hello")=true
regexmatch(".","a")=true
regexmatch("yes|no","maybe")=false
regexmatch("what","what's up dog?")=false

```

### `regexreplace(string, pattern, replacement)`
Replaces all instances where the _regex_ `pattern` matches in `string`, with `replacement`. This uses the JavaScript replace method under the hood, so you can use special characters like `$1` to refer to the first capture group, and so on.
```
regexreplace("yes","[ys]","a")="aea"
regexreplace("Suite 1000","\d+","-")="Suite -"

```

### `replace(string, pattern, replacement)`
Replace all instances of `pattern` in `string` with `replacement`.
```
replace("what","wh","h")="hat"
replace("The big dog chased the big cat.","big","small")="The small dog chased the small cat."
replace("test","test","no")="no"

```

### `lower(string)`
Convert a string to all lower case.
```
lower("Test")="test"
lower("TEST")="test"

```

### `upper(string)`
Convert a string to all upper case.
```
upper("Test")="TEST"
upper("test")="TEST"

```

### `split(string, delimiter, [limit])`
Split a string on the given delimiter string. If a third argument is provided, it limits the number of splits that occur. The delimiter string is interpreted as a regular expression. If there are capture groups in the delimiter, matches are spliced into the result array, and non-matching captures are empty strings.
```
split("hello world"," ")=list("hello","world")
split("hello world","\s")=list("hello","world")
split("hello there world"," ",2)=list("hello","there")
split("hello there world","(t?here)")=list("hello ","there"," world")
split("hello there world","( )(x)?")=list("hello"," ","","there"," ","","world")

```

### `startswith(string, prefix)`
Checks if a string starts with the given prefix.
```
startswith("yes","ye")=true
startswith("path/to/something","path/")=true
startswith("yes","no")=false

```

### `endswith(string, suffix)`
Checks if a string ends with the given suffix.
```
endswith("yes","es")=true
endswith("path/to/something","something")=true
endswith("yes","ye")=false

```

### `padleft(string, length, [padding])`
Pads a string up to the desired length by adding padding on the left side. If you omit the padding character, spaces will be used by default.
```
padleft("hello",7)=" hello"
padleft("yes",5,"!")="!!yes"

```

### `padright(string, length, [padding])`
Equivalent to `padleft`, but pads to the right instead.
```
padright("hello",7)="hello "
padright("yes",5,"!")="yes!!"

```

### `substring(string, start, [end])`
Take a slice of a string, starting at `start` and ending at `end` (or the end of the string if unspecified).
```
substring("hello",0,2)="he"
substring("hello",2,4)="ll"
substring("hello",2)="llo"
substring("hello",0)="hello"

```

### `truncate(string, length, [suffix])`
Truncate a string to be at most the given length, including the `suffix` (which defaults to `...`). Generally useful to cut off long text in tables.
```
truncate("Hello there!",8)="Hello..."
truncate("Hello there!",8,"/")="Hello t/"
truncate("Hello there!",10)="Hello t..."
truncate("Hello there!",10,"!")="Hello the!"
truncate("Hello there!",20)="Hello there!"

```

## Utility Functions
### `default(field, value)`
If `field` is null, return `value`; otherwise return `field`. Useful for replacing null values with defaults. For example, to show projects which haven't been completed yet, use `"incomplete"` as their default value:
```
default(dateCompleted,"incomplete")

```

Default is vectorized in both arguments; if you need to use default explicitly on a list argument, use `ldefault`, which is the same as default but is not vectorized.
```
default(list(1,2,null),3)=list(1,2,3)
ldefault(list(1,2,null),3)=list(1,2,null)

```

### `display()`
Display function converts the input into a string representation while trying to preserve the display property of data types. This means that links and urls will be replaced by their display value.
```
display("Hello World")="Hello World"
display("**Hello** World")="Hello World"
display("Hello [[World]]")="Hello World"
display(link("path/to/file.md"))="file"
display(link("path/to/file.md","displayname"))="displayname"
display(date("2024-11-18"))="November 18, 2024"
display(list("Hello","World"))="Hello, World"

```

### `choice(bool, left, right)`
A primitive if statement - if the first argument is truthy, returns left; otherwise, returns right.
```
choice(true,"yes","no")="yes"
choice(false,"yes","no")="no"
choice(x>4,y,z)=yifx>4,elsez

```

### `hash(seed, [text], [variant])`
Generate a hash based on the `seed`, and the optional extra `text` or a variant `number`. The function generates a fixed number based on the combination of these parameters, which can be used to randomize the sort order of files or lists/tasks. If you choose a `seed` based on a date, i.e. "2024-03-17", or another timestamp, i.e. "2024-03-17 19:13", you can make the "randomness" be fixed related to that timestamp. `variant` is a number, which in some cases is needed to make the combination of `text` and `variant` become unique.
```
hash(dateformat(date(today),"YYYY-MM-DD"),file.name)=...Auniquevalueforagivendateintime
hash(dateformat(date(today),"YYYY-MM-DD"),file.name,position.start.line)=...Aunique"random"valueinaTASKquery

```

This function can be used in a `SORT` statement to randomize the order. If you're using a `TASK` query, since the file name could be the same for multiple tasks, you can add some number like the starting line number (as shown above) to make it a unique combination. If using something like `FLATTEN file.lists as item`, the similar addition would be to do `item.position.start.line` as the last parameter.
### `striptime(date)`
Strip the time component of a date, leaving only the year, month, and day. Good for date comparisons if you don't care about the time.
```
striptime(file.ctime)=file.cday
striptime(file.mtime)=file.mday

```

### `dateformat(date|datetime, string)`
Format a Dataview date using a formatting string. Uses Luxon tokens.
```
dateformat(file.ctime,"yyyy-MM-dd")="2022-01-05"
dateformat(file.ctime,"HH:mm:ss")="12:18:04"
dateformat(date(now),"x")="1407287224054"
dateformat(file.mtime,"ffff")="Wednesday, August 6, 2014, 1:07 PM Eastern Daylight Time"

```

**Note:** `dateformat()` returns a string, not a date, so you can't compare it against the result from a call to `date()` or a variable like `file.day` which already is a date. To make those comparisons you can format both arguments.
### `durationformat(duration, string)`
Format a Dataview duration using a formatting string. Anything inside single quotes will not be treated as a token and instead will be shown in the output as written. See examples.
You may use these tokens:
  * `S` for milliseconds
  * `s` for seconds
  * `m` for minutes
  * `h` for hours
  * `d` for days
  * `w` for weeks
  * `M` for months
  * `y` for years


```
durationformat(dur("3 days 7 hours 43 seconds"),"ddd'd' hh'h' ss's'")="003d 07h 43s"
durationformat(dur("365 days 5 hours 49 minutes"),"yyyy ddd hh mm ss")="0001 000 05 49 00"
durationformat(dur("2000 years"),"M months")="24000 months"
durationformat(dur("14d"),"s 'seconds'")="1209600 seconds"

```

### `currencyformat(number, [currency])`
Presents the number depending on your current locale, according to the `currency` code, from ISO 4217.
```
number = 123456.789
currencyformat(number, "EUR") = €123,456.79 in locale: en_US)
currencyformat(number, "EUR") = 123.456,79 € in locale: de_DE)
currencyformat(number, "EUR") = € 123 456,79 in locale: nb)

```

### `localtime(date)`
Converts a date in a fixed timezone to a date in the current timezone.
### `meta(link)`
Get an object containing metadata of a link. When you access a property on a link what you get back is the property value from the linked file. The `meta` function makes it possible to access properties of the link itself.
There are several properties on the object returned by `meta`:
#### `meta(link).display`
Get the display text of a link, or null if the link does not have defined display text.
```
meta([[2021-11-01|Displayedlinktext]]).display="Displayed link text"
meta([[2021-11-01]]).display=null

```

#### `meta(link).embed`
True or false depending on whether the link is an embed. Those are links that begin with an exclamation mark, like `![[Some Link]]`.
#### `meta(link).path`
Get the path portion of a link.
```
meta([[MyProject]]).path="My Project"
meta([[MyProject#NextActions]]).path="My Project"
meta([[MyProject#^9bcbe8]]).path="My Project"

```

#### `meta(link).subpath`
Get the subpath of a link. For links to a heading within a file the subpath will be the text of the heading. For links to a block the subpath will be the block ID. If neither of those cases applies then the subpath will be null.
```
meta([[MyProject#NextActions]]).subpath="Next Actions"
meta([[MyProject#^9bcbe8]]).subpath="9bcbe8"
meta([[MyProject]]).subpath=null

```

This can be used to select tasks under specific headings.
```
```dataview
task
where meta(section).subpath = "Next Actions"
```

```

#### `meta(link).type`
Has the value "file", "header", or "block" depending on whether the link links to an entire file, a heading within a file, or to a block within a file.
```
meta([[MyProject]]).type="file"
meta([[MyProject#NextActions]]).type="header"
meta([[MyProject#^9bcbe8]]).type="block"

```




================================================================================

## 16. Resources > Examples




# Examples
A small collection of simple usages of the dataview query language.
Show all games in the games folder, sorted by rating, with some metadata:
Query
```
TABLE
time-playedAS"Time Played",
lengthAS"Length",
ratingAS"Rating"
FROM"games"
SORTratingDESC

```

Output
File | Time Played | Length | Rating  
---|---|---|---  
Outer Wilds | November 19th - 21st, 2020 | 15h | 9.5  
Minecraft | All the time. | 2000h | 9.5  
Pillars of Eternity 2 | August - October 2019 | 100h | 9  
List games which are MOBAs or CRPGs.
Query
```
LISTFROM#games/mobasOR#games/crpg

```

Output
  * League of Legends
  * Pillars of Eternity 2


List all tasks in un-completed projects:
Query
```
TASKFROM"dataview"

```

Output
dataview/Project A
  * I am a task.
  * I am another task.


dataview/Project A
  * I could be a task, though who knows.
    * Determine if this is a task.
  * I'm a finished task.


List all of the files in the `books` folder, sorted by the last time you modified the file:
Query
```
TABLEfile.mtimeAS"Last Modified"
FROM"books"
SORTfile.mtimeDESC

```

Output
File | Last Modified  
---|---  
Atomic Habits | 11:06 PM - August 07, 2021  
Can't Hurt Me | 10:58 PM - August 07, 2021  
Deep Work | 10:52 PM - August 07, 2021  
List all files which have a date in their title (of the form `yyyy-mm-dd`), and list them by date order.
Query
```
LISTfile.dayWHEREfile.day
SORTfile.dayDESC

```

Output
  * 2021-08-07: August 07, 2021
  * 2020-08-10: August 10, 2020





================================================================================

## 17. Queries > Structure





# Structure of a Query
Dataview offers multiple ways to write queries and the syntax differs for each.
This page provides information on how to write a **Dataview Query Language** (**DQL**) query. If you're interested in how to write Inline Queries, refer to the inline section on DQL, JS and Inlines. You'll find more information about **Javascript Queries** on the Javascript Reference.
**DQL** is a SQL like query language for creating different views or calculations on your data. It supports:
  * Choosing an **output format** of your output (the Query Type)
  * Fetch pages **from a certainsource**, i.e. a tag, folder or link
  * **Filtering pages/data** by simple operations on fields, like comparison, existence checks, and so on
  * **Transforming fields** for displaying, i.e. with calculations or splitting up multi-value fields
  * **Sorting** results based on fields
  * **Grouping** results based on fields
  * **Limiting** your result count


Warning
If you are familiar with SQL, please read Differences to SQL to avoid confusing DQL with SQL.
Let's have a look at how we can put DQL to use.
## General Format of a DQL Query
Every query follows the same structure and consists of
  * exactly one **Query Type** with zero, one or many fields, depending on query type
  * zero or one **FROM** data commands with one to many sources
  * zero to many other **data commands** with one to many expressions and/or other infos depending on the data command


At a high level, a query conforms to the following pattern:
```
```dataview
<QUERY-TYPE> <fields>
FROM <source>
<DATA-COMMAND> <expression>
<DATA-COMMAND> <expression>
     ...
```

```

Only the Query Type is mandatory.
The following sections will explain the theory in further detail.
## Choose a Output Format
The output format of a query is determined by its **Query Type**. There are four available:
  1. **TABLE** : A table of results with one row per result and one or many columns of field data.
  2. **LIST** : A bullet point list of pages which match the query. You can output one field for each page alongside their file links.
  3. **TASK** : An interactive task list of tasks that match the given query.
  4. **CALENDAR** : A calendar view displaying each hit via a dot on its referred date.


The Query Type is the **only mandatory command in a query**. Everything else is optional.
Possibly memory intense examples
Depending on the size of your vault, executing the following examples can take long and even freeze Obsidian in extreme cases. It's recommended that you specify a `FROM` to restrict the query execution to a specific subset of your vaults' files. See next section.
```
Lists all pages in your vault as a bullet point list
```dataview
LIST
```
Lists all tasks (completed or not) in your vault
```dataview
TASK
```
Renders a Calendar view where each page is represented as a dot on its creation date.
```dataview
CALENDAR file.cday
```
Shows a table with all pages of your vault, their field value of due, the files' tags and an average of the values of multi-value field working-hours
```dataview
TABLE due, file.tags AS "tags", average(working-hours)
```

```

Read more about the available Query Types and how to use them here.
## Choose your source
Additionally to the Query Types, you have several **Data Commands** available that help you restrict, refine, sort or group your query. One of these query commands is the **FROM** statement. `FROM` takes a source or a combination of sources as an argument and restricts the query to a set of pages that match your source.
It behaves differently from the other Data Commands: You can add **zero or one** `FROM` data command to your query, right after your Query Type. You cannot add multiple FROM statements and you cannot add it after other Data Commands.
```
Lists all pages inside the folder Books and its sub folders
```dataview
LIST
FROM "Books"
```
Lists all pages that include the tag #status/open or #status/wip
```dataview
LIST
FROM #status/open OR #status/wip
```
Lists all pages that have either the tag #assignment and are inside folder "30 School" (or its sub folders), or are inside folder "30 School/32 Homeworks" and are linked on the page School Dashboard Current To Dos
```dataview
LIST
FROM (#assignment AND "30 School") OR ("30 School/32 Homeworks" AND outgoing([[School Dashboard Current To Dos]]))
```

```

Read more about `FROM` here.
## Filter, sort, group or limit results
In addition to the Query Types and the **Data command** `FROM` that's explained above, you have several other **Data Commands** available that help you restrict, refine, sort or group your query results.
All data commands except the `FROM` command can be used **multiple times in any order** (as long as they come after the Query Type and `FROM`, if `FROM` is used at all). They'll be executed in the order they are written.
Available are:
  1. **FROM** like explained above.
  2. **WHERE** : Filter notes based on information **inside** notes, the meta data fields.
  3. **SORT** : Sorts your results depending on a field and a direction.
  4. **GROUP BY** : Bundles up several results into one result row per group.
  5. **LIMIT** : Limits the result count of your query to the given number.
  6. **FLATTEN** : Splits up one result into multiple results based on a field or calculation.


```
Lists all pages that have a metadata field `due` and where `due` is before today
```dataview
LIST
WHERE due AND due < date(today)
```
Lists the 10 most recently created pages in your vault that have the tag #status/open
```dataview
LIST
FROM #status/open
SORT file.ctime DESC
LIMIT 10
```
Lists the 10 oldest and incomplete tasks of your vault as an interactive task list, grouped by their containing file and sorted from oldest to newest file.
```dataview
TASK
WHERE !completed
SORT created ASC
LIMIT 10
GROUP BY file.link
SORT rows.file.ctime ASC
```

```

Find out more about available data commands.
## Examples
Following are some example queries. Find more examples here.
```
```dataview
TASK
```

```

```
```dataview
TABLE recipe-type AS "type", portions, length
FROM #recipes
```

```

```
```dataview
LIST
FROM #assignments
WHERE status = "open"
```

```

```
```dataview
TABLE file.ctime, appointment.type, appointment.time, follow-ups
FROM "30 Protocols/32 Management"
WHERE follow-ups
SORT appointment.time
```

```

```
```dataview
TABLE L.text AS "My lists"
FROM "dailys"
FLATTEN file.lists AS L
WHERE contains(L.author, "Surname")
```

```

```
```dataview
LIST rows.c
WHERE typeof(contacts) = "array" AND contains(contacts, [[Mr. L]])
SORT length(contacts)
FLATTEN contacts as c
SORT link(c).age ASC
```

```




================================================================================

## 18. Resources > Develop Against Dataview





# Developing Against Dataview
Dataview includes a high-level plugin-facing API as well as TypeScript definitions and a utility library; to install it, simply use:
```
npminstall-Dobsidian-dataview

```

To verify that it is the correct version installed, do `npm list obsidian-dataview`. If that fails to report the latest version, which currently is 0.5.64, you can do:
```
npminstallobsidian-dataview@0.5.64

```

**Note** : If Git is not already installed on your local system, you will need to install it first. You may need to restart your device to complete the Git installation before you can install the Dataview API.
##### Accessing the Dataview API
You can use the `getAPI()` function to obtain the Dataview Plugin API; this returns a `DataviewApi` object which provides various utilities, including rendering dataviews, checking dataview's version, hooking into the dataview event life cycle, and querying dataview metadata.
```
import{getAPI}from"obsidian-dataview";
constapi=getAPI();

```

For full API definitions available, check index.ts or the plugin API definition plugin-api.ts.
##### Binding to Dataview Events
You can bind to dataview metadata events, which fire on all file updates and changes, via:
```
plugin.registerEvent(plugin.app.metadataCache.on("dataview:index-ready",()=>{
...
});
plugin.registerEvent(plugin.app.metadataCache.on("dataview:metadata-change",
(type,file,oldPath?)=>{...}));

```

For all events hooked on MetadataCache, check index.ts.
##### Value Utilities
You can access various type utilities which let you check the types of objects and compare them via `Values`:
```
import{getAPI,Values}from"obsidian-dataview";
constfield=getAPI(plugin.app)?.page('sample.md').field;
if(!field)return;
if(Values.isHtml(field))// do something
elseif(Values.isLink(field))// do something
// ...

```




================================================================================

## 19. Reference > Sources





# Sources
A dataview **source** is something that identifies a set of files, tasks, or other data. Sources are indexed internally by Dataview, so they are fast to query. The most prominent use of sources is the FROM data command. They are also used in various JavaScript API query calls.
## Types of Sources
Dataview currently supports **four source types**.
### Tags
Sources of the form `#tag`. These match all files / sections / tasks with the given tag.
```
```dataview
LIST
FROM #homework
```

```

### Folders
Sources of the form `"folder"`. These match all files / sections / tasks contained in the given folder and its sub folders. The full vault path is expected instead of just the folder name. Note that trailing slashes are not supported, i.e. `"Path/To/Folder/"` will not work but `"Path/To/Folder"` will.
```
```dataview
TABLE file.ctime, status
FROM "projects/brainstorming"
```

```

### Specific Files
You can select from a specific file by specifying it's full path: `"folder/File"`.
  * If you have both a file and a folder with the exact same path, Dataview will prefer the folder. You can force it to read from the file by specifying an extension: `folder/File.md`.


```
```dataview
LIST WITHOUT ID next-in-line
FROM "30 Hobbies/Games/Dashboard"
```

```

### Links
You can either select links **to** a file, or all links **from** a file.
  * To obtain all pages which link **to** `[[note]]`, use `[[note]]`.
  * To obtain all pages which link **from** `[[note]]` (i.e., all the links in that file), use `outgoing([[note]])`.
  * You can implicitly reference the current file via `[[#]]` or `[[]]`, i.e. `[[]]` lets you query from all files linking to the current file.


```
```dataview
LIST
FROM [[]]
```
```dataview
LIST
FROM outgoing([[Dashboard]])
```

```

## Combining Sources
You can compose these filters in order to get more advanced sources using `and` and `or`.
  * For example, `#tag and "folder"` will return all pages in `folder` and with `#tag`.
  * Querying from `#food and !#fastfood` will only return pages that contain `#food` but does not contain `#fastfood`.
  * `[[Food]] or [[Exercise]]` will give any pages which link to `[[Food]]` OR `[[Exercise]]`.


If you have complex queries where grouping or precedence matters, you can use parenthesis to logically group them:
  * `#tag and ("folder" or #other-tag)`
  * `(#tag1 or #tag2) and (#tag3 or #tag4)`





================================================================================

## 20. Queries > Dql Js Inline





# DQL, JS and Inlines
Once you've added useful data to relevant pages, you'll want to actually display it somewhere or operate on it. Dataview allows this in four different ways, all of which are written in codeblocks directly in your Markdown and live-reloaded when your vault changes.
## Dataview Query Language (DQL)
The **Dataview Query Language** (for short **DQL**) is a SQL-like language and Dataviews core functionality. It supports four Query Types to produce different outputs, data commands to refine, resort or group your result and plentiful functions which allow numerous operations and adjustments to achieve your wanted output.
Warning
If you are familiar with SQL, please read Differences to SQL to avoid confusing DQL with SQL.
You create a **DQL** query with a codeblock that uses `dataview` as type:
```
```dataview
TABLE rating AS "Rating", summary AS "Summary" FROM #games
SORT rating DESC
```

```

Use backticks
A valid codeblock needs to use backticks (`) on start and end (three each). Do not confuse the backtick with the similar looking apostrophe ' !
Find a explanation how to write a DQL Query under the query language reference. If you learn better by example, take a look at the query examples.
## Inline DQL
A Inline DQL uses a inline block format instead of a code block and a configurable prefix to mark this inline code block as a DQL block.
```
`= this.file.name`

```

Change of DQL prefix
You can change the `=` to another token (like `dv:` or `~`) in Dataviews' settings under "Codeblock Settings" > "Inline Query Prefix"
Inline DQL Queries display **exactly one value** somewhere in the middle of your note. They seamlessly blend into the content of your note:
```
Today is `= date(today)` - `= [[exams]].deadline - date(today)` until exams!

```

would, for example, render to
```
Today is November 07, 2022 - 2 months, 5 days until exams!

```

**Inline DQL** queries always display exactly one value, not a list (or table) of values. You can access the properties of the **current page** via prefix `this.` or a different page via `[[linkToPage]].`.
```
`= this.file.name`
`= this.file.mtime`
`= this.someMetadataField`
`= [[secondPage]].file.name`
`= [[secondPage]].file.mtime`
`= [[secondPage]].someMetadataField`

```

You can use everything available as expressions and literals in an Inline DQL Query, including functions. Query Types and Data Commands, on the other hand, are **not available in Inlines.**
```
Assignment due in `= this.due - date(today)`
Final paper due in `= [[Computer Science Theory]].due - date(today)`
🏃‍♂️ Goal reached? `= choice(this.steps > 10000, "YES!", "**No**, get moving!")`
You have `= length(filter(link(dateformat(date(today), "yyyy-MM-dd")).file.tasks, (t) => !t.completed))` tasks to do. `= choice(date(today).weekday > 5, "Take it easy!", "Time to get work done!")`

```

## Dataview JS
The dataview JavaScript API gives you the full power of JavaScript and provides a DSL for pulling Dataview data and executing queries, allowing you to create arbitrarily complex queries and views. Similar to the query language, you create Dataview JS blocks via a `dataviewjs`-annotated codeblock:
```
```dataviewjs
letpages=dv.pages("#books and -#books/finished").where(b=>b.rating>=7);
for(letgroupofpages.groupBy(b=>b.genre)){
dv.header(3,group.key);
dv.list(group.rows.file.name);
}
```

```

Inside of a JS dataview block, you have access to the full dataview API via the `dv` variable. For an explanation of what you can do with it, see the API documentation, or the API examples.
Advanced usage
Writing Javascript queries is a advanced technique that requires understanding in programming and JS. Please be aware that JS Queries have access to your file system and be cautious when using other peoples' JS Queries, especially when they are not publicly shared through the Obsidian Community.
## Inline Dataview JS
Similar to the query language, you can write JS inline queries, which let you embed a computed JS value directly. You create JS inline queries via inline code blocks:
```
`$= dv.current().file.mtime`

```

In inline DataviewJS, you have access to the `dv` variable, as in `dataviewjs` codeblocks, and can make all of the same calls. The result should be something which evaluates to a JavaScript value, which Dataview will automatically render appropriately.
Unlike Inline DQL queries, Inline JS queries do have access to everything a Dataview JS Query has available and can hence query and output multiple pages.
Change of Inline JS prefix
You can change the `$=` to another token (like `dvjs:` or `$~`) in Dataviews' settings under "Codeblock Settings" > "Javascript Inline Query Prefix"



================================================================================

## 21. Queries > Query Types





# Query Types
The **Query Type** determines how the output of your dataview query looks like. It is the **first and only mandatory** specification you give to a dataview query. There are four available: `LIST`, `TABLE`, `TASK` and `CALENDAR`.
The Query Type also determines which **information level** a query is executed on. `LIST`, `TABLE` and `CALENDAR` operate at **page level** whereas `TASK` queries operate at the `file.tasks` level. More on that in the `TASK` Query Type.
You can combine **every Query Type with all availableData Commands** to refine your result set. Read more about the interconnection between Query Types and Data Commands on How to Use Dataview and the structure page.
Query Type
The Query Type determines the output format of a query. It's the only mandatory information for a query.
## LIST
`LIST` queries output a bullet point list consisting of your file links or the group name, if you decided to group. You can specify up to **one additional information** to output alongside your file or group information.
Query Type `LIST`
`LIST` outputs a bullet point list of page links or Group keys. You can specify one additional information to show for each result.
The simplest LIST query outputs a bullet point list of all files in your vault:
```
```dataview
LIST
```

```


but you can, of course, use data commands to restrict which pages you want to have listed:
```
```dataview
LIST
FROM #games/mobas OR #games/crpg
```

```


### Output an additional information
To add a **additional information** to your query, specify it right after the `LIST` command and before possibly available data commands:
```
```dataview
LIST file.folder
```

```


You can only add **one** additional information, not multiple. But you can **specify a computed value** instead of a plain meta data field, which can contain information of multiple fields:
```
```dataview
LIST "File Path: " + file.folder + " _(created: " + file.cday + ")_"
FROM "Games"
```

```


### Grouping
A **grouped list** shows their group keys, and only the group keys, by default:
```
```dataview
LIST
GROUP BY type
```

```

**Output**
  * game
  * knowledge
  * moc
  * recipe
  * summary


A common use-case on grouped `LIST` queries is to add the file links to the output by specifying them as the additional information:
```
```dataview
LIST rows.file.link
GROUP BY type
```

```

  * game:
    * Stardew Valley
    * League of Legends
    * Pillars of Eternity 2
  * knowledge:
    * Git Basics
  * moc:
    * Dashboard
  * recipe:
    * Classic Cheesecake
  * summary:
    * How to fix Git Cheatsheet


### LIST WITHOUT ID
If you don't want the file name or group key included in the list view, you can use `LIST WITHOUT ID`. `LIST WITHOUT ID` works the same as `LIST`, but it does not output the file link or group name if you add an additional information.
```
```dataview
LIST WITHOUT ID
```

```


It's the same as `LIST`, because it does not contain an additional information!
```
```dataview
LIST WITHOUT ID type
```

```

**Output**
  * moc
  * recipe
  * summary
  * knowledge
  * game
  * game
  * game


`LIST WITHOUT ID` can be handy if you want to output computed values, for example.
```
```dataview
LIST WITHOUT ID length(rows) + " pages of type " + key
GROUP BY type
```

```

**Output**
  * 3 pages of type game
  * 1 pages of type knowledge
  * 1 pages of type moc
  * 1 pages of type recipe
  * 1 pages of type summary


## TABLE
The `TABLE` query types outputs page data as a tabular view. You can add zero to multiple meta data fields to your `TABLE` query by adding them as a **comma separated list**. You can not only use plain meta data fields as columns, but specify **calculations** as well. Optionally, you can specify a **table header** via the `AS <header>` syntax. Like all other query types, you can refine your result set for your query with data commands.
`TABLE` Query Type
`TABLE` queries render a tabular view of any number of meta data values or calculations. It is possible to specify column headers via `AS <header>`.
```
```dataview
TABLE
```

```

**Output**
File (7)  
---  

Changing the first column header name
You can change the name of the first column header (by default "File" or "Group") via the Dataview Settings under Table Settings -> Primary Column Name / Group Column Name. If you want to change the name only for one specific `TABLE` query, have a look at `TABLE WITHOUT ID`.
Disabling Result count
The first column always shows the result count. If you do not want to get it displayed, you can disable it in Dataview's settings ("Display result count", available since 0.5.52).
Of course, a `TABLE` is made for specifying one to multiple additional information:
```
```dataview
TABLE started, file.folder, file.etags
FROM #games
```

```

**Output**
File (3) | started | file.folder | file.etags  
---|---|---|---  
League of Legends | May 16, 2021 | Games | - #games/moba  
Pillars of Eternity 2 | April 21, 2022 | Games | - #games/crpg  
Stardew Valley | April 04, 2021 | Games/finished | - #games/simulation  
Implicit fields
Curious about `file.folder` and `file.etags`? Learn more about implicit fields on pages.
### Custom Column Headers
You can specify **custom headings** for your columns by using the `AS` syntax:
```
```dataview
TABLE started, file.folder AS Path, file.etags AS "File Tags"
FROM #games
```

```

**Output**
File (3) | started | Path | File Tags  
---|---|---|---  
League of Legends | May 16, 2021 | Games | - #games/moba  
Pillars of Eternity 2 | April 21, 2022 | Games | - #games/crpg  
Stardew Valley | April 04, 2021 | Games/finished | - #games/simulation  
Custom headers with spaces
If you want to use a custom header with spaces, like `File Tags`, you need to wrap it into double quotes: `"File Tags"`.
This is especially useful when you want to use **calculations or expressions as column values** :
```
```dataview
TABLE
default(finished, date(today)) - started AS "Played for",
file.folder AS Path,
file.etags AS "File Tags"
FROM #games
```

```

**Output**
File (3) | Played for | Path | File Tags  
---|---|---|---  
League of Legends | 1 years, 6 months, 1 weeks | Games | - #games/moba  
Pillars of Eternity 2 | 7 months, 2 days | Games | - #games/crpg  
Stardew Valley | 4 months, 3 weeks, 3 days | Games/finished | - #games/simulation  
Calculations and expressions
Learn more about the capability of computing expressions and calculations under expressions and functions.
### TABLE WITHOUT ID
If you don't want the first column ("File" or "Group" by default), you can use `TABLE WITHOUT ID`. `TABLE WITHOUT ID` works the same as `TABLE`, but it does not output the file link or group name as a first column if you add additional information.
You can use this if you, for example, output another identifying value:
```
```dataview
TABLE WITHOUT ID
steamid,
file.etags AS "File Tags"
FROM #games
```

```

**Output**
steamid (3) | File Tags  
---|---  
560130 | - #games/crog  
- | - #games/moba  
413150 | - #games/simulation  
Also, you can use `TABLE WITHOUT ID` if you want to **rename the first column for one specific query**.
```
```dataview
TABLE WITHOUT ID
file.link AS "Game",
file.etags AS "File Tags"
FROM #games
```

```

**Output**
Game (3) | File Tags  
---|---  
League of Legends | - #games/moba  
Pillars of Eternity 2 | - #games/crpg  
Stardew Valley | - #games/simulation  
Renaming the first column in general
If you want to rename the first column in all cases, change the name in Dataviews settings under Table Settings.
## TASK
The `TASK` Query outputs **an interactive list of all tasks in your vault** that match the given data commands (if any). `TASK` queries are special compared to the other Query Types because they do give back **Tasks as results and not pages**. This implies that all data commands operate on **Task level** and makes it possible to granularly filter your tasks i.e. for their status or meta data specified on the task itself.
Also, `TASK` Queries are the only possibility to **manipulate your files through DQL**. Normally, Dataview does not touch the content of your files; however, if you check a task through a dataview query, it'll get **checked in its original file, too**. In the Dataview Settings under "Task Settings", you can opt-in to automatically set a `completion` meta data field when checking a task in dataview. Mind though that this only works if you check the task inside a dataview block.
`TASK` Query Type
`TASK` queries render an interactive list of all tasks in your vault. `TASK` Queries are executed on **task level** , not page level, allowing for task-specific filtering. This is the only command in dataview that modifies your original files if interacted with.
```
```dataview
TASK
```

```

**Output**
  * Buy new shoes #shopping
  * Mail Paul about training schedule
  * Finish the math assignment
    * Finish Paper 1 [due:: 2022-08-13]
    * Read again through chapter 3 [due:: 2022-09-01]
    * Write a cheatsheet [due:: 2022-08-02]
    * Write a summary of chapter 1-4 [due:: 2022-09-12]
  * Hand in physics
  * Get new pillows for mom #shopping
  * Buy some working pencils #shopping


You can use data commands like for all other Query Types. Data Commands are executed on task level, making implicit fields on tasks directly available.
```
```dataview
TASK
WHERE !completed AND contains(tags, "#shopping")
```

```

**Output**
  * Buy new shoes #shopping
  * Get new pillows for mom #shopping


A common use case for tasks is to **group tasks by their originating file** :
```
```dataview
TASK
WHERE !completed
GROUP BY file.link
```

```

**Output**
2022-07-30 (1)
  * Finish the math assignment
    * Read again through chapter 3 [due:: 2022-09-01]
    * Write a summary of chapter 1-4 [due:: 2022-09-12]


2022-09-21 (2)
  * Buy new shoes #shopping
  * Mail Paul about training schedule


2022-09-27 (1)
  * Get new pillows for mom #shopping


Counting tasks with subtask
Noticing the (1) on the header of `2022-07-30`? Child tasks belong to their parent task and are not counted separately. Also, they **behave differently** on filtering.
### Child Tasks
A task is considered a **child task** if it is **indented by a tab** and is below an unindented task.
  * clean up the house
    * kitchen
    * living room
    * Bedroom [urgent:: true]


Children of a bullet point item
While indented tasks under a bulleted list item are, strictly speaking, also child tasks, Dataview will handle them like normal tasks in most cases.
Child Tasks **belong to their parent**. This means if you're querying for tasks, you'll get child tasks as part of their parent back.
```
```dataview
TASK
```

```

**Output**
  * clean up the house
    * kitchen
    * living room
    * Bedroom [urgent:: true]
  * Call the insurance about the car
  * Find out the transaction number


This specifically means that child task will be part of your result set **as long as the parent matches the query** - even if the child task itself doesn't.
```
```dataview
TASK
WHERE !completed
```

```

**Output**
  * clean up the house
    * kitchen
    * living room
    * Bedroom [urgent:: true]
  * Call the insurance about the car


Here, `living room` does **not match** the query, but is included anyway, because its parent `clean up the house` does match.
Mind that you'll get individual children tasks back, if the child matches your predicate but the parent doesn't:
```
```dataview
TASK
WHERE urgent
```

```

**Output**
  * Bedroom [urgent:: true]


## CALENDAR
The `CALENDAR` Query outputs a monthly based calendar where every result is depicted as a dot on it referring date. The `CALENDAR` is the only Query Type that requires an additional information. This additional information needs to be a date (or unset) on all queried pages.
`CALENDAR` Query Type
The `CALENDAR` Query Types renders a calendar view where every result is represented by a dot on the given meta data field date.
```
```dataview
CALENDAR file.ctime
```

```

**Output**
!
While it is possible to use `SORT` and `GROUP BY` in combination with `CALENDAR`, it has **no effect**. Additionally, the calendar query does not render if the given meta data field contains something else than a valid date (but the field can be empty). To make sure you're only taking valid pages into account, you can filter for valid meta data values:
```
```dataview
CALENDAR due
WHERE typeof(due) = "date"
```

```




================================================================================

## 22. Reference > Literals





# Literals
Dataview query language _literals_ are **expressions** which represent constant values like a text (`"Science"`) or a number (`2021`). They can be used as part as functions or of expressions like comparison. Some examples of Queries that use **literals** :
```
Literal (number) 2022 used in a comparison
```dataview
LIST
WHERE file.day.year = 2022
```
Literal (text) "Math" used in a function call
```dataview
LIST
WHERE contains(file.name, "Math")
```
Literal (link) [[Study MOC]] used as a source
```dataview
LIST
FROM [[Study MOC]]
```
Literal (date) date(yesterday) used in a comparison
```dataview
TASK
WHERE !completed AND file.day = date(yesterday)
```
Literal (duration) dur(2 days) used in a comparison
```dataview
LIST
WHERE end - start > dur(2 days)
```

```

Literals
Literals are **static values** that can be used as part of the Dataview Query Language (DQL), i.e. for comparisons.
The following is an extensive, but non-exhaustive list of possible literals in DQL.
### General
Literal | Description  
---|---  
`0` | The number zero  
`1337` | The positive number 1337  
`-200` | The negative number -200  
`"The quick brown fox jumps over the lazy dog"` | Text (sometimes referred to as "string")  
`[[Science]]` | A link to the file named "Science"  
`[[]]` | A link to the current file  
`[1, 2, 3]` | A list of numbers 1, 2, and 3  
`[[1, 2],[3, 4]]` | A list of list [1, 2] and [3, 4]  
`{ a: 1, b: 2 }` | An object with keys a and b, whereas a has value 1, b 2.  
`date(2021-07-14)` | A date (read more below)  
`dur(2 days 4 hours)` | A duration (read more below)  
Literals as field values
Literals are only interpreted this way when used inside a Query, not when used as a meta data value. For possible values and their data types for fields, please refer to Types of Metadata.
### Dates
Whenever you use a field value in Date ISO format, you'll need to compare these fields against date objects. Dataview provides some shorthands for common use cases like tomorrow, start of current week etc. Please note that `date()` is also a function, which can be called on **text** to extract dates.
Literal | Description  
---|---  
`date(2021-11-11)` | A date, November 11th, 2021  
`date(2021-09-20T20:17)` | A date, September 20th, 2021 at 20:17  
`date(today)` | A date representing the current date  
`date(now)` | A date representing the current date and time  
`date(tomorrow)` | A date representing tomorrow's date  
`date(yesterday)` | A date representing yesterday's date  
`date(sow)` | A date representing the start of the current week  
`date(eow)` | A date representing the end of the current week  
`date(som)` | A date representing the start of the current month  
`date(eom)` | A date representing the end of the current month  
`date(soy)` | A date representing the start of the current year  
`date(eoy)` | A date representing the end of the current year  
### Durations
Durations are representatives of a time span. You can either define them directly or create them due to calculating with dates, and use these for i.e. comparisons.
#### Seconds
Literal | Description  
---|---  
`dur(1 s)` | one second  
`dur(3 s)` | three seconds  
`dur(1 sec)` | one second  
`dur(3 secs)` | three seconds  
`dur(1 second)` | one second  
`dur(3 seconds)` | three seconds  
#### Minutes
Literal | Description  
---|---  
`dur(1 m)` | one minute  
`dur(3 m)` | three minutes  
`dur(1 min)` | one minute  
`dur(3 mins)` | three minutes  
`dur(1 minute)` | one minute  
`dur(3 minutes)` | three minutes  
#### Hours
Literal | Description  
---|---  
`dur(1 h)` | one hour  
`dur(3 h)` | three hours  
`dur(1 hr)` | one hour  
`dur(3 hrs)` | three hours  
`dur(1 hour)` | one hour  
`dur(3 hours)` | three hours  
#### Days
Literal | Description  
---|---  
`dur(1 d)` | one day  
`dur(3 d)` | three days  
`dur(1 day)` | one day  
`dur(3 days)` | three days  
#### Weeks
Literal | Description  
---|---  
`dur(1 w)` | one week  
`dur(3 w)` | three weeks  
`dur(1 wk)` | one week  
`dur(3 wks)` | three weeks  
`dur(1 week)` | one week  
`dur(3 weeks)` | three weeks  
#### Months
Literal | Description  
---|---  
`dur(1 mo)` | one month  
`dur(3 mo)` | three month  
`dur(1 month)` | one month  
`dur(3 months)` | three months  
#### Years
Literal | Description  
---|---  
`dur(1 yr)` | one year  
`dur(3 yrs)` | three years  
`dur(1 year)` | one year  
`dur(3 years)` | three years  
#### Combinations
Literal | Description  
---|---  
`dur(1 s, 2 m, 3 h)` | three hours, two minutes, and one second  
`dur(1 s 2 m 3 h)` | three hours, two minutes, and one second  
`dur(1s 2m 3h)` | three hours, two minutes, and one second  
`dur(1second 2min 3h)` | three hours, two minutes, and one second  



================================================================================

## 23. Reference > Expressions





# Expressions
Dataview query language **expressions** are anything that yields a value:
  * all fields
  * all literals
  * and computed values, like `field - 9` of function calls. 


Basically, everything that is not a Query Type, nor a data command is an expression.
For a very high level summary, following is considered an **expression** in DQL:
```
# Literals
1          (number)
true/false     (boolean)
"text"       (text)
date(2021-04-18)  (date)
dur(1 day)     (duration)
[[Link]]      (link)
[1, 2, 3]      (list)
{ a: 1, b: 2 }   (object)
# Lambdas
(x1, x2) => ...   (lambda)
# References
field        (directly refer to a field)
simple-field    (refer to fields with spaces/punctuation in them like "Simple Field!")
a.b         (if a is an object, retrieve field named 'b')
a[expr]       (if a is an object or array, retrieve field with name specified by expression 'expr')
f(a, b, ...)    (call a function called `f` on arguments a, b, ...)
# Arithmetic
a + b        (addition)
a - b        (subtraction)
a * b        (multiplication)
a / b        (division)
a % b        (modulo / remainder of division)
# Comparison
a > b        (check if a is greater than b)
a < b        (check if a is less than b)
a = b        (check if a equals b)
a != b       (check if a does not equal b)
a <= b       (check if a is less than or equal to b)
a >= b       (check if a is greater than or equal to b)
# Strings
a + b        (string concatenation)
a * num       (repeat string <num> times)
# Special Operations
[[Link]].value   (fetch `value` from page `Link`)

```

More detailed explanations of each follow.
## Expression Types
### Fields as Expressions
The simplest expression is one that just directly refers to a field. If you have a field called "duedate", then you can refer to it directly by name - `duedate`. 
```
```dataview
TABLE duedate, class, field-with-space
```

```

Field names with spaces and punctuations
If the field name has spaces, punctuation, or other non-letter/number characters, then you can refer to it using Dataview's simplified name, which is all lower case with spaces replaced with "-". For example, `this is a field` becomes `this-is-a-field`; `Hello!` becomes `hello`, and so on. Read more under Field names
### Literals
Constant values - things like `1` or `"hello"` or `date(som)` ("start of month"). There are literals for each data type that dataview supports; read more about them here.
```
```dataview
LIST
WHERE file.name = "Scribble"
```

```

### Arithmetic
You can use standard arithmetic operators to combine fields: addition (`+`), subtraction (`-`), multiplication (`*`), and division (`/`). For example `field1 + field2` is an expression which computes the sum of the two fields.
```
```dataview
TABLE start, end, (end - start) - dur(8 h) AS "Overtime" 
FROM #work
```
```dataview
TABLE hrs / 24 AS "days"
FROM "30 Projects"
```

```

### Comparisons
You can compare most values using the various comparison operators: `<`, `>`, `<=`, `>=`, `=`, `!=`. This yields a boolean true or false value which can be used in `WHERE` blocks in queries.
```
```dataview
LIST
FROM "Games"
WHERE price > 10
```
```dataview
TASK
WHERE due <= date(today)
```
```dataview
LIST
FROM #homework
WHERE status != "done"
```

```

Comparing different types
Comparing different data types with each other can lead to unexpected results. Take the second example: If `due` is not set (neither on page nor task level), it is `null` and `null <= date(today)` returns true, including tasks without any due date. If this is not wanted, add a type check to make sure you're always comparing the same types: 
```
```dataview
TASK
WHERE typeof(due) = "date" AND due <= date(today)
```

```

Most often, it is sufficient to check if the meta data is available via `WHERE due AND due <= date(today)`, but checking the type is the safer way to get foreseeable results. 
### List/Object Indexing
You can retrieve data from lists/arrays via the index operator `list[<index>]`, where `<index>` is any computed expression. Lists are 0-indexed, so the first element is index 0, the second element is index 1, and so on. For example `list("A", "B", "C")[0] = "A"`.
A similar notation style works for objects. You can use `field["nestedfield"]` to reference fields inside an object or otherwise similarly nested. For example, in the YAML defined below, we can reference `previous` via `episode_metadata["previous"]`. 
```
---
aliases:
-"ABC"
current_episode:"S01E03"
episode_metadata:
previous:"S01E02"
next:"S01E04"
---

```

You can also retrieve data from objects (which map text to data values) also using the index operator, where indexes are now strings/text instead of numbers. You can also use the shorthand `object.<name>`, where `<name>` is the name of the value to retrieve. For the previous frontmatter example, we could also use `episode_metadata.previous` to obtain the same value.
Index expressions also work on objects which have fields that are not directly supported by the query language. A good example is `where`, since it is a keyword. If your frontmatter/metadata contains a field `where`, you can reference it via the `row` syntax: `row["where"]`. See the note in the FAQ and the corresponding issue for further information.
```
```dataview
TABLE id, episode_metadata.next, aliases[0]
```

```

### Function Calls
Dataview supports various functions for manipulating data, which are described in full in the functions documentation. They have the general syntax `function(arg1, arg2, ...)` - i.e., `lower(file.name)` or `regexmatch("A.+", file.folder)`.
```
```dataview
LIST
WHERE contains(file.name, "WIP")
```
```dataview
LIST
WHERE string(file.day.year) = split(this.file.name, "-W")[0]
```

```

### Lambdas
Lambdas are advanced literals which let you define a function that takes some number of inputs, and produces an output. They have the general form:
```
(arg1, arg2, arg3, ...) => <expression using args>

```

Lambdas are used in several advanced operators like `reduce` and `map` to allow for complex transformations of data. A few examples:
```
(x) => x.field         (return field of x, often used for map)
(x, y) => x + y         (sum x and y)
(x) => 2 * x          (double x)
(value) => length(value) = 4  (return true if value is length 4)

```

```
```dataview
CALENDAR file.day
FLATTEN all(map(file.tasks, (x) => x.completed)) AS "allCompleted"
WHERE !allCompleted
```

```

## Type-specific Interactions & Values
Most dataview types have special interactions with operators, or have additional fields that can be retrieved using the index operator. This is true for dates and durations and as well for links. Read more about date and durations on their respective section in Types of Metadata.
### Links
You can "index through" a link to get values on the corresponding page. For example `[[Assignment Math]].duedate` would get the value `duedate` from page `Assignment Math`.
Link Indexing in Expressions
If your link is a field that you defined in an inline field or in front-matter, like `Class:: [[Math]]` and you want to get the field `timetable`, then you index into it by writing `Class.timetable`. Using `[[Class]].timetable` would look up the page literally called `Class`, and not `Math`!



================================================================================

## 24. Resources > Faq





# Frequently Asked Questions
A collection of frequently asked questions for Dataview queries and the expression language.
### How do I use fields with the same name as keywords (like "from", "where")?
Dataview provides a special "fake" field called `row` which can be indexed into to obtain fields which conflict with Dataview keywords:
```
row.from/* Same as "from" */
row.where/* Same as "where" */

```

### How do I access fields with spaces in the name?
There are two ways:
  1. Use the normalized Dataview name for such a field - just convert the name to lowercase and replace whitespace with dashes ("-"). Something like `Field With Space In It` becomes `field-with-space-in-it`.
  2. Use the implicit `row` field: 
```
row["Field With Space In It"]

```



### Do you have a list of resources to learn from?
Yes! Please see the Resources page.
### Can I save the result of a query for reusability?
You can write reusable Javascript Queries with the dv.view function. In DQL, beside the possibility of writing your Query inside a Template and using this template (either with the Core Plugin Templates or the popular Community Plugin Templater), you can **save calculations in metadata fields viaInline DQL**, for example:
```
start:: 07h00m
end:: 18h00m
pause:: 01h30m
duration:: `= this.end - this.start - this.pause`

```

You can list the value (9h 30m in our example) then i.e. in a TABLE without needing to repeat the calculation:
```
```dataview
TABLE start, end, duration
WHERE duration
```

```

Gives you
File (1) | start | end | duration  
---|---|---|---  
Example | 7 hours | 18 hours | 9 hours, 30 minutes  
**But storing a Inline DQL in a field comes with a limitation** : While the value that gets displayed in the result is the calculated one, **the saved value inside your metadata field is still your Inline DQL calculation**. The value is literally `= this.end - this.start - this.pause`. This means you cannot filter for the Inlines' result like:
```
```dataview
TABLE start, end, duration
WHERE duration > dur("10h")
```

```

This will give you back the example page, even though the result doesn't fulfill the `WHERE` clause, because the value you are comparing against is `= this.end - this.start - this.pause` and is not a duration.
### How can I hide the result count on TABLE Queries?
With Dataview 0.5.52, you can hide the result count on TABLE and TASK Queries via a setting. Go to Dataview's settings -> Display result count.
### How can I style my queries?
You can use CSS Snippets to define custom styling in general for Obsidian. So if you define `cssclasses: myTable` as a property, and enable the snippet below you could set the background color of a table from dataview. Similar to target the outer <ul> of a `TASK` or `LIST` query, you could use the `ul.contains-task-list` or `ul.list-view-ul` respectively.
```
.myTabledataview.table{
background-color:green
}

```

In general there are no unique ID's given to a specific table on a page, so the mentioned targeting applies to any note having that `cssclasses` defined and **all** tables on that page. Currently you can't target a specific table using an ordinary query, but if you're using javascript, you can add the class `clsname` directly to your query result by doing:
```
dv.container.className+=' clsname'

```

However, there is a trick to target any table within Obsidian using tags like in the example below, and that would apply to any table having that tag tag within it. This would apply to both manually and dataview generated tables. To make the snippet below work add the tag `#myId` _anywhere_ within your table output.
```
[href="#myId"]{
display:none;/* Hides the tag from the table view */
}
table:has([href="#myId"]){
/* Style your table as you like */
background-color:#262626;
&tr:nth-child(even)td:first-child{
background-color:#3f3f3f;
}
}

```

Which would end up having a grey background on the entire table, and the first cell in every even row a different variant of grey. **Disclaimer:** We're not style gurus, so this is just an example to show some of the syntax needed for styling different parts of a table.
Furthermore, in Style dataview table columns @s-blu describes an alternate trick using `<span>` to style various parts of table cells (and columns).



================================================================================

## 25. Resources > Resources And Support





# Other Resources
There is a bit of a learning curve to getting started with Dataview. This page is a collection of resources that will help you get started. Dataview gets new features and fixes fairly frequently so please account for these resources being slightly out of date. Feel free to contribute directly to this list, documentation, or even reach out to the authors of the original sources for updates.
## Resources
### The Obsidian Hub
  * SkepticMystic's Introduction to Dataview supplemented by a textual guide


### YouTube videos
  * SkepticMystic's aforementioned community talk
  * Dataview Plugin: How To Use This Powerful Obsidian Plugin (With Examples) by Filipe Donadio
  * Automate Your Vault With Dataview - How To Use Dataview in Obsidian by FromSergio
  * How to use the Obsidian Dataview plugin by Nicole van der Hoeven
  * Intro to Dataview Plugin - Obsidian Community Talk


### Example Vault
  * @s-blu has very kindly put together a vault of example queries that you can use as a playground of sorts.


### Blog Posts
  * Obsidian Dataview For Beginners: A checklist to help fix your dataview queries


### GitHub Discussion
The GitHub repository has a fairly active Discussions Page with dozens of answered questions.
### Obsidian Forums
The Obsidian Forums have a wealth of questions and answers and other interesting tidbits as well. Try searching the forums for an answer, especially if it seems like a beginner question.
### Discord
The Obsidian Members Group Discord server has a `#dataview` channel. Once again, more likely than not, your question has been asked before so try searching the thread though it is known that Discord's search can be spotty. In case you don't find anything satisfactory, This is the closest you'll get to real-time support but there are no guarantees of instant replies. There are many helpful people though so don't be afraid to ask.
## Support
Where do you go when you have questions? Here's what we recommend you try.
  1. Search GitHub Discussions and the Obsidian Forums for your question.
  2. Search through Discord for possible solutions.
  3. Depending on the complexity of the your question:
  4. If you need close to synchronous communication, use Discord. Note that we are a community of volunteers and there may be delays in responding.
  5. If you expect your problem needs time over multiple days and asynchronous communication, open a GitHub discussion.
  6. If you found a bug, please report it in the repo's issues.





================================================================================


## 27. Data Annotation





# Adding Metadata to your Pages
Dataview cannot query all content of your vault. In order to be able to search, filter and display content, this content needs to be **indexed**. Some content is indexed automatically, like bullet points or task lists - so called **Implicit fields** , more on that below - and other data needs to be saved in a metadata **field** to be accessible through dataview. 
## What is a "field"?
A metadata field is a pair of a **key** and a **value**. The _value_ of a field has a data type (more on that here) that determines how this field will behave when querying it. 
You can add any number of fields to a **note** , a **list item** or a **task**. 
## How do I add fields?
You can add fields to a **note** in three different ways. How a field look like depends on the way you add it.
On **tasks or list items** , you will have YAML Frontmatter information available, but won't be able to add them to a specific list item. If you want to add metadata to one list item or task only, use Inline Fields.
### Frontmatter
Frontmatter is a common Markdown extension which allows for YAML metadata to be added to the top of a page. It is natively supported by Obsidian and explained in its official documentation. All YAML Frontmatter fields will be automatically available as Dataview fields.
```
---
alias:"document"
last-reviewed:2021-08-17
thoughts:
rating:8
reviewable:false
---

```

With this your note has metadata fields named `alias`, `last-reviewed`, and `thoughts`. Each of these have different **data types** :
  * `alias` is a text, because its wrapped in ""
  * `last-reviewed` is a date, because it follows the ISO date format
  * `thoughts` is a object field, because it uses the YAML Frontmatter object syntax


You could query for this note with the following query:
```
```dataview
LIST
WHERE thoughts.rating = 8
```

```

### Inline Fields
For those wanting a more natural-looking annotation, Dataview supports "inline" fields via a `Key:: Value` syntax that you can use everywhere in your file. This allows you to write your queryable data right where you need it - for example in the middle of a sentence. 
If your inline field has an own line, without any content beforehand, you can write it like this: 
```
# Markdown Page
Basic Field:: Some random Value
**Bold Field**:: Nice!

```

All content after the `::` is the value of the field until the next line break.
Mind the `::`
Note that you need to use a double colon `::` between key and value when using inline fields, contrary to YAML Frontmatter fields where one colon is enough. 
If you want to embed metadata inside sentences, or multiple fields on the same line, you can use the bracket syntax and wrap your field in square brackets:
```
I would rate this a [rating:: 9]! It was [mood:: acceptable].

```

Fields on list items and tasks
When you want to annotate a list item, e.g. a task, with metadata, you always need to use the bracket syntax (because the field is not the only information in this line) 
```
- [ ] Send an mail to David about the deadline [due:: 2022-04-05].

```

Bracketed inline fields are the only way to explicitly add fields to specific list items, YAML frontmatter always applies to the whole page (but is also available in context of list items.) 
There is also the alternative parenthesis syntax, which hides the key when rendered in Reader mode:
```
This will not show the (longKeyIDontNeedWhenReading:: key).

```

will render to:
```
This will not show the key.

```

You can use YAML Frontmatter and Inline fields with all syntax variants together in one file. You do not need to decide for one and can mix them to fit your workflow.
## Field names
Imagine you used all the examples for Inline fields you see above in one note, then following metadata would be available to you:
Metadata Key | Sanitized Metadata key | Value | Data Type of Value  
---|---|---|---  
`Basic Field` | `basic-field` | Some random Value | Text  
`Bold Field` | `bold-field` | Nice! | Text  
`rating` | - | 9 | Number  
`mood` | - | acceptable | Text  
`due` | - | Date Object for 2022-04-05 | Date  
`longKeyIDontNeedWhenReading` | `longkeyidontneedwhenreading` | key | Text  
Like you can see in the table, if you are using **spaces or capitalized letters** in your metadata key name, dataview will provide you with a **sanitized version** of the key. 
**Keys with spaces** cannot be used in a query as-is. You have two possibilities here: Either use the sanitized name, that is always all lowercase and with dashes instead of spaces or use the **row** variable syntax. Find out more in the FAQ.
**Keys with capitalized letters** can be used as-is, if you wish. The sanitized version allows you to query for a key independent of its capitalization and makes it easier to use: You can query the same field that's, for example, in one file named `someMetadata` and in another `someMetaData` when using the sanitized key `somemetadata`. 
In addition, the **bold field key is missing its formatting tokens**. Even though the `**` used to make it appear bold are part of the key name in the file, they are left out when indexing your note. The same goes for all other built-in formatting, like strike through or italic. This means formatted keys can only be queried without their formatting. This allows you to format the key in context of the note without worrying that you might create different keys for the same type of information. 
### Usage of emojis and non-latin characters
You are not limited to latin characters when naming your metadata fields. You can use all characters available in UTF-8:
```
Noël:: Un jeu de console
クリスマス:: 家庭用ゲーム機
[🎅:: a console game]
[xmas🎄:: a console game]

```

**Using emojis as metadata keys** is possible, but it comes with some limitations. When using emojis in field names, you need to put them into square brackets so that dataview recognize them correctly. Also, please be aware when switching the OS (i.e. from Windows to Android), the same emoji could use another character code and you might not find your metadata when querying it.
Task Field Shorthands
An exception to this are the shorthand syntax in Tasks. You can use shorthands without bracketing. Please mind though that this only counts for listed shorthands - every other field (if with emojis or not) need to use the `[key:: value]` syntax.
## Implicit fields
Even if you do not add any metadata explicitly to your note, dataview provides you with a big amount of indexed data out of the box. Some examples for implicit fields are:
  * day the file was created (`file.cday`)
  * links in the file (`file.outlinks`)
  * tags in the file (`file.etags`)
  * all list items in the file (`file.lists` and `file.tasks`)


and many more. Available implicit fields differ depending if you look at a page or a list item. Find the full list of available implicit fields on Metadata on pages and Metadata on Tasks and Lists.


