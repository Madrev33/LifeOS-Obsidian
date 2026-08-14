# Documentação Completa - quickadd_obsidian_guide

**URL Original**: https://quickadd.obsidian.guide/docs/
**Data**: 28/05/2025 21:15:02
**Estratégia**: BFS
**Extraído com**: Crawl4AI - Madrev Edition

---

## 1. https://quickadd.obsidian.guide/docs/



## Installation​
**This plugin is in the community plugin browser in Obsidian**. You can search for it and install it there .
You can also do a manual installation.
## First steps​
The first thing you'll want to do is add a new choice. A choice can be one of four types.
  * Template Choice - Insert templates into your vault. Works together with Obsidian template syntax and popular _Templater_ plugin, augmenting them and adding more options.
  * Capture Choice - Quick capture your manually written information and save it. Daily notes, work log, to-read-and-watch-later list, etc.
  * Macro Choice - Macros to augment your workflow. Use the full power of Javascript programming language and Obsidian functions to do anything your want. E.g. create a personal movie database by writing a movie name and getting the movie notes fully customized and filled with correct film's up-to-date data.
  * Multi Choice - Folders to better organize the previous 3 choices. Usability feature, not a new functionality.


In your choices, you can use format syntax, which is similar to the Obsidian template syntax.
You could, for example, use `{{DATE}}` to get the current date.
## I want to...​
### Be inspired​
Take a look at some examples...
  * Capture: Add Journal Entry
  * Macro: Log book to daily journal
  * Template: Add an Inbox Item
  * Macro: Move all notes with a tag to a certain folder
  * Template: Automatically create a new book note with notes & highlights from Readwise
  * Capture: Add a task to a Kanban board
  * Macro: Easily change properties in your daily note (requires MetaEdit)
  * Capture: Fetch tasks from Todoist and capture to a file
  * Macro: Zettelizer - easily create new notes from headings while keeping the contents in the file
  * Macro: Obsidian Map View plugin helper - insert location from address
  * Macro: Toggl Manager - set preset Toggl Track time entries and start them from Obsidian
  * How I Read Research Papers with Obsidian and Zotero
  * How I Import Literature Notes into Obsidian
  * Macro: Fetching movies and TV shows into your vault


### Create powerful scripts and macros to automate my workflow​
Take a look at the QuickAdd API, format syntax, inline scripts, and macros.
### Use QuickAdd even when Obsidian is minimized / in the background​
You got it. Take a look at this AutoHotKey script.
  * Installation
  * First steps
  * I want to...
    * Be inspired
    * Create powerful scripts and macros to automate my workflow
    * Use QuickAdd even when Obsidian is minimized / in the background




================================================================================

## 2. https://quickadd.obsidian.guide




================================================================================

## 3. https://quickadd.obsidian.guide/docs



## Installation​
**This plugin is in the community plugin browser in Obsidian**. You can search for it and install it there .
You can also do a manual installation.
## First steps​
The first thing you'll want to do is add a new choice. A choice can be one of four types.
  * Template Choice - Insert templates into your vault. Works together with Obsidian template syntax and popular _Templater_ plugin, augmenting them and adding more options.
  * Capture Choice - Quick capture your manually written information and save it. Daily notes, work log, to-read-and-watch-later list, etc.
  * Macro Choice - Macros to augment your workflow. Use the full power of Javascript programming language and Obsidian functions to do anything your want. E.g. create a personal movie database by writing a movie name and getting the movie notes fully customized and filled with correct film's up-to-date data.
  * Multi Choice - Folders to better organize the previous 3 choices. Usability feature, not a new functionality.


In your choices, you can use format syntax, which is similar to the Obsidian template syntax.
You could, for example, use `{{DATE}}` to get the current date.
## I want to...​
### Be inspired​
Take a look at some examples...
  * Capture: Add Journal Entry
  * Macro: Log book to daily journal
  * Template: Add an Inbox Item
  * Macro: Move all notes with a tag to a certain folder
  * Template: Automatically create a new book note with notes & highlights from Readwise
  * Capture: Add a task to a Kanban board
  * Macro: Easily change properties in your daily note (requires MetaEdit)
  * Capture: Fetch tasks from Todoist and capture to a file
  * Macro: Zettelizer - easily create new notes from headings while keeping the contents in the file
  * Macro: Obsidian Map View plugin helper - insert location from address
  * Macro: Toggl Manager - set preset Toggl Track time entries and start them from Obsidian
  * How I Read Research Papers with Obsidian and Zotero
  * How I Import Literature Notes into Obsidian
  * Macro: Fetching movies and TV shows into your vault


### Create powerful scripts and macros to automate my workflow​
Take a look at the QuickAdd API, format syntax, inline scripts, and macros.
### Use QuickAdd even when Obsidian is minimized / in the background​
You got it. Take a look at this AutoHotKey script.
  * Installation
  * First steps
  * I want to...
    * Be inspired
    * Create powerful scripts and macros to automate my workflow
    * Use QuickAdd even when Obsidian is minimized / in the background




================================================================================

## 4. https://quickadd.obsidian.guide/docs/Choices/CaptureChoice



Allows to quickly capture your input and save it from anywhere in Obsidian, without leaving your current window setup e.g.
  * Add messages to your work log
  * Save interesting links for later reading and watching
  * Individually timed notes in Daily notes file


## Capture To​
 _Capture To_ is the name of the file you are capturing to. You can choose to either enable _Capture to active file_ , or you can enter a file name in the _File Name_ input field.
This field also supports the format syntax, which allows you to use dynamic file names. I have one for my daily journal with the name `bins/daily/{{DATE:gggg-MM-DD - ddd MMM D}}.md`. This automatically finds the file for the day, and whatever I enter will be captured to it.
### Capturing to folders​
You can also type a **folder name** into the _Capture To_ field, and QuickAdd will ask you which file in the folder you'd like to capture to. This also supports the format syntax. You can even write a filename in the suggester that opens, and it will create the file for you - assuming you have the _Create file if it doesn't exist_ setting enabled.
For example, you might have a folder called `CRM/people`. In this folder, you have a note for the people in your life. You can type `CRM/people` in the _Capture To_ field, and QuickAdd will ask you which file to capture to. You can then type `John Doe` in the suggester, and QuickAdd will create a file called `John Doe.md` in the `CRM/people` folder.
You could also write nothing - or `/` - in the _Capture To_ field. This will open the suggester with all of your files in it, and you can select or type the name of the file you want to capture to.
Capturing to a folder will show all files in that folder. This means that files in nested folders will also appear.
### Capturing to tags​
Similarly, you can type a **tag name** in the _Capture To_ field, and QuickAdd will ask you which file to capture to, assuming the file has the tag you specify.
If you have a tag called `#people`, and you type `#people` in the _Capture To_ field, QuickAdd will ask you which file to capture to, assuming the file has the `#people` tag.
## Capture Options​
  *  _Create file if it doesn't exist_ will do as the name implies - you can also create the file from a template, if you specify the template (the input box will appear below the setting).
  * _Task_ will format your captured text as a task.
  * _Write to bottom of file_ will put whatever you enter at the bottom of the file.
  * _Append link_ will append a link to the file you have open in the file you're capturing to.


## Insert after​
Insert After will allow you to insert the text after some line with the specified text.
With Insert After, you can also enable `Insert at end of section` and `Consider subsections`. You can see an explanation of these below.
I use this in my daily journal capture, where I insert after the heading line `## What did I do today?`.
It's also possible to use `Create line if not found`, which will create the line if it doesn't exist. This is useful if you want to insert after a line that might not exist in the file you're capturing to. This setting can place the line at the start or end of the file, or at your current cursor position.
### Consider subsections -option​
#### `Consider subsections` disabled​
Behavior with `Insert after` & `Insert at end`:
```
## 1. First heading**Insert after** comes here.-  content 1-  content 2-  content 3**Insert at end** comes here.### 1.1. Nested heading 1Content## 2. Another headingContent
```

#### `Consider subsections` enabled​
Behavior with `Insert after` & `Insert at end`:
```
## 1. First heading**Insert after** comes here-  content 1-  content 2-  content 3### 1.1. Nested heading 1Content**Insert at end** comes here. Captures to after this, as it's considered part of the "1. First heading" section.## 2. Another headingContent
```

## Capture Format​
Capture format lets you specify the exact format that you want what you're capturing to be inserted as. You can do practically anything here. Think of it as a mini template.
If you do not enable this, QuickAdd will default to `{{VALUE}}`, which will just insert whatever you enter in the prompt that appears when activating the Capture.
You can use format syntax here, which allows you to use dynamic values in your capture format.
In my journal capture, I have it set to `- {{DATE:HH:mm}} {{VALUE}}`. This inserts a bullet point with the time in hour:minute format, followed by whatever I entered in the prompt.
  * Capture To
    * Capturing to folders
    * Capturing to tags
  * Capture Options
  * Insert after
    * Consider subsections -option
  * Capture Format




================================================================================

## 5. https://quickadd.obsidian.guide/docs/AIAssistant



# AI Assistant
The AI Assistant in QuickAdd leverages the power of Large Language Models (LLMs) to act as your personal AI assistant within Obsidian. It can streamline your workflows by automating routine tasks and providing intellectual support. To use this feature, you need the QuickAdd plugin and a provider you'd like to use.
## How to Setup the AI Assistant​
To set up the AI Assistant, follow these steps:
  1. In Obsidian, create a new folder dedicated to AI prompt templates, e.g. `bins/ai_prompts`.
  2. Navigate to QuickAdd settings and locate the "AI Assistant" section. Specify the path to the folder you created in step 1.
  3. In the same section, add a provider to get started. If you are using OpenAI, you will need to add your API key to the settings. As of v1.8.x, you need to enter your API key in the provider settings. The video below is from an older version, but the process is the similar.


That's really it. You're now ready to use the AI Assistant.
The basic idea is that you set up a QuickAdd Macro, which will trigger the AI Assistant. The AI Assistant will then use the prompt template you specify to generate a prompt, which it will then send to OpenAI. OpenAI will then return a response, which the AI Assistant passes on to the QuickAdd Macro. You can then use the response in subsequent steps in the macro, e.g. to capture to a note, or create a new note.
**Creating prompt templates is simple: just create a note in your prompt templates folder.**
Creating prompt templates is as simple as creating a note within your prompt templates folder. These templates can utilize QuickAdd's Format Syntax or Inline Scripts.
Here's an example of how you can set up a prompt template:
You can also use AI Assistant features from within the API.
## Providers​
QuickAdd supports multiple providers for LLMs. The only requirement is that they are OpenAI-compatible, which means their API should be similar to OpenAIs.
Here are a few providers that are known to work with QuickAdd:
  * TogetherAI
  * Ollama (local)


Paid providers expose their own API, which you can use with QuickAdd. Free providers, such as Ollama, are also supported.
By default, QuickAdd will add the OpenAI provider. You can add more providers by clicking the "Add Provider" button in the AI Assistant settings.
Here's a video showcasing adding Groq as a provider:
### Local LLMs​
You can use your own machine to run LLMs. This is useful if you want to keep your data private, or if you want to use a specific model that isn't available on the cloud. To use a local LLM, you need to set up a server that can run the model. You can then add the server as a provider in QuickAdd.
One such server is Ollama. Ollama is a free, open-source, and self-hosted LLM server. You can set up Ollama on your own machine, and then use it as a provider in QuickAdd. You can find the quick start documentation here. Ollama binds to the port `11434` (src), so your provider settings would be as follows:
```
Name: OllamaURL: http://localhost:11434/v1Api Key: (empty)
```

And that's it! You can now use Ollama as a provider in QuickAdd. Make sure you add the model you want to use. mistral is great.
## AI Assistant Settings​
Within the main AI Assistant settings accessible via QuickAdd settings, you can configure the following options:
  * OpenAI API Key: The key to interact with OpenAI's models.
  * Prompt Templates Folder: The location where all your prompt templates reside.
  * Default model: The default OpenAI model to be used.
  * Show Assistant: Toggle for status messages.
  * Default System Prompt Template: Sets the behavior of the model.


For each individual AI Assistant command in your macros, you can set these options:
  * Prompt Template: Determines the prompt template to use.
  * Model: Specifies the OpenAI model to use, overriding the default model.
  * Output Name Variable: Sets the variable name for the AI Assistant’s output.
  * System Prompt Template: Determines the models behavior, overriding the default system prompt template.


You can also tweak model parameters in advanced settings:
  * **temperature:** Allows you to adjust the sampling temperature between 0 and 2. Higher values result in more random outputs, while lower values make the output more focused and deterministic.
  * **top_p:** This parameter relates to nucleus sampling. The model considers only the tokens comprising the top 'p' probability mass. For example, 0.1 means only tokens from the top 10% probability mass are considered.
  * **frequency_penalty:** A parameter ranging between -2.0 and 2.0. Positive values penalize new tokens based on their frequency in the existing text, reducing the model's tendency to repeat the same lines.
  * **presence_penalty:** Also ranging between -2.0 and 2.0, positive values penalize new tokens based on their presence in the existing text, encouraging the model to introduce new topics.


## AI-Powered Workflows​
You can create powerful workflows utilizing the AI Assistant. Some examples are:
  * **Generating Writing Prompts:** Using links to related notes to generate writing prompts.
  * **Summarizer:** Create summaries of selected text.
  * **Transform Selected:** Transform selected text based on provided instructions.
  * **Flashcard Creator:** Generate flashcards based on selected text.
  * **Get Me Started Writing About…:** Generate points to kickstart your writing on a given topic.
  * **Manual Prompt:** Provide a manual prompt to the AI assistant.
  * **Alternative Viewpoints:** Obtain alternative perspectives and improvements on your draft.
  * **Prompt Chaining:** Chain multiple prompts together, with each prompt using the output of the previous one.


All of these examples, and more, can be found in Christian's blog post about the AI Assistant.
Please note, using the AI Assistant will incur costs depending on the API usage. Set spending limits on your OpenAI account to avoid unexpected expenses. Play around with different models to find the one that best suits your needs.
### Example: Summarizer​
Here’s a simple prompt where you select some text, and then use the assistant with that prompt. Then it’ll spit out an AI-generated summary:
```
Please summarize the following text. Use only the text itself as material for summarization, and do not add anything new. Rewrite this for brevity, in outline form:{{value}}
```

You can use the getting-started demonstration shown earlier to set this up.
  * How to Setup the AI Assistant
  * Providers
    * Local LLMs
  * AI Assistant Settings
  * AI-Powered Workflows
    * Example: Summarizer




================================================================================

## 6. https://quickadd.obsidian.guide/docs/Choices/TemplateChoice



The template choice type is not meant to be a replacement for Templater plugin or core `Templates`. It's meant to augment them, to add more possibilities. You can use both QuickAdd format syntax in a Templater template - and both will work.
## Mandatory​
**Template Path**. This is a path to the template you wish to insert.
## Optional​
**File Name Format**. You can specify a format for the file name, which is based on the format syntax - which you can see further down this page. Basically, this allows you to have dynamic file names. If you wrote `£ {{DATE}} {{NAME}}`, it would translate to a file name like `£ 2021-06-12 Manually-Written-File-Name`, where `Manually-Written-File-Name` is a value you enter when invoking the template.
**Create in folder**. In which folder should the file be created in. You can specify as many folders as you want. If you don't, it'll just create the file in the root directory. If you specify one folder, it'll automatically create the file in there. If you specify multiple folders, you'll get a suggester asking which of the folders you wish to create the file in.
**Append link**. The file you're currently in will get a link to a newly created file.
**Increment file name**. If a file with that name already exists, increment the file name with a number. So if a file called `untitled` already exists, the new file will be called `untitled1`.
**Open**. Will open the file you've created. By default, it opens in the active pane. If you enable **New tab** , it'll open in a new tab in the direction you specified. 
  * Mandatory
  * Optional




================================================================================

## 7. https://quickadd.obsidian.guide/docs/Examples/Capture_AddJournalEntry


This captures a new journal entry in my daily journal under the `What did I do today` header.
Capture To: `bins/daily/{{DATE:gggg-MM-DD - ddd MMM D}}.md`
Insert after: `## What did I do today?`
Capture format:
```
- {{DATE:HH:mm}} {{VALUE}}\n
```



================================================================================

## 8. https://quickadd.obsidian.guide/docs/Choices/MacroChoice



Macros are powerful tools that allow you to execute any sequence of Obsidian commands and user scripts. User scripts are Javascript scripts that you can write to do something in Obsidian. All you need is a Javascript file in your vault, and you can activate it.
Each _macro choice_ has an associated _macro_. A macro choice allows you to activate a macro from the QuickAdd suggester.
This is what the settings for a _macro choice_ looks like.
You can have any amount of _macros_. 
Manage settings using the **macro manager**. 
  * **Run on plugin load**. Useful e.g. to create a daily note automatically when you open Obsidian. 


## Practical programming example​
I have a `logBook` macro. It just executes my user scripts, which in turn update the book in my daily page to something I specify in a prompt.
Here it is - with some comments that explain the code. How-to-install guide.
```
// You have to export the function you wish to run.// QuickAdd automatically passes a parameter, which is an object with the Obsidian app object// and the QuickAdd API (see description further ).module.exports=async(params)=>{// Object destructuring. We pull inputPrompt out of the QuickAdd API in params.const{quickAddApi:{ inputPrompt },    app,}= params;// Here, I pull in the update function from the MetaEdit API.const{ update }= app.plugins.plugins["metaedit"].api;// This opens a prompt with the header "📖 Book Name". val will be whatever you enter.const val =awaitinputPrompt("📖 Book Name");// This gets the current date in the specified format.const date =window.moment().format("gggg-MM-DD - ddd MMM D");// Invoke the MetaEdit update function on the Book property in my daily journal note.// It updates the value of Book to the value entered (val).awaitupdate("Book", val,`bins/daily/${date}.md`);
```

Any function executed by QuickAdd will be passed an object as the first (and only) parameter. The object contains
  * A reference to the Obsidian `app`.
  * A reference to the QuickAddApi - which allows you to use the functions below.
  * A reference to `variables`, an object which, if you assign values to it, you can use in your format syntax.


Let's talk a bit more about `variables`. If you assign a value to a key in `variables`, you can access that variable by its key name. This can be accessed both in subsequent macros, and the format syntax `{{VALUE:<variable name>}}`.
For example, say you assign `myVar` to `variables`. Then you can access the value of `myVar` in subsequent macros, as well as through the format syntax `{{VALUE:myVar}}`. You can also access it through `<parametername>.variables["myVar"]`.
```
// MACRO 1module.exports=(params)=>{  params.variables["myVar"]="test";// MACRO 2module.exports=(params)=>{console.log(params.variables["myVar"]);
```

You can use variables to pass parameters between user scripts.
In your user scripts for your macros, you can have use `module.exports` to export a function, which will be executed as expected.
You can, however, export much more than functions. You can also export variables - and more functions!
```
// Macro called 'MyMacro'module.exports={myVar:"test",plus:(params)=> params.variables["a"]+ params.variables["b"],  start,asyncfunctionstart(params){  params.app.vault.doSomething();const input =await params.quickAddApi.suggester(["DisplayValue1","DisplayValue2","DisplayValue3"],["ActualValue1","ActualValue2","ActualValue3"]return input;
```

If you select the macro that contains a user script with the above code, you'll be prompted to choose between one of the three exported items.
However, if you want to skip that, you can access nested members using this syntax: `{{MACRO:MyMacro::Start}}`. This will just instantly execute `start`.
## Troubleshooting​
Getting `Syntax error: unexpected identifier`? Please see this issue for a solution.
  * Practical programming example
  * Troubleshooting




================================================================================

## 9. https://quickadd.obsidian.guide/docs/Examples/Macro_MovieAndSeriesScript



This script allows you to easily insert a movie or TV show note into your vault.
We use OMDb api to get the movie or TV show information. You can get an API key on the website here. This will be needed to use this script.
## Demo​
## Installation​
We'll need to install a QuickAdd user script for this to work. I have made a video which shows you how to do so - click here. You will need to put the user script into a new macro and then create a Macro choice in the main menu to activate it. You can find the script here.
  1. Save the script (`movies.js`) to your vault somewhere. Make sure it is saved as a JavaScript file, meaning that it has the `.js` at the end.
  2. Create a new template in your designated templates folder. Example template is provided below.
  3. Open the Macro Manager by opening the QuickAdd plugin settings and clicking `Manage Macros`.
  4. Create a new Macro - you decide what to name it. I named mine `Movie`.
  5. Add the user script to the command list.
  6. Add a new Template step to the macro. This will be what creates the note in your vault. Settings are as follows:
    1. Set the template path to the template you created.
    2. Enable File Name Format and use `{{VALUE:fileName}}` as the file name format. You can specify this however you like. The `fileName` value is the name of the Movie or TV show without illegal file name characters.
    3. The remaining settings are for you to specify depending on your needs.
  7. Click on the cog icon to the right of the script step to configure the script settings. This should allow you to enter the API key you got from OMDb. Image demonstration.
  8. Go back out to your QuickAdd main menu and add a new Macro choice. Again, you decide the name. I named mine `🎬 Movie`. This is what activates the macro.
  9. Attach the Macro to the Macro Choice you just created. Do so by clicking the cog ⚙ icon and selecting it.


You can now use the macro to create notes with movie or TV show information in your vault.
### Example template​
```
---cover:{{ VALUE:Poster }}---category:: {{VALUE:typeLink}}director:: {{VALUE:directorLink}}genre:: {{VALUE:genreLinks}}imdbId:: {{VALUE:imdbID}}ratingImdb:: {{VALUE:imdbRating}}rating::year:: {{VALUE:Year}}cast:: {{VALUE:actorLinks}}plot:: {{VALUE:Plot}}!poster
```

## Usage​
It's possible to access whichever JSON variables are sent in response through a `{{VALUE:<variable>}}` tag (e.g. `{{VALUE:Title}}`). Below is an example response for the TV show 'Arcane'.
```
"Title":"Arcane","Year":"2021–","Rated":"TV-14","Released":"06 Nov 2021","Runtime":"N/A","Genre":"Animation, Action, Adventure","Director":"N/A","Writer":"N/A","Actors":"Hailee Steinfeld, Kevin Alejandro, Jason Spisak","Plot":"Set in utopian Piltover and the oppressed underground of Zaun, the story follows the origins of two iconic League champions-and the power that will tear them apart.","Language":"English","Country":"United States, France","Awards":"N/A","Poster":"https://m.media-amazon.com/images/M/MV5BYmU5OWM5ZTAtNjUzOC00NmUyLTgyOWMtMjlkNjdlMDAzMzU1XkEyXkFqcGdeQXVyMDM2NDM2MQ@@._V1_SX300.jpg","Ratings":"Source":"Internet Movie Database","Value":"9.2/10""Metascore":"N/A","imdbRating":"9.2","imdbVotes":"105,113","imdbID":"tt11126994","Type":"series","totalSeasons":"2","Response":"True"
```

  * [Installation
    * Example template




================================================================================

## 10. https://quickadd.obsidian.guide/docs/Examples/Capture_AddTaskToKanbanBoard


This will add a task to the chosen Kanban Board.
In Capture To, select the board.
Select the Task option.
Then select the Insert after option, and write `## ` followed by the name of the lane you want to add the task to.
In my case, I want to add tasks to a lane called `Backlog`, so it becomes `## Backlog`.
If you want, you can experiment with the format syntax - you could, for example, experiment with adding dates and times.
To add a date for a task, you could just write `{{VALUE}} @{{{DATE}}}` in the format syntax. This would add the current date as the date for the card.
You could also use `{{VALUE}} @{{{VDATE:DATE,gggg-MM-DD}}}` to get asked which date you want to input - but do note that this requires the Natural Language Dates plugin.
Read more about format syntax here.


================================================================================

## 11. https://quickadd.obsidian.guide/docs/Choices/MultiChoice


Multi-choices are pretty simple. They're like folders for other choices. Here are mine. They're the ones which you can 'open' and 'close'.
To actually add something in this "folder", you need to drag it in! This is not easy to do when it is the first item in the multi-folder.
Make sure the multi is unfolded (as it is in the screenshot). Click the drag handle of one of the choices you want to add and drag it to just below and to the right of the drag handle for the multi. When successful, the choice will be indented under the multi.


================================================================================

## 12. https://quickadd.obsidian.guide/docs/Examples/Macro_ChangePropertyInDailyNotes


This macro opens a suggester containing all properties in my daily journal note.
When I select one of them, I get prompted to add a value to it.
To use this, you need to change the path to your daily note - as this one only fits those similar to mine.
  1. Change the date format from `gggg-MM-DD - ddd MMM D` to your daily notes' format.
  2. Change the path to the daily note. Mine is in the `bins/daily/` folder - you should change yours such that it matches wherever your daily notes are.


Once you've done this, it'll work!
In case you already know which properties you want to change, and you don't want to get asked about the rest, you could just make an array containing the names of the properties instead. You'd pass that array to the `suggester` method.
```
module.exports=async(params)=>{const{quickAddApi:{inputPrompt, suggester}}= params;const{update, getPropertiesInFile}= app.plugins.plugins["metaedit"].api;const date =window.moment().format("gggg-MM-DD - ddd MMM D");const dailyJournalFilePath =`bins/daily/${date}.md`;const propertiesInDailyJournal =awaitgetPropertiesInFile(dailyJournalFilePath);const targetProp =awaitsuggester(propertiesInDailyJournal.map(p=> p.key), propertiesInDailyJournal);const newPropertyValue =awaitinputPrompt(`Log ${targetProp.key}`, targetProp.content, targetProp.content);awaitupdate(targetProp.key, newPropertyValue, dailyJournalFilePath);
```



================================================================================

## 13. https://quickadd.obsidian.guide/docs/Examples/Macro_MoveNotesWithATagToAFolder


This script allows you to move notes with a certain tag to a folder. 
```
module.exports=asyncfunctionmoveFilesWithTag(params){const{    app,quickAddApi:{ suggester, yesNoPrompt },}= params;const allTags =Object.keys(app.metadataCache.getTags());const tag =awaitsuggester(allTags, allTags);if(!tag)return;const shouldMoveNested =awaityesNoPrompt("Should I move nested tags, too?",`If you say no, I'll only move tags that are strictly equal to what you've chosen. If you say yes, I'll move tags that are nested under ${tag}.`const cache = app.metadataCache.getCachedFiles();let filesToMove =[];  cache.forEach((key)=>{if(key.contains("template"))return;const fileCache = app.metadataCache.getCache(key);let hasFrontmatterCacheTag, hasTag;if(!shouldMoveNested){      hasFrontmatterCacheTag = fileCache.frontmatter?.tags?.split(" ").some((t)=> t === tag.replace("#",""));      hasFrontmatterCacheTag =        hasFrontmatterCacheTag ||        fileCache.frontmatter?.Tags?.split(" ").some((t)=> t === tag.replace("#","")      hasFrontmatterCacheTag =        hasFrontmatterCacheTag ||        fileCache.frontmatter?.tag?.split(" ").some((t)=> t === tag.replace("#",""));      hasFrontmatterCacheTag =        hasFrontmatterCacheTag ||        fileCache.frontmatter?.Tag?.split(" ").some((t)=> t === tag.replace("#","")      hasTag = fileCache?.tags?.some((t)=> t.tag=== tag);}else{      hasFrontmatterCacheTag = fileCache.frontmatter?.tags?.split(" ").some((t)=> t.contains(tag.replace("#","")));      hasFrontmatterCacheTag =        hasFrontmatterCacheTag ||        fileCache.frontmatter?.Tags?.split(" ").some((t)=>.contains(tag.replace("#",""))      hasFrontmatterCacheTag =        hasFrontmatterCacheTag ||        fileCache.frontmatter?.tag?.split(" ").some((t)=> t.contains(tag.replace("#","")));      hasFrontmatterCacheTag =        hasFrontmatterCacheTag ||        fileCache.frontmatter?.Tag?.split(" ").some((t)=>.contains(tag.replace("#",""))      hasTag = fileCache?.tags?.some((t)=> t.tag.contains(tag));if(hasFrontmatterCacheTag || hasTag) filesToMove.push(key);});const folders = app.vault.getAllLoadedFiles().filter((f)=> f.children).map((f)=> f.path);const targetFolder =awaitsuggester(folders, folders);if(!targetFolder)return;for(const file of filesToMove){const tfile = app.vault.getAbstractFileByPath(file);await app.fileManager.renameFile(      tfile,`${targetFolder}/${tfile.name}`
```



================================================================================

## 14. https://quickadd.obsidian.guide/docs/Examples/Capture_FetchTasksFromTodoist



For this capture to work, you will need the Todoist plugin for Obsidian. You will also need to set it up with your API key.
This is very useful for capturing tasks on the go with your phone, and then adding them to Obsidian when you get back to your computer.
You will need to set up a macro with the Todoist Script.
The script has three exports, `SelectFromAllTasks`, `GetAllTasksFromProject`, and `GetAllTasksFromSection`.
  * `SelectFromAllTasks` will prompt you to select tasks from all tasks on your Todoist account,
  * `GetAllTasksFromProject` will prompt you for a project and get all tasks from that project, and
  * `GetAllTasksFromSection` will prompt you for a section and get all tasks from that section.


Personally, I just let QuickAdd ask me which one to execute.
However, when you are entering the user script in the macro, you can add `::GetAllTasksFromProject` (or, `::` followed by any of the other exports) to directly call one of the exported functions.
**IMPORTANT:** If you do _NOT_ want this script to complete tasks in Todoist that you put into your vault, remove the function call to `closeSelectedTasks`.
Now, you will need a Capture choice with the following settings.
  * _Capture To File Name:_ the path to the file where you want to store the tasks.
  * _Capture format:_ Enabled - and in the format, write`{{MACRO:<MACRONAME>}}` where `MACRONAME` is the name of the macro that you made earlier.


The tasks are written in this format: `- [ ] <Task Content> 📆 <YYYY-MM-DD>`
Which equals: `- [ ] Buy groceries 📆 2021-06-27`
This task will be recognized by the Tasks plugin for Obsidian, as well. If there isn't a date set for the task, they'll simply be entered as `- [ ] Buy groceries`.
### Steps​
 _NOTE:_ If you simply follow the process below, you will be asked which export to execute each time. That is fine - if you want to be asked - but you can also make separate Capture choices for each exported function, meaning, it'll execute that function without asking you which one to execute. Just set up the macro as shown in the image above.
  1. Set up the Todoist plugin - grab the API key from your Todoist account. There's a link in the plugin's settings.
  2. Grab the code block from the example and add it to your vault as a javascript file. I'd encourage you to call it something like todoistTaskSync.js to be explicit.
  3. Follow along with what I do in the gif below


### Installation video​

  * Installation video




================================================================================

## 15. https://quickadd.obsidian.guide/docs/Examples/Macro_AddLocationLongLatFromAddress


This is especially useful for the Obsidian Map View plugin.
You can find the script here. Here is a guide to installing user scripts like this one.
  1. Grab the script from this page. This can be done in multiple ways:
    1. By clicking the 'Raw' button, and then saving the 'page' (CTRL+S on Windows, probably command+S on Mac), or
    2. Copying the file contents and saving it as `getLongLatFromAddress.js`. The `.js` is _crucial_.
  2. Save the file to somewhere in your vault. It doesn't matter where, as long as it's in your vault.
  3. Open QuickAdd settings, and then click 'Manage Macros'.
  4. Enter a macro name (I call mine 'Mapper'), and click 'Add macro'.
  5. The macro should appear. Click its 'Configure' button.
  6. There will be 3 input fields. Place your cursor in the one besides 'User Scripts', and it should display a suggester. Assuming you have no other `.js` files in your vault besides the one we just grabbed, it should be the only one shown. Either way, you'll want to click it, and then click 'Add'. It should get added as number 1.
  7. Go back to the QuickAdd main settings. Add a new choice with a name of your choosing. This choice should be a _Macro_ choice, which can be selected using the dropdown next to the 'Add Choice' button. Add this choice, and then
  8. It will appear on the list of choices. Click the ⚙ (gear) button for it, to configure it.
  9. Select the macro you've just created.
  10. Go back out of the QuickAdd settings. You can now run QuickAdd with the `Run QuickAdd` command in the command palette. The Choice you've made should appear.


It adds a YAML property to the active file called `location` with `[lat, long]` as its value given the address you enter.
**Important:** Requires MetaEdit. If you have your edit mode in MetaEdit set to All Multi, do note that you will need to remove the braces on line 23 in the script, so it looks like this: `await createYamlProperty("location", `${lat}, ${lon}`, activeFile);`.


================================================================================

## 16. https://quickadd.obsidian.guide/docs/Examples/Macro_LogBookToDailyJournal


```
// You have to export the function you wish to run.// QuickAdd automatically passes a parameter, which is an object with the Obsidian app object// and the QuickAdd API (see description further ).module.exports=async(params)=>{// Object destructuring. We pull inputPrompt out of the QuickAdd API in params.const{quickAddApi:{ inputPrompt },}= params;// Here, I pull in the update function from the MetaEdit API.const{ update }= app.plugins.plugins["metaedit"].api;// This opens a prompt with the header "📖 Book Name". val will be whatever you enter.const val =awaitinputPrompt("📖 Book Name");// This gets the current date in the specified format.const date =window.moment().format("gggg-MM-DD - ddd MMM D");// Invoke the MetaEdit update function on the Book property in my daily journal note.// It updates the value of Book to the value entered (val).awaitupdate("Book", val,`bins/daily/${date}.md`);
```



================================================================================

## 17. https://quickadd.obsidian.guide/docs/InlineScripts


# Inline scripts
QuickAdd supports the usage of inline scripts in Template choices and Capture choices.
Inline scripts allow you to execute any JavaScript code you want.
You are given the QuickAdd API, just as with user scripts. In inline scripts, it is passed in as `this`, as can be seen in the example below.
```
```js quickaddconst input = await this.quickAddApi.inputPrompt("✍");return `Input given: ${input}`;```
```

When you are making an inline script, remember to write `js quickadd` and not just `js` when denoting the language - otherwise you're just inserting a code snippet.
If you want to insert something, simply `return` it. The return type **must** be a string


================================================================================

## 18. https://quickadd.obsidian.guide/docs/Examples/Template_AddAnInboxItem


Template Path: `bins/templates/Inbox Template.md`
File Name Format: `{{DATE:YYYY-MM-DD-HH-mm-ss}} {{NAME}}`


================================================================================

## 19. https://quickadd.obsidian.guide/docs/FormatSyntax


Template| Description  
---|---  
`{{DATE}}`| Outputs the current date in `YYYY-MM-DD` format. You could write `{{DATE+3}}` to offset the date with 3 days. You can use `+-3` to offset with `-3` days.  
`{{DATE:<DATEFORMAT>}}`| Replace `<DATEFORMAT>` with a Moment.js date format. You could write `{{DATE<DATEFORMAT>+3}}` to offset the date with 3 days.  
`{{VDATE:<variable name>, <date format>}}`| You'll get prompted to enter a date and it'll be parsed to the given date format. You could write 'today' or 'in two weeks' and it'll give you the date for that. Works like variables, so you can use the date in multiple places. **REQUIRES THE NATURAL LANGUAGE DATES PLUGIN!**  
`{{VALUE}}` or `{{NAME}}`| Interchangeable. Represents the value given in an input prompt. If text is selected in the current editor, it will be used as the value. When using the QuickAdd API, this can be passed programmatically using the reserved variable name 'value'.  
`{{VALUE:<variable name>}}`| You can now use variable names in values. They'll get saved and inserted just like values, but the difference is that you can have as many of them as you want. Use comma separation to get a suggester rather than a prompt.  
`{{LINKCURRENT}}`| A link to the file from which the template is activated from. `[[link]]` format.  
`{{MACRO:<MACRONAME>}}`| Execute a macro and write the return value here.  
`{{TEMPLATE:<TEMPLATEPATH>}}`| Include templates in your `format`. Supports Templater syntax.  
`{{MVALUE}}`| Math modal for writing LaTeX. Use CTRL + Enter to submit.  
`{{FIELD:<FIELDNAME>}}`| Suggest the values of `FIELDNAME` anywhere `{{FIELD:FIELDNAME}}` is used. Fields are YAML fields, and the values represent any value this field has in your vault. If there exists no such field or value, you are instead prompted to enter one. This is currently in beta, and the syntax can change—leave your thoughts here.  
`{{selected}}`| The selected text in the current editor. Will be empty if no active editor exists.


================================================================================

## 20. https://quickadd.obsidian.guide/docs/Examples/Macro_Zettelizer



You can get the `.js` file for this userscript here. To install it, you can follow the same process as in the fetch tasks from Todoist example - with video.
## Setup​
You will need to define the folder you want the script to place the new notes in.
This can be done on line 19, where it says `const folder = "..."`. Change the text inside the `""` to match the desired folder path.
Currently, the script _only_ looks for level 3 headers. This means headers with three pound symbols, like so `### header`.
You can freely change this. On line 29 it says `if (heading.level === 3)`. You can change this to any other number, denoting the heading level desired. You can also, rather than checking for equality (`===`), check for other conditions, such as `heading.level >= 1`, which denotes headers of level 1 or greater.
The script looks for headers in your active file with the desired level. If such a header is found, it will ignore the first 'word' (any sequence of characters - i.e., letters, numbers, symbols, etc - followed by a space). Then, it will create a file with a name containing the remaining text in the heading.
In that file, it will link to the heading it created the file from.




================================================================================

## 21. https://quickadd.obsidian.guide/docs/Examples/Macro_TogglManager



This Macro allows you to set preset time entries for Toggl Track.
It uses the Toggl plugin for Obsidian. Make sure that is set up before you continue.
We'll need to install a QuickAdd user script for this to work. I have made a video which shows you how to do so - click here. You will need to put the user script into a new macro and then create a Macro choice in the main menu to activate it. You can find the script here.
## Installation​
  1. Save the script (`togglManager.js`) to your vault somewhere. Make sure it is saved as a JavaScript file, meaning that it has the `.js` at the end.
  2. Open the Macro Manager by opening the QuickAdd plugin settings and clicking `Manage Macros`.
  3. Create a new Macro - you decide what to name it. I named mine `⏳ TogglManager`.
  4. Add the user script to the command list.
  5. Go back out to your QuickAdd main menu and add a new Macro choice. Again, you decide the name. I named mine `⏳ Toggl Manager`. This is what activates the macro.
  6. Attach the Macro to the Macro Choice you just created. Do so by clicking the cog ⚙ icon and selecting it.


Your Macro should look like this:
Your Macro Choice should look like this: 
## Configuration​
You will need to configure your script to match your own settings. I have included some example settings from my own setup, but you'll likely want to make it match your own preferences.
To customize the script, open the JavaScript file you just saved. You'll see this menu setup:
```
const menu ={"🧠 Learning & Skill Development":{// Sub-menu for Learning and Skill DevelopmenttogglProjectName:"Learning & Skill Development",// Name of your corresponding Toggl projectmenuOptions:{"✍ Note Making":"Note Making",// Preset time entry. The left part is what's displayed, and the right part is what Toggl gets."🃏 Spaced Repetition":"Spaced Repetition",// So for this one, I would see '🃏 Spaced Repetition' in my menu, but Toggl would receive 'Spaced Repetition' as the entry."📖 Read Later Processing":"Read Later Processing","👨‍💻 Computer Science & Software Engineering":"Computer Science & Software Engineering","🤴 Personal":{togglProjectName:"Personal",menuOptions:{"🏋️‍♂️ Exercise":"Exercise","🧹 Chores":"Chores","👨‍🔬 Systems Work":"Systems Work","🌀 Weekly Review":"Weekly Review","📆 Monthly Review":"Monthly Review","✔ Planning":"Planning","👨‍🎓 School":{togglProjectName:"School",menuOptions:{"🧠 Machine Intelligence (MI)":"Machine Intelligence (MI)","💾 Database Systems (DBS)":"Database Systems (DBS)","🏃‍♂ Agile Software Engineering (ASE)":"Agile Software Engineering (ASE)","💻 P5":"P5",
```

In the menu, there'll be 3 sub-menus with their own time entries. I have added some comments to explain the anatomy of the menu.
You can customize it however you like. You can add more menus, remove menus, and so on.
  * Installation
  * Configuration




================================================================================

## 22. https://quickadd.obsidian.guide/docs/Misc/AHK_OpenQuickAddFromDesktop



**UPDATE: A more reliable method is to use theGlobal Hotkeys plugin for Obsidian.**
This is an AutoHotkey script which unminimizes/focuses Obsidian and sends some keypresses to it.
I've bound this to my QuickAdd activation hotkey, so this script automatically brings Obsidian to the front of my screen with QuickAdd open.
```
#SingleInstance, ForceSendMode InputSetWorkingDir, %A_ScriptDir%SetTitleMatchMode, RegEx!^+g::  WinActivate, i) Obsidian  ControlSend,, {CtrlDown}{AltDown}{ShiftDown}G{CtrlUp}{CtrlUp}{ShiftUp}, i)ObsidianReturn
```

I'm using CTRL+SHIFT+ALT+G as my shortcut, both in Obsidian and for the AHK script to activate. I use a keyboard shortcut to send those keys (lol, I know - but it's to avoid potential conflicts). Here's a guide to what the `!^+` mean, and how you can customize it: 
#### Update​
If you are willing to install the `Obsidian Advanced URI` plugin, this script is much easier for you to use.
```
SendMode InputSetWorkingDir, %A_ScriptDir%SetTitleMatchMode, RegEx!^+g::  WinActivate, i) Obsidian  Run "obsidian://advanced-uri?vault=<YOUR_VAULT_NAME>&commandname=QuickAdd: Run QuickAdd"Return
```

Simply replace `<YOUR_VAULT_NAME>` with the name of your vault.
**This version is more reliable** , as the other one can fail to activate occasionally.
It uses the same hotkey to activate as above (`CTRL+SHIFT+ALT+G`). If you wish to change it:
  * `!` means `Alt`
  * `^` means `Ctrl`
  * `+` means `Shift`


So, you can replace the `!^+g` with any hotkey of your choosing.


================================================================================

## 23. https://quickadd.obsidian.guide/docs/ManualInstallation


  1. Go to Releases and download the ZIP file from the latest release. The one that looks like `quickadd-x.x.x.zip`.
  2. This ZIP file should be extracted in your Obsidian plugins folder. If you don't know where that is, you can go to `Community Plugins` inside Obsidian. There is a folder icon on the right of `Installed Plugins`. Click that and it opens your plugins folder.
  3. Extract the contents of the ZIP file there.
  4. Now you should have a folder in plugins called 'quickadd' containing a `main.js` file, `manifest.json` file, and a `styles.css` file.




================================================================================

## 24. https://quickadd.obsidian.guide/docs/QuickAddAPI



# QuickAdd API
The API is an interface accessible from scripts, macros and choices.
As of v0.8.0, the API is available for public consumption from just `app.plugins.plugins.quickadd.api`. This means you can use the API methods found below in your Dataviewjs scripts, Templater scripts, and so on.
It is also accessible from within inline scripts and user scripts.
### `inputPrompt(header: string, placeholder?: string, value?: string): Promise<string>`​
Opens a prompt that asks for an input. Returns a string with the input.
This function is asynchronous. You should `await` it.
### `wideInputPrompt: (header: string, placeholder?: string, value?): Promise<string>`​
Opens a wide prompt that asks for an input. Returns a string with the input.
This function is asynchronous. You should `await` it.
### `yesNoPrompt: (header: string, text?: string): Promise<boolean>`​
Opens a prompt asking for confirmation. Returns `true` or `false` based on answer.
This function is asynchronous. You should `await` it.
### `infoDialog: (header: string, text: string[] | string): Promise<void>`​
Opens a dialog showing information the text and an `OK` button. You can pass a single string, which results in a single line, or an array of strings, which will be displayed as multiple lines.
This function is asynchronous. You should `await` it.
### `suggester: (displayItems: string[] | ((value: string, index?: number, arr?: string[]) => string[]), actualItems: string[]): Promise<string>`​
Opens a suggester. Displays the `displayItems`, but you map these the other values with `actualItems`.
The `displayItems` can either be an array of strings, or a map function that will be executed on the actual items.
This means that the following syntax is possible:
```
const pickedFile =await params.quickAddApi.suggester((file)=> file.basename,  params.app.vault.getMarkdownFiles()
```

Returns the selected value.
This function is asynchronous. You should `await` it.
### `checkboxPrompt: (items: string[], selectedItems: string[]): Promise<string[]>`​
Opens a checkbox prompt with the items given. Items in the `selectedItems` array will be selected by default.
Returns an array of the selected items.
This function is asynchronous. You should `await` it.
### `executeChoice(choiceName: string, variables?: {[key: string]: any}): Promise`​
Executes choice with the given name.
You can also pass an optional parameter, `variables`.
The object will be read as variables for the choice to be executed. These variables do _not_ affect the currently set variables. You should view the execution as a new branch, separate from the one executing the macro.
This function is asynchronous. You should `await` it.
#### Example use case for `executeChoice`​
Say you have added a Capture Choice. Now you want to call it from within a script / macro, because you want to execute it repeatedly with different parameters.
Then you'd be able to do something like this:
```
const massiveDataArray =[/* ... */];massiveDataArray.forEach(async(data)=>{await params.quickAddApi.executeChoice('Capture Choice',{X: data.x,Y: data.y,Z: data.z,// ...});});
```

This would execute the choice for each item in the array, passing the data as a variable. This means you can access the variables from within your Capture with `{{VALUE:X}}` (and so on, for each key-value pair in the object).
Additionally, you can use the reserved variable name 'value' to pass a value directly to `{{VALUE}}` or `{{NAME}}` format tags:
```
await params.quickAddApi.executeChoice('My Template Choice',{value:"This text will be used for {{VALUE}} tags",customVar:"This will be available as {{VALUE:customVar}}"});
```

## Utility module​
Given by `api.utility`.
### `getClipboard(): Promise<string>`​
Returns the contents of your clipboard.
This function is asynchronous. You should `await` it.
Syntax: `await quickAddApi.utility.getClipboard();`
### `setClipboard(text: string): Promise`​
Sets the contents of your clipboard to the given input.
This function is asynchronous. You should `await` it.
Syntax: `await quickAddApi.utility.setClipboard();`
## Date module​
Formats always default to `YYYY-MM-DD`.
### `now(format?: string, offset?: number)`​
Gets the current time and formats according to the given format.
Providing an offset will offset the date by number of days. Giving -1 would mean yesterday, and giving 1 would mean tomorrow - and so on.
### `tomorrow(format?: string)`​
Same as `now` but with offset set to 1.
### `yesterday(format?: string)`​
Again, same as `now` but with offset set to -1.
## AI Module​
Given by `api.ai`.
### `prompt(prompt: string, model: Model, settings?: Partial<{variableName: string, shouldAssignVariables: boolean, modelOptions: Partial<OpenAIModelParameters>, showAssistantMessages: boolean, systemPrompt: string}>): Promise<{[key: string]: string}>`​
This function is a part of the AI module and it takes a prompt and a Large Language Model (LLM) to perform an action and return the result. The optional settings parameter is used to control the function's behavior. 
This function is asynchronous. You should `await` it.
The parameters of the function are as follows:
  * `prompt`: A `string`. The prompt that will be passed to the machine learning model.
  * `model`: A `Model`. The machine learning model that will process the prompt. The model could be "gpt-3.5-turbo", "gpt-3.5-turbo-16k", "gpt-4", "gpt-4-32k", or "text-davinci-003".
  * `settings`: An optional `object` with the following keys:
    * `variableName`: A `string`. The name of the output variable. Default is "output".
    * `shouldAssignVariables`: A `boolean`. If set to true, the result of the function will be assigned to the variables of the `choiceExecutor`. Default is `false`.
    * `modelOptions`: An instance of `Partial<OpenAIModelParameters>`. The parameters to be used when interacting with the OpenAI model. Defaults to an empty object.
    * `showAssistantMessages`: A `boolean`. If set to true, messages from the assistant will be shown. Default is `true`.
    * `systemPrompt`: A `string`. The system prompt to be used. Default is your default system prompt, as specified in the AI Assistant settings.


Returns a `Promise` that resolves to the result of the `Prompt` function call. That is an object with the following keys:
  * `output` or your specified `variableName`: A `string`. The output of the machine learning model. 
  * `output-quoted` or your specified `variableName` + `-quoted`: A `string`. The output of the machine learning model, but in a markdown quote.


#### Example use case for `ai.prompt`​
```
const promptText ="What is the capital of France?";const model ="gpt-4";const settings ={variableName:"capital",shouldAssignVariables:true,modelOptions:{temperature:0.6,max_tokens:60,frequency_penalty:0.5,presence_penalty:0.5showAssistantMessages:true,systemPrompt:"Please provide the answer"const response =await api.ai.prompt(promptText, model, settings);
```

In this example, the function will ask the GPT-4 model "What is the capital of France?". The response from the model will be assigned to the variable "capital". The model parameters will be set to a temperature of 0.6, maximum of 60 tokens, frequency penalty of 0.5, and presence penalty of 0.5. Assistant messages will be shown, and the system prompt will be "Please provide the answer".
An example response is:
```
"capital":"The capital of France is [[Paris]].","capital-quoted":"> The capital of France is [[Paris]]."
```

### `getModels(): Model[]`​
Returns an array containing the names of all available LLMs. 
This function is synchronous.
#### Example use case for `ai.getModels`​
```
const models = api.ai.getModels();console.log(models);// Outputs: ["gpt-3.5-turbo", "gpt-3.5-turbo-16k", "gpt-4", "gpt-4-32k", "text-davinci-003"]
```

In this example, the function will return all the available LLMs.
### `getMaxTokens(model: Model): number`​
Returns the maximum number of tokens that the specified model can handle.
This function is synchronous.
  * `model`: A `Model`. The LLM for which the maximum token limit will be returned.


#### Example use case for `ai.getMaxTokens`​
```
const model ="gpt-4";const maxTokens = api.ai.getMaxTokens(model);console.log(maxTokens);// Outputs: Max token limit for the specified model
```

In this example, the function will return the maximum token limit for the GPT-4 model.
### `countTokens(text: string, model: Model): number`​
Counts the number of tokens in the provided text string according to the tokenization rules of the specified model.
This function is synchronous.
  * `text`: A `string`. The text for which the token count will be computed.
  * `model`: A `Model`. The LLM whose tokenization rules will be used.


#### Example use case for `ai.countTokens`​
```
const model ="gpt-4";const text ="This is a sample sentence.";const tokenCount = api.ai.countTokens(text, model);console.log(tokenCount);// Outputs: Token count for the specified sentence
```

In this example, the function will return the token count for the text "This is a sample sentence." according to the GPT-4 model's tokenization rules.
## Obsidian​
The Obsidian API is exposed as well. Accessible through the first parameter in your scripts. For example:
```
module.exports=({obsidian})=>{// obsidian is the API
```

  * `inputPrompt(header: string, placeholder?: string, value?: string): Promise<string>`
  * `wideInputPrompt: (header: string, placeholder?: string, value?): Promise<string>`
  * `yesNoPrompt: (header: string, text?: string): Promise<boolean>`
  * [`infoDialog: (header: string, text: string[] | string): Promise<void>`](https://quickadd.obsidian.guide/docs/QuickAddAPI#infodialog-header-string-text-string--string-promisevoid)
  * [`suggester: (displayItems: string[] | ((value: string, index?: number, arr?: string[]) => string[]), actualItems: string[]): Promise<string>`](https://quickadd.obsidian.guide/docs/QuickAddAPI#suggester-displayitems-string--value-string-index-number-arr-string--string-actualitems-string-promisestring)
  * [`checkboxPrompt: (items: string[], selectedItems: string[]): Promise<string[]>`](https://quickadd.obsidian.guide/docs/QuickAddAPI#checkboxprompt-items-string-selecteditems-string-promisestring)
  * [`executeChoice(choiceName: string, variables?: {[key: string]: any}): Promise`](https://quickadd.obsidian.guide/docs/QuickAddAPI#executechoicechoicename-string-variables-key-string-any-promise)
  * Utility module
    * `getClipboard(): Promise<string>`
    * `setClipboard(text: string): Promise`
  * Date module
    * `now(format?: string, offset?: number)`
    * `tomorrow(format?: string)`
    * `yesterday(format?: string)`
  * AI Module
    * [`prompt(prompt: string, model: Model, settings?: Partial<{variableName: string, shouldAssignVariables: boolean, modelOptions: Partial<OpenAIModelParameters>, showAssistantMessages: boolean, systemPrompt: string}>): Promise<{[key: string]: string}>`](https://quickadd.obsidian.guide/docs/QuickAddAPI#promptprompt-string-model-model-settings-partialvariablename-string-shouldassignvariables-boolean-modeloptions-partialopenaimodelparameters-showassistantmessages-boolean-systemprompt-string-promisekey-string-string)
    * [`getModels(): Model[]`](https://quickadd.obsidian.guide/docs/QuickAddAPI#getmodels-model)
    * `getMaxTokens(model: Model): number`
    * `countTokens(text: string, model: Model): number`
  * Obsidian




================================================================================

## 25. https://quickadd.obsidian.guide/docs/Examples/Template_AutomaticBookNotesFromReadwise



#### Installation​
Here's a video guide for installing user scripts in QuickAdd.
Basically, you'll want to create a new JavaScript file (file extension is `.js`) with the contents of the script. Then, in the script, you see the `YOUR_READWISE_TOKEN`, which is where you'll want to insert your Readwise token (find it here).
Now you need to create a new macro. To do so, open the Macro Manager, enter a name for it (I use `Readwise`), and then click `Add`. Then click `Configure` on that macro. Once a modal opens, select the user script you've created and click `Add`.
Once that's done, you can use the template provided below. If you have your own, then you can just use the `{{MACRO:Readwise::instaFetchBook}}` to insert the highlights. If you called your macro something else than `Readwise`, replace `Readwise` with that.
This template should be added to a Template choice, and should be given values that resemble this: 
The template path should be the path the template made based on the one here.
Notably, the book's name would be the one selected. I have chosen to write prepend a `{ ` before it, as I use this to denote literature notes in my vault.
The remaining settings are up to you. Activating this choice will open a menu which allows you to choose a book, and the book notes will be used appended to the template. You can customize the template as much as you like, but make sure to keep the `{{MACRO:Readwise::instaFetchBook}}`, as that is what gets the highlights (and where they'll be inserted).
#### Script​
Most of the setup is shown in the gif.
```
module.exports={ start, getDailyQuote, instaFetchBook, getBooks };const apiUrl ="https://readwise.io/api/v2/";const books ="📚 Books",  articles ="📰 Articles",  tweets ="🐤 Tweets",  supplementals ="💭 Supplementals",  podcasts ="🎙 Podcasts",  searchAll ="🔍 Search All Highlights (slow!)";const categories ={  books,  articles,  tweets,  supplementals,  podcasts,  searchAll,constrandomNumberInRange=(max)=>Math.floor(Math.random()* max);const token ="YOUR_READWISE_TOKEN";let quickAddApi;asyncfunctionstart(params){({ quickAddApi }= params);let highlights;const category =awaitcategoryPromptHandler();if(!category)return;if(category ==="searchAll"){    highlights =awaitgetAllHighlights();}else{let res =awaitgetHighlightsByCategory(category);if(!res)return;const{ results }= res;const item =await quickAddApi.suggester(      results.map((item)=> item.title),      resultsif(!item)return;    params.variables["author"]=`[[${item.author}]]`;const res2 =awaitgetHighlightsForElement(item);if(!res2)return;    highlights = res2.results.reverse();const textToAppend =awaithighlightsPromptHandler(highlights);return!textToAppend ?"": textToAppend;asyncfunctiongetBooks(params){const{results: books }=awaitgetHighlightsByCategory("books");const bookNames = books.map((book)=> book.title);const selectedBook =await params.quickAddApi.suggester(    bookNames,    bookNames  params.variables["Book Title"]= selectedBook;return selectedBook;asyncfunctioninstaFetchBook(params){const bookTitle = params.variables["Book Title"];if(!bookTitle)returnawaitstart(params);const{results: books }=awaitgetHighlightsByCategory("books");const book = books.find((b)=>    b.title.toLowerCase().contains(bookTitle.toLowerCase())if(!book)thrownewError("Book "+ bookTitle +" not found.");  params.variables["author"]=`[[${book.author}]]`;const highlights =(awaitgetHighlightsForElement(book)).results.reverse();returnwriteAllHandler(highlights);asyncfunctiongetDailyQuote(params){const category ="supplementals";const res =awaitgetHighlightsByCategory(category);if(!res)return;const{ results }= res;const targetItem = results[randomNumberInRange(results.length)];const{results: highlights }=awaitgetHighlightsForElement(targetItem);if(!highlights)return;const randomHighlight = highlights[randomNumberInRange(highlights.length)];const quote =formatDailyQuote(randomHighlight.text, targetItem);return`${quote}`;asyncfunctioncategoryPromptHandler(){const choice =await quickAddApi.suggester(Object.values(categories),Object.keys(categories)if(!choice)returnnull;return choice;asyncfunctionhighlightsPromptHandler(highlights){const writeAll ="Write all highlights to page",    writeOne ="Write one highlight to page";const choices =[writeAll, writeOne];const choice =await quickAddApi.suggester(choices, choices);if(!choice)returnnull;if(choice == writeAll)returnwriteAllHandler(highlights);elsereturnawaitwriteOneHandler(highlights);functionwriteAllHandler(highlights){return highlights.map((hl)=>{if(hl.text=="No title")return;const{ quote, note }=textFormatter(hl.text, hl.note);return`${quote}${note}`;.join("\n\n");asyncfunctionwriteOneHandler(highlights){const chosenHighlight =await quickAddApi.suggester(    highlights.map((hl)=> hl.text),    highlightsif(!chosenHighlight)returnnull;const{ quote, note }=textFormatter(    chosenHighlight.text,    chosenHighlight.notereturn`${quote}${note}`;functionformatDailyQuote(sourceText, sourceItem){let quote = sourceText.split("\n").filter((line)=> line !="").map((line)=>{return`> ${line}`;});const attr =`\n>\\- ${sourceItem.author}, _${sourceItem.title}_`;return`${quote}${attr}`;functiontextFormatter(sourceText, sourceNote){let quote = sourceText.split("\n").filter((line)=> line !="").map((line)=>{if(sourceNote.includes(".h1"))return`## ${line}`;elsereturn`> ${line}`;.join("\n");let note;if(sourceNote.includes(".h1")|| sourceNote ==""||!sourceNote){    note ="";}else{    note ="\n\n"+ sourceNote;return{ quote, note };asyncfunctiongetHighlightsByCategory(category){returnapiGet(`${apiUrl}books`,{ category,page_size:1000});asyncfunctiongetHighlightsForElement(element){returnapiGet(`${apiUrl}highlights`,{book_id: element.id,page_size:1000,});asyncfunctiongetAllHighlights(){constMAX_PAGE_SIZE=1000;constURL=`${apiUrl}highlights`;let promises =[];const{ count }=awaitapiGet(URL);const requestsToMake =Math.ceil(count /MAX_PAGE_SIZE);for(let i =1; i <= requestsToMake; i++){    promises.push(apiGet(URL,{page_size:MAX_PAGE_SIZE,page: i }));const allHighlights =(awaitPromise.all(promises)).map((hl)=> hl.results);return allHighlights;asyncfunctionapiGet(url, data){let finalURL =newURL(url);if(data)Object.keys(data).forEach((key)=>      finalURL.searchParams.append(key, data[key])returnawaitfetch(finalURL,{method:"GET",cache:"no-cache",headers:{"Content-Type":"application/json",Authorization:`Token ${token}`,}).then(async(res)=>await res.json());
```

#### Template​
```
---image:tags: in/booksaliases:- templater_documentationcssclass:---# Title: [[templater_documentation]]## MetadataTags::Type:: [[{]]Author:: {{VALUE:author}}Reference::Rating::Reviewed Date:: [[2025-06-25 - Wed Jun 25]]Finished Year:: [[2025]]# Thoughts# Actions Taken / Changes# Summary of Key Points# Highlights & Notes{{MACRO:Readwise::instaFetchBook}}
```



================================================================================

## 26. https://quickadd.obsidian.guide/assets/files/TodoistScript-016ac3cedee31d57df2df19099f1088e.js

```
module.exports={SelectFromAllTasks:SelectFromAllTasks,GetAllTasksFromProject:GetAllTasksFromProject,GetAllTasksFromSection:GetAllTasksFromSection};const getTodoistPluginApi=t=>t.plugins.plugins["todoist-sync-plugin"].api;async function SelectFromAllTasks(t){const s=await getAllTasks(t);if(0===s.length)return void new Notice("No tasks.");const e=await selectTasks(t,s);return await closeSelectedTasks(t.app,e),formatTasksToTasksPluginTask(e)}async function GetAllTasksFromProject(t){const[s,e]=await Promise.all([getAllTasks(t),getProjects(t.app)]),a=await t.quickAddApi.suggester((t=>(t.tasks=s.filter((s=>s.projectID===t.id)),`${t.name} (${t.tasks.length})`)),e);if(a){if(0!==a.tasks.length)return new Notice(`Added ${a.tasks.length} tasks from '${a.name}'.`),await closeSelectedTasks(t.app,a.tasks),formatTasksToTasksPluginTask(a.tasks);new Notice(`No tasks in '${a.name}'.`)}}async function GetAllTasksFromSection(t){const[s,e,a]=await Promise.all([getProjects(t.app),getSections(t.app),getAllTasks(t)]),n=await t.quickAddApi.suggester((t=>{const e=s.find((s=>s.id===t.project_id));return t.tasks=a.filter((s=>s.sectionID===t.id)),`${e.name} > ${t.name} (${t.tasks.length})`}),e);if(0!==n.tasks.length)return new Notice(`Added ${n.tasks.length} tasks from '${n.name}'.`),await closeSelectedTasks(n.tasks),formatTasksToTasksPluginTask(n.tasks);new Notice(`No tasks in '${n.name}'.`)}async function getAllTasks(t){const s=getTodoistPluginApi(t.app),{ok:e}=await s.getTasks();return e}async function selectTasks(t,s){const e=await t.quickAddApi.checkboxPrompt(s.map((t=>t.content)));return s.filter((t=>e.some((s=>s.contains(t.content)))))}async function closeSelectedTasks(t,s){const e=getTodoistPluginApi(t);s.forEach((async t=>await e.closeTask(t.id)))}function formatTasksToTasksPluginTask(t){return t.map((t=>t=t.rawDatetime?`- [ ] ${t.content} \ud83d\udcc5 ${t.rawDatetime.format("YYYY-MM-DD")}`:`- [ ] ${t.content}`)).join("\n")+"\n"}async function getTasksGroupedByProject(t){const s=getTodoistPluginApi(t),{ok:e}=await s.getTasksGroupedByProject();return e}async function getProjects(t){const s=getTodoistPluginApi(t),{ok:e}=await s.getProjects();return e}async function getSections(t){const s=getTodoistPluginApi(t),{ok:e}=await s.getSections();return e}
```



================================================================================

## 27. https://quickadd.obsidian.guide/assets/files/movies-86507f5b12922d1a3faca11b07d6b883.js

```
const notice=e=>new Notice(e,5e3),log=e=>console.log(e),API_KEY_OPTION="OMDb API Key",API_URL="https://www.omdbapi.com/",IMDB_BASE_URL="https://www.imdb.com/title/";let QuickAdd,Settings;async function start(e,t){QuickAdd=e,Settings=t;const i=await QuickAdd.quickAddApi.inputPrompt("Enter movie title or IMDB ID: ");if(!i)throw notice("No query entered."),new Error("No query entered.");let n;if(isImdbId(i))n=await getByImdbId(i);else{const e=await getByQuery(i),t=await QuickAdd.quickAddApi.suggester(e.map(formatTitleForSuggestion),e);if(!t)throw notice("No choice selected."),new Error("No choice selected.");n=await getByImdbId(t.imdbID)}QuickAdd.variables={...n,imdbUrl:IMDB_BASE_URL+n.imdbID,Released:formatDateString(n.Released),actorLinks:linkifyList(n.Actors.split(",")),genreLinks:linkifyList(n.Genre.split(",")),directorLink:linkifyList(n.Director.split(",")),fileName:replaceIllegalFileNameCharactersInString(n.Title),typeLink:`[[${"movie"===n.Type?"Movies":"Series"}]]`,languageLower:n.Language.toLowerCase()}}function isImdbId(e){return/^tt\d+$/.test(e)}function formatTitleForSuggestion(e){return`(${"movie"===e.Type?"M":"TV"}) ${e.Title} (${e.Year})`}function formatDateString(e){const[t,i,n]=e.split(" "),r=["Jan","Feb","Mar","Apr","May","Jun","Jul","Aug","Sep","Oct","Nov","Dec"].indexOf(i),a=new Date(n,r,t);return`${a.getFullYear()}-${String(a.getMonth()+1).padStart(2,"0")}-${String(a.getDate()).padStart(2,"0")}`}async function getByQuery(e){const t=await apiGet(API_URL,{s:e});if(!t.Search||!t.Search.length)throw notice("No results found."),new Error("No results found.");return t.Search}async function getByImdbId(e){const t=await apiGet(API_URL,{i:e});if(!t)throw notice("No results found."),new Error("No results found.");return t}function linkifyList(e){return 0===e.length?"":1===e.length?`\n - "[[${e[0]}]]"`:e.map((e=>`\n - "[[${e.trim()}]]"`)).join("")}function replaceIllegalFileNameCharactersInString(e){return e.replace(/[\\,#%&\{\}\/*<>$\'\":@]*/g,"")}async function apiGet(e,t){let i=new URL(e);t&&Object.keys(t).forEach((e=>i.searchParams.append(e,t[e]))),i.searchParams.append("apikey",Settings["OMDb API Key"]);const n=await request({url:i.href,method:"GET",cache:"no-cache",headers:{"Content-Type":"application/json"}});return JSON.parse(n)}module.exports={entry:start,settings:{name:"Movie Script",author:"Christian B. B. Houmann",options:{"OMDb API Key":{type:"text",defaultValue:"",placeholder:"OMDb API Key"}}}};
```



================================================================================

## 28. https://quickadd.obsidian.guide/assets/files/getLongLatFromAddress-4eebd21878d6ec1b86eea2835eb14b91.js

```
async function apiGet(e){let t=new URL(`https://nominatim.openstreetmap.org/search?q=${e}&format=json`);return await fetch(t,{method:"GET",cache:"no-cache",headers:{"Content-Type":"application/json"}}).then((async e=>await e.json()))}module.exports=async e=>{const{createYamlProperty:t}=e.app.plugins.plugins.metaedit.api,a=await e.quickAddApi.inputPrompt("\ud83c\udfe0 Address");if(!a)return void new Notice("No address given",5e3);const n=await apiGet(a);if(!n.length)return void new Notice("No results found",5e3);const{lat:i,lon:o}=n[0],c=e.app.workspace.getActiveFile();c?await t("location",`[${i}, ${o}]`,c):new Notice("No active file",5e3)};
```



================================================================================

## 29. https://quickadd.obsidian.guide/assets/files/togglManager-d2a9eee0fc616070330ae8b1e4dda4e4.js

```
let togglApi,quickAddApi,projects;const back="<- Back",menu={"\ud83e\udde0 Learning & Skill Development":{togglProjectName:"Learning & Skill Development",menuOptions:{"\u270d Note Making":"Note Making","\ud83c\udccf Spaced Repetition":"Spaced Repetition","\ud83d\udcd6 Read Later Processing":"Read Later Processing","\ud83d\udc68\u200d\ud83d\udcbb Computer Science & Software Engineering":"Computer Science & Software Engineering"}},"\ud83e\udd34 Personal":{togglProjectName:"Personal",menuOptions:{"\ud83c\udfcb\ufe0f\u200d\u2642\ufe0f Exercise":"Exercise","\ud83e\uddf9 Chores":"Chores","\ud83d\udc68\u200d\ud83d\udd2c Systems Work":"Systems Work","\ud83c\udf00 Weekly Review":"Weekly Review","\ud83d\udcc6 Monthly Review":"Monthly Review","\u2714 Planning":"Planning"}},"\ud83d\udc68\u200d\ud83c\udf93 School":{togglProjectName:"School",menuOptions:{"\ud83e\udde0 Machine Intelligence (MI)":"Machine Intelligence (MI)","\ud83d\udcbe Database Systems (DBS)":"Database Systems (DBS)","\ud83c\udfc3\u200d\u2642 Agile Software Engineering (ASE)":"Agile Software Engineering (ASE)","\ud83d\udcbb P5":"P5"}}};module.exports=async function(e){togglApi=e.app.plugins.plugins["obsidian-toggl-integration"].toggl._apiManager,quickAddApi=e.quickAddApi,projects=await togglApi.getProjects(),openMainMenu(menu)};const dateInSeconds=e=>Math.floor(e/1e3);async function startTimer(e,n){await togglApi.startTimer({description:e,pid:n})}async function openMainMenu(e){const{suggester:n}=quickAddApi,i=Object.keys(e),t=await n(i,i);if(!t)return;const o=e[t];await openSubMenu(o)}async function openSubMenu(e){const{suggester:n}=quickAddApi,i=[...Object.keys(e.menuOptions),back],t=await n(i,i);if(!t)return;if(t===back)return await openMainMenu(menu);startTimer(e.menuOptions[t],projects.find((n=>n.name===e.togglProjectName)).id)}
```



================================================================================

## 30. https://quickadd.obsidian.guide/docs/Examples/Macro_BookFinder



This script allows you to easily insert the details of a book into your vault.
We use Google books api to get the the details. You don't need an API key because we're only exploring publicly available information.
## Installation​
We'll need to install a QuickAdd BookFinder script for this to work. You will need to put the user script into a new macro and then create a Macro choice in the main menu to activate it. You can find the script here.
  1. Save the script (`BookFinder.js`) to your vault somewhere. Make sure it is saved as a JavaScript file, meaning that it has the `.js` at the end.
  2. Create a new template in your designated templates folder. Example template is provided below.
  3. Open the Macro Manager by opening the QuickAdd plugin settings and clicking `Manage Macros`.
  4. Create a new Macro - you decide what to name it. I named mine `BookFinder`.
  5. Add the user script to the command list.
  6. Add a new Template step to the macro. This will be what creates the note in your vault. Settings are as follows:
    1. Set the template path to the template you created.
    2. Enable File Name Format and use `{{VALUE:fileName}}` as the file name format. You can specify this however you like. The `fileName` value is the name of the Book without illegal file name characters.
    3. The remaining settings are for you to specify depending on your needs.
  7. Go back out to your QuickAdd main menu and add a new Macro choice. Again, you decide the name. I named mine `Book`. This is what activates the macro.
  8. Attach the Macro to the Macro Choice you just created. Do so by clicking the cog ⚙ icon and selecting it.


You can now use the macro to create notes with book information in your vault.
### Example template​
```
!poster**Author**:: {{VALUE:authors}}**Title**:: {{VALUE:title}}**Category**::{{VALUE:categories}}**Status**:: 📥**Related Books**### Core Questions for Me### Actions### My Notes## Details{{VALUE:description}}
```

## Usage​
It's possible to access whichever JSON variables are sent in response through a `{{VALUE:<variable>}}` tag (e.g. `{{VALUE:Title}}`). Below is an example response for the Book 'Flowers for Algernon'. **From personal experience this JSON is messy enough that we might want encourage people to extend the JS code to extract additional info**
```
"kind":"books#volumes","totalItems":119,"items":"kind":"books#volume","id":"6P_jN6zUuMcC","etag":"FpDPG4koVaQ","selfLink":"https://www.googleapis.com/books/v1/volumes/6P_jN6zUuMcC","volumeInfo":{"title":"Flowers for Algernon","authors":["Daniel Keyes""publisher":"Houghton Mifflin Harcourt","publishedDate":"2004","description":"Oscar-winning film Charly starring Cliff Robertson and Claire Bloom-a mentally challenged man receives an operation that turns him into a genius...and introduces him to heartache.","industryIdentifiers":["type":"ISBN_13","identifier":"9780156030083""type":"ISBN_10","identifier":"015603008X""readingModes":{"text":false,"image":true"pageCount":324,"printType":"BOOK","categories":["Fiction""averageRating":4,"ratingsCount":179,"maturityRating":"NOT_MATURE","allowAnonLogging":true,"contentVersion":"1.3.3.0.preview.1","panelizationSummary":{"containsEpubBubbles":false,"containsImageBubbles":false"imageLinks":{"smallThumbnail":"http://books.google.com/books/content?id=6P_jN6zUuMcC&printsec=frontcover&img=1&zoom=5&edge=curl&source=gbs_api","thumbnail":"http://books.google.com/books/content?id=6P_jN6zUuMcC&printsec=frontcover&img=1&zoom=1&edge=curl&source=gbs_api""language":"en","previewLink":"http://books.google.ca/books?id=6P_jN6zUuMcC&printsec=frontcover&dq=intitle:Flowers+for+Algernon&hl=&cd=1&source=gbs_api","infoLink":"http://books.google.ca/books?id=6P_jN6zUuMcC&dq=intitle:Flowers+for+Algernon&hl=&source=gbs_api","canonicalVolumeLink":"https://books.google.com/books/about/Flowers_for_Algernon.html?hl=&id=6P_jN6zUuMcC""saleInfo":{"country":"CA","saleability":"NOT_FOR_SALE","isEbook":false"accessInfo":{"country":"CA","viewability":"PARTIAL","embeddable":true,"publicDomain":false,"textToSpeechPermission":"ALLOWED","epub":{"isAvailable":false"pdf":{"isAvailable":true,"acsTokenLink":"http://books.google.ca/books/download/Flowers_for_Algernon-sample-pdf.acsm?id=6P_jN6zUuMcC&format=pdf&output=acs4_fulfillment_token&dl_type=sample&source=gbs_api""webReaderLink":"http://play.google.com/books/reader?id=6P_jN6zUuMcC&hl=&source=gbs_api","accessViewStatus":"SAMPLE","quoteSharingAllowed":false"searchInfo":{"textSnippet":"WINNER OF THE HUGO AWARD AND THE NEBULA AWARD The classic novel that inspired the Academy Award-winning movie Charly Daniel Keyes, the author of eight books, was born in Brooklyn, New York, and received his B.A. and M.A. degrees from ..."
```

  * [Installation
    * Example template




================================================================================

## 31. https://quickadd.obsidian.guide/docs/Advanced/ObsidianUri



QuickAdd choices can be launched from external scripts or apps such as Shortcuts on Mac and iOS, through the use of the `obsidian://quickadd` URI.
```
obsidian://quickadd?choice=<YOUR_CHOICE_NAME>[&value-VALUE_NAME=...]
```

note
All parameter names and values must be properly URL encoded to work. You can use an online tool like urlencoder.org to help you easily encode parts of the URI.
The only required parameter is `choice` which selects the choice to run by its name. The name must match exactly, otherwise it will not be able to be found.
Variables to your choice are passed as additional `value-VARIABLE_NAME` parameters, with `value-` prefixing the name. Variables with a space in their name can still be used, but the spaces in the name must be encoded as `%20` as usual. For example, a capture asking for a variable named `log notes` would be passed as `value-log%20notes=...` in the URI.
Keep in mind that unnamed variables (a bare `{{VALUE}}`/`{{NAME}}` or `{{MVALUE}}`) cannot be filled by the URI and you will instead be prompted inside Obsidian as usual.
## Vault parameter​
Like every Obsidian URI, you can use the special `vault` parameter to specify which vault to run QuickAdd in. If left blank, it will be executed in your most recent vault.
```
obsidian://quickadd?vault=My%20Vault&choice=Daily%20log&value-contents=Lorem%20ipsum.
```

  * Vault parameter




================================================================================

## 32. https://quickadd.obsidian.guide/docs/Advanced/scriptsWithSettings



QuickAdd supports scripts with settings. This allows you to create scripts that can be configured by the user.
Any script with settings will have a ⚙️ button next to the script name in a macro. Clicking the button will open a settings menu for the script.
As an example, see the Movies macro.
## Creating a script with settings​
A script with settings is a JavaScript file that exports an object with two properties: `entry` and `settings`.
The `entry` property is a function that is called when the script is executed. The function is passed two arguments: `QuickAdd` and `settings` (naming is up to you). `QuickAdd` is an object containing the same as what is usually passed to scripts in macros. `settings` is an object containing the settings for the script, as set by the user.
The `settings` property is an object containing the settings for the script. It has three properties: `name`, `author` and `options`.
`name` is the name of the script, as shown in the settings menu.
`author` is the author of the script, as shown in the settings menu.
`options` is an object containing the settings for the script. The keys are the names of the settings, and the values are objects containing the setup parameters for the setting.
For example, the following script will have a text field setting with the key `Text field`, a checkbox setting with the key `Checkbox`, a dropdown setting with the key `Dropdown` and a format setting with the key `Format`. This is shown in the image below.
It's possible to give a description to a setting by adding a `description` property to the setting object.
```
constTEXT_FIELD="Text field";module.exports={entry:async(QuickAdd, settings)=>{// Logic hereconst textFieldSettingValue = settings[TEXT_FIELD];settings:{name:"Demo",author:"Christian B. B. Houmann",options:{[TEXT_FIELD]:{type:"text",defaultValue:"",placeholder:"Placeholder",description:"Description here.","Checkbox":{type:"checkbox",defaultValue:false,"Dropdown":{type:"dropdown",defaultValue:"Option 1",options:"Option 1","Option 2","Option 3","Format":{type:"format",defaultValue:"{{DATE:YYYY-MM-DD}}",placeholder:"Placeholder",
```

## Setting types[​
  * `text` and `input`: A text field.
  * `checkbox` and `toggle`: A checkbox.
  * `dropdown` and `select`: A dropdown.
  * `format`: A format field, adhering to format syntax.


  * Creating a script with settings
  * Setting types




================================================================================

## 33. https://quickadd.obsidian.guide/assets/files/zettelizer-18f874f5b8558ae013bd85477086954b.js

```
module.exports=async e=>{console.log("Starting..."),console.log(e);const o=e.app.workspace.getActiveFile();if(!o)return void new Notice("No active file.");console.log("Found active file: ",o.basename);const a=e.app.metadataCache.getFileCache(o).headings;if(!a)return void new Notice(`No headers in file ${o.name}`);console.log("Found headings in active file: ",a);const i="40 Slipbox/44 Zettels";e.app.vault.adapter.exists(i)?(console.log("Folder does exist: ",i),a.forEach((async a=>{if(console.log(`Checking ${a.heading}. It is level ${a.level}`),3===a.level){const t=a.heading.split(" "),l=t[0].trim(),n=t.length>1?[...t.slice(1)].join(" ").trim():"",s=`${i}/${n.replace(/[\\,#%&\{\}\/*<>$\'\":@]*/g,"")}.md`,c=`![[${o.basename}#${l}${n?" "+n:""}]]`;console.log(`Path: ${s}.\nContent: ${c}`),n&&!await e.app.vault.adapter.exists(s)?await e.app.vault.create(s,c):n&&new Notice(`File ${s} already exists.`,5e3)}})),console.log("Finished!")):new Notice(`Could not find folder ${i}`)};
```



================================================================================

## 34. https://quickadd.obsidian.guide/assets/files/moviescript_settings-08d76309c8e32186648ecd330366f838.jpg




================================================================================

## 35. https://quickadd.obsidian.guide/Docs/FormatSyntax


Template| Description  
---|---  
`{{DATE}}`| Outputs the current date in `YYYY-MM-DD` format. You could write `{{DATE+3}}` to offset the date with 3 days. You can use `+-3` to offset with `-3` days.  
`{{DATE:<DATEFORMAT>}}`| Replace `<DATEFORMAT>` with a Moment.js date format. You could write `{{DATE<DATEFORMAT>+3}}` to offset the date with 3 days.  
`{{VDATE:<variable name>, <date format>}}`| You'll get prompted to enter a date and it'll be parsed to the given date format. You could write 'today' or 'in two weeks' and it'll give you the date for that. Works like variables, so you can use the date in multiple places. **REQUIRES THE NATURAL LANGUAGE DATES PLUGIN!**  
`{{VALUE}}` or `{{NAME}}`| Interchangeable. Represents the value given in an input prompt. If text is selected in the current editor, it will be used as the value. When using the QuickAdd API, this can be passed programmatically using the reserved variable name 'value'.  
`{{VALUE:<variable name>}}`| You can now use variable names in values. They'll get saved and inserted just like values, but the difference is that you can have as many of them as you want. Use comma separation to get a suggester rather than a prompt.  
`{{LINKCURRENT}}`| A link to the file from which the template is activated from. `[[link]]` format.  
`{{MACRO:<MACRONAME>}}`| Execute a macro and write the return value here.  
`{{TEMPLATE:<TEMPLATEPATH>}}`| Include templates in your `format`. Supports Templater syntax.  
`{{MVALUE}}`| Math modal for writing LaTeX. Use CTRL + Enter to submit.  
`{{FIELD:<FIELDNAME>}}`| Suggest the values of `FIELDNAME` anywhere `{{FIELD:FIELDNAME}}` is used. Fields are YAML fields, and the values represent any value this field has in your vault. If there exists no such field or value, you are instead prompted to enter one. This is currently in beta, and the syntax can change—leave your thoughts here.  
`{{selected}}`| The selected text in the current editor. Will be empty if no active editor exists.


================================================================================

## 36. https://quickadd.obsidian.guide/assets/files/BookFinder-f390080e94ba4a7df746b067ec1add78.js

```
const notice=e=>new Notice(e,5e3),log=e=>console.log(e),GOOGLE_BOOKS_API_URL="https://www.googleapis.com/books/v1/volumes",GOOGLE_BOOKS_TITLE_TERM="intitle:";let QuickAdd;function replaceIllegalFileNameCharactersInString(e){return e.replace(/[\\,#%&\{\}\/*<>?$\'\":@]*/g,"")}module.exports=async function(e){QuickAdd=e;let t=await QuickAdd.quickAddApi.utility.getClipboard();const i=await QuickAdd.quickAddApi.inputPrompt("Enter Book title: ",t,t);if(!i)throw new Notice("No title entered.",5e3),new Error("No title entered.");const o=encodeURIComponent("intitle:"+i),l=GOOGLE_BOOKS_API_URL+"?q="+o+"&maxResults=10",n=await fetch(l),a=await n.json();QuickAdd.variables={...a.items[0],title:a.items[0].volumeInfo.title,authors:a.items[0].volumeInfo.authors,categories:a.items[0].volumeInfo.categories,description:a.items[0].volumeInfo.description,fileName:replaceIllegalFileNameCharactersInString(a.items[0].volumeInfo.title),Poster:a.items[0].volumeInfo.imageLinks.smallThumbnail}};
```



================================================================================
