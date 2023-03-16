Markdown and Visual Studio Code
===============================

Working with Markdown files in Visual Studio Code is simple, straightforward, and fun. Besides VS Code's basic editing, there are a number of Markdown specific features that will help you be more productive.

Markdown extensions[#](https://code.visualstudio.com/docs/languages/markdown#_markdown-extensions)
--------------------------------------------------------------------------------------------------

In addition to the functionality VS Code provides out of the box, you can install an extension for greater functionality.

[![markdownlint](https://davidanson.gallerycdn.vsassets.io/extensions/davidanson/vscode-markdownlint/0.47.0/1648872337042/Microsoft.VisualStudio.Services.Icons.Default)markdownlint3.9MDavidAnsonMarkdown linting and style checking for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)[![Markdown Theme Kit](https://ms-vscode.gallerycdn.vsassets.io/extensions/ms-vscode/theme-markdownkit/0.1.4/1499504007109/Microsoft.VisualStudio.Services.Icons.Default)Markdown Theme Kit367.9Kms-vscodeTheme Kit for VS Code optimized for Markdown. Based on the TextMate themes.](https://marketplace.visualstudio.com/items?itemName=ms-vscode.Theme-MarkdownKit)[![Markdown Shortcuts](https://mdickin.gallerycdn.vsassets.io/extensions/mdickin/markdown-shortcuts/0.12.0/1573402114639/Microsoft.VisualStudio.Services.Icons.Default)Markdown Shortcuts187.0KmdickinShortcuts for Markdown editing](https://marketplace.visualstudio.com/items?itemName=mdickin.markdown-shortcuts)[![Print](https://pdconsec.gallerycdn.vsassets.io/extensions/pdconsec/vscode-print/0.9.26/1658321679678/Microsoft.VisualStudio.Services.Icons.Default)Print84.4KpdconsecRendered Markdown, coloured code.](https://marketplace.visualstudio.com/items?itemName=pdconsec.vscode-print)

> Tip: Click on an extension tile above to read the description and reviews to decide which extension is best for you. See more in the [Marketplace](https://marketplace.visualstudio.com/).

Markdown preview[#](https://code.visualstudio.com/docs/languages/markdown#_markdown-preview)
--------------------------------------------------------------------------------------------

VS Code supports Markdown files out of the box. You just start writing Markdown text, save the file with the .md extension and then you can toggle the visualization of the editor between the code and the preview of the Markdown file; obviously, you can also open an existing Markdown file and start working with it. To switch between views, press Ctrl+Shift+V in the editor. You can view the preview side-by-side (Ctrl+K V) with the file you are editing and see changes reflected in real-time as you edit.

Here is an example with a very simple file.

![Markdown Preview](https://code.visualstudio.com/assets/docs/languages/Markdown/preview.png)

> **Tip:** You can also right-click on the editor Tab and select **Open Preview** (Ctrl+Shift+V) or use the **Command Palette** (Ctrl+Shift+P) to run the **Markdown: Open Preview to the Side** command (Ctrl+K V).

### Dynamic previews and preview locking[#](https://code.visualstudio.com/docs/languages/markdown#_dynamic-previews-and-preview-locking)

By default, Markdown previews automatically update to preview the currently active Markdown file:

![The preview automatically switching to preview the current Markdown document](https://code.visualstudio.com/assets/docs/languages/Markdown/md-dynamic-preview.gif)

You can lock a Markdown preview using the **Markdown: Toggle Preview Locking** command to keep it locked to its current Markdown document. Locked previews are indicated by **[Preview]** in the title:

![A locked Markdown preview](https://code.visualstudio.com/assets/docs/languages/Markdown/locked-preview-title.png)

### Editor and preview synchronization[#](https://code.visualstudio.com/docs/languages/markdown#_editor-and-preview-synchronization)

VS Code automatically synchronizes the Markdown editor and the preview panes. Scroll the Markdown preview and the editor is scrolled to match the preview's viewport. Scroll the Markdown editor and the preview is scrolled to match its viewport:

![Markdown Preview editor selection scroll sync](https://code.visualstudio.com/assets/docs/languages/Markdown/preview-scroll-sync.gif)

You can disable scroll synchronization using the `markdown.preview.scrollPreviewWithEditor` and `markdown.preview.scrollEditorWithPreview` [settings](https://code.visualstudio.com/docs/getstarted/settings).

The currently selected line in the editor is indicated in the Markdown preview by a light gray bar in the left margin:

![Markdown Preview editor line marker](https://code.visualstudio.com/assets/docs/languages/Markdown/preview-selection-marker.png)

Additionally, double clicking an element in the Markdown preview will automatically open the editor for the file and scroll to the line nearest the clicked element.

![Markdown Preview double click switches to editor](https://code.visualstudio.com/assets/docs/languages/Markdown/double-click-preview-switch.gif)

Outline view[#](https://code.visualstudio.com/docs/languages/markdown#_outline-view)
------------------------------------------------------------------------------------

The Outline view is a separate section in the bottom of the File Explorer. When expanded, it will show the symbol tree of the currently active editor. For Markdown files, the symbol tree is the Markdown file's header hierarchy.

![Markdown Outline view](https://code.visualstudio.com/assets/docs/languages/Markdown/markdown-outline-view.png)

The Outline view is a great way to review your document's header structure and outline.

Extending the Markdown preview[#](https://code.visualstudio.com/docs/languages/markdown#_extending-the-markdown-preview)
------------------------------------------------------------------------------------------------------------------------

Extensions can contribute custom styles and scripts to the Markdown preview to change its appearance and add new functionality. Here's a set of example extensions that customize the preview:

[![Markdown Preview Github Styling](https://bierner.gallerycdn.vsassets.io/extensions/bierner/markdown-preview-github-styles/1.0.1/1642545629948/Microsoft.VisualStudio.Services.Icons.Default)Markdown Preview Github Styling730.6KbiernerChanges VS Code's built-in markdown preview to match Github's style](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-preview-github-styles)[![Markdown Emoji](https://bierner.gallerycdn.vsassets.io/extensions/bierner/markdown-emoji/0.3.0/1657843376933/Microsoft.VisualStudio.Services.Icons.Default)Markdown Emoji299.5KbiernerAdds emoji syntax support to VS Code's built-in markdown preview and markdown cells in notebook](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-emoji)[![Markdown+Math](https://goessner.gallerycdn.vsassets.io/extensions/goessner/mdmath/2.7.4/1622978497071/Microsoft.VisualStudio.Services.Icons.Default)Markdown+Math211.2KgoessnerLaTeX Math for Markdown ... with macros and more](https://marketplace.visualstudio.com/items?itemName=goessner.mdmath)[![Markdown Preview with Bitbucket Styles](https://hbrok.gallerycdn.vsassets.io/extensions/hbrok/markdown-preview-bitbucket/1.0.0/1517363154766/Microsoft.VisualStudio.Services.Icons.Default)Markdown Preview with Bitbucket Styles10.3KhbrokReplaces the Markdown preview with Bitbucket styles.](https://marketplace.visualstudio.com/items?itemName=hbrok.markdown-preview-bitbucket)

### Using your own CSS[#](https://code.visualstudio.com/docs/languages/markdown#_using-your-own-css)

You can also use your own CSS in the Markdown preview with the `"markdown.styles": []` [setting](https://code.visualstudio.com/docs/getstarted/settings). This lists URLs for style sheets to load in the Markdown preview. These stylesheets can either be `https` URLs, or relative paths to local files in the current workspace.

For example, to load a stylesheet called `Style.css` at the root of your current workspace, use **File** > **Preferences** > **Settings** to bring up the workspace `settings.json` file and make this update:

```
<code style="box-sizing: border-box; font-family: Menlo, Monaco, Consolas, &quot;Courier New&quot;, monospace !important; font-size: inherit; padding: 0px; color: inherit; background-color: transparent; border-radius: 0px; white-space: pre-wrap; tab-size: 2;">// Place your settings in this file to overwrite default and user settings.
{
  "markdown.styles": ["Style.css"]
}</code>
```

### Keep trailing whitespace in order to create line breaks[#](https://code.visualstudio.com/docs/languages/markdown#_keep-trailing-whitespace-in-order-to-create-line-breaks)

To create [hard line breaks](https://spec.commonmark.org/0.29/#hard-line-breaks), Markdown requires two or more spaces at the end of a line. Depending on your user or workspace settings, VS Code may be configured to remove trailing whitespace. In order to keep trailing whitespace in Markdown files only, you can add these lines to your `settings.json`:

```
<code style="box-sizing: border-box; font-family: Menlo, Monaco, Consolas, &quot;Courier New&quot;, monospace !important; font-size: inherit; padding: 0px; color: inherit; background-color: transparent; border-radius: 0px; white-space: pre-wrap; tab-size: 2;">{
  "[markdown]": {
  "files.trimTrailingWhitespace": false
 }
}</code>
```

Markdown preview security[#](https://code.visualstudio.com/docs/languages/markdown#_markdown-preview-security)
--------------------------------------------------------------------------------------------------------------

For security reasons, VS Code restricts the content displayed in the Markdown preview. This includes disabling script execution and only allowing resources to be loaded over `https`.

When the Markdown preview blocks content on a page, an alert popup is shown in the top right corner of the preview window:

![Markdown security alert](https://code.visualstudio.com/assets/docs/languages/Markdown/security-alert.png)

You can change what content is allowed in the Markdown preview by clicking on this popup or running the **Markdown: Change preview security settings** command in any Markdown file:

![Markdown security selector](https://code.visualstudio.com/assets/docs/languages/Markdown/security-selector.png)

The Markdown preview security settings apply to all files in the workspace.

Here are the details about each of these security levels:

### Strict[#](https://code.visualstudio.com/docs/languages/markdown#_strict)

This is the default setting. Only loads trusted content and disables script execution. Blocks `http` images.

It is strongly recommended that you keep `Strict` security enabled unless you have a very good reason to change it AND you trust all Markdown files in the workspace.

### Allow insecure content[#](https://code.visualstudio.com/docs/languages/markdown#_allow-insecure-content)

Keeps scripts disabled but allows content to be loaded over `http`.

### Disable[#](https://code.visualstudio.com/docs/languages/markdown#_disable)

Disables additional security in the preview window. This allows script execution and also allows content to be loaded over `http`.

Snippets for Markdown[#](https://code.visualstudio.com/docs/languages/markdown#_snippets-for-markdown)
------------------------------------------------------------------------------------------------------

There are several built-in Markdown snippets included in VS Code - press Ctrl+Space (Trigger Suggest) and you get a context specific list of suggestions.

> **Tip:** You can add in your own User Defined Snippets for Markdown. Take a look at [User Defined Snippets](https://code.visualstudio.com/docs/editor/userdefinedsnippets) to find out how.

Compiling Markdown into HTML[#](https://code.visualstudio.com/docs/languages/markdown#_compiling-markdown-into-html)
--------------------------------------------------------------------------------------------------------------------

VS Code integrates with Markdown compilers through the integrated [task runner](https://code.visualstudio.com/docs/editor/tasks). We can use this to compile `.md` files into `.html` files. Let's walk through compiling a simple Markdown document.

### Step 1: Install a Markdown compiler[#](https://code.visualstudio.com/docs/languages/markdown#_step-1-install-a-markdown-compiler)

For this walkthrough, we use the popular [Node.js](https://nodejs.org/) module, [markdown-it](https://github.com/markdown-it/markdown-it).

```
<code style="box-sizing: border-box; font-family: Menlo, Monaco, Consolas, &quot;Courier New&quot;, monospace !important; font-size: inherit; padding: 0px; color: inherit; background-color: transparent; border-radius: 0px; white-space: pre-wrap; tab-size: 2;">npm install -g markdown-it</code>
```

> **Note:** There are many Markdown compilers to choose from beyond **markdown-it**. Pick the one that best suits your needs and environment.

### Step 2: Create a simple MD file[#](https://code.visualstudio.com/docs/languages/markdown#_step-2-create-a-simple-md-file)

Open VS Code on an empty folder and create a `sample.md` file.

> **Note:** You can open a folder with VS Code by either selecting the folder with **File** > **Open Folder** or navigating to the folder and typing 'code .' at the command line.

Place the following source code in that file:

```
<code style="box-sizing: border-box; font-family: Menlo, Monaco, Consolas, &quot;Courier New&quot;, monospace !important; font-size: inherit; padding: 0px; color: inherit; background-color: transparent; border-radius: 0px; white-space: pre-wrap; tab-size: 2;"># Hello Markdown in VS Code!

This is a simple introduction to compiling Markdown in VS Code.

Things you'll need:

* [Node.js](https://nodejs.org)
* [markdown-it](https://www.npmjs.com/package/markdown-it)
* [tasks.json](/docs/editor/tasks)

## Section Title

> This block quote is here for your information.</code>
```

### Step 3: Create tasks.json[#](https://code.visualstudio.com/docs/languages/markdown#_step-3-create-tasksjson)

The next step is to set up the task configuration file `tasks.json`. To do this, run **Terminal** > **Configure Tasks** and click **Create tasks.json file from templates**. VS Code then presents a list of possible `tasks.json` templates to choose from. Select **Others** since we want to run an external command.

This generates a `tasks.json` file in your workspace `.vscode` folder with the following content:

```
<code style="box-sizing: border-box; font-family: Menlo, Monaco, Consolas, &quot;Courier New&quot;, monospace !important; font-size: inherit; padding: 0px; color: inherit; background-color: transparent; border-radius: 0px; white-space: pre-wrap; tab-size: 2;">{
  // See https://go.microsoft.com/fwlink/?LinkId=733558
  // for the documentation about the tasks.json format
  "version": "2.0.0",
  "tasks": [
 {
  "label": "echo",
  "type": "shell",
  "command": "echo Hello"
 }
 ]
}</code>
```

To use **markdown-it** to compile the Markdown file, change the contents as follows:

```
<code style="box-sizing: border-box; font-family: Menlo, Monaco, Consolas, &quot;Courier New&quot;, monospace !important; font-size: inherit; padding: 0px; color: inherit; background-color: transparent; border-radius: 0px; white-space: pre-wrap; tab-size: 2;">{
  // See https://go.microsoft.com/fwlink/?LinkId=733558
  // for the documentation about the tasks.json format
  "version": "2.0.0",
  "tasks": [
 {
  "label": "Compile Markdown",
  "type": "shell",
  "command": "markdown-it sample.md -o sample.html",
  "group": "build"
 }
 ]
}</code>
```

> **Tip:** While the sample is there to help with common configuration settings, IntelliSense is available for the `tasks.json` file as well to help you along. Use Ctrl+Space to see the available settings.

### Step 4: Run the Build Task[#](https://code.visualstudio.com/docs/languages/markdown#_step-4-run-the-build-task)

Since there can be more than one build task in more complex environments, we prompt you to pick the task to execute after pressing Ctrl+Shift+B (**Run Build Task**). In addition, we allow you to scan the output for compile problems. Since we only want to convert the Markdown file to HTML, select **Never scan the build output** from the presented list.

At this point, you should see an additional file show up in the file list `sample.html`.

If you want to make the **Compile Markdown** task the default build task to run, execute **Configure Default Build Task** from the global **Terminal** menu and select **Compile Markdown** from the presented list. The final `tasks.json` file will then look like this:

```
<code style="box-sizing: border-box; font-family: Menlo, Monaco, Consolas, &quot;Courier New&quot;, monospace !important; font-size: inherit; padding: 0px; color: inherit; background-color: transparent; border-radius: 0px; white-space: pre-wrap; tab-size: 2;">{
  // See https://go.microsoft.com/fwlink/?LinkId=733558
  // for the documentation about the tasks.json format
  "version": "2.0.0",
  "tasks": [
 {
  "label": "Compile Markdown",
  "type": "shell",
  "command": "markdown-it sample.md -o sample.html",
  "problemMatcher": [],
  "group": {
  "kind": "build",
  "isDefault": true
 }
 }
 ]
}</code>
```

Automating Markdown compilation[#](https://code.visualstudio.com/docs/languages/markdown#_automating-markdown-compilation)
--------------------------------------------------------------------------------------------------------------------------

Let's take things a little further and automate Markdown compilation with VS Code. We can do so with the same task runner integration as before, but with a few modifications.

### Step 1: Install Gulp and some plug-ins[#](https://code.visualstudio.com/docs/languages/markdown#_step-1-install-gulp-and-some-plugins)

We use [Gulp](https://gulpjs.com/) to create a task that automates Markdown compilation. We also use the [gulp-markdown](https://www.npmjs.com/package/gulp-markdown) plug-in to make things a little easier.

We need to install gulp both globally (`-g` switch) and locally:

```
<code style="box-sizing: border-box; font-family: Menlo, Monaco, Consolas, &quot;Courier New&quot;, monospace !important; font-size: inherit; padding: 0px; color: inherit; background-color: transparent; border-radius: 0px; white-space: pre-wrap; tab-size: 2;">npm install -g gulp
npm install gulp gulp-markdown-it</code>
```

> **Note:** gulp-markdown-it is a Gulp plug-in for the **markdown-it** module we were using before. There are many other Gulp Markdown plug-ins you can use, as well as plug-ins for Grunt.

You can test that your gulp installation was successful by typing `gulp -v`. You should see a version displayed for both the global (CLI) and local installations.

### Step 2: Create a simple Gulp task[#](https://code.visualstudio.com/docs/languages/markdown#_step-2-create-a-simple-gulp-task)

Open VS Code on the same folder from before (contains `sample.md` and `tasks.json` under the `.vscode` folder), and create `gulpfile.js` at the root.

Place the following source code in that file:

```
<code style="box-sizing: border-box; font-family: Menlo, Monaco, Consolas, &quot;Courier New&quot;, monospace !important; font-size: inherit; padding: 0px; color: inherit; background-color: transparent; border-radius: 0px; white-space: pre-wrap; tab-size: 2;">var  gulp = require('gulp');
var  markdown = require('gulp-markdown-it');

gulp.task('markdown', function() {
  return  gulp
 .src('**/*.md')
 .pipe(markdown())
 .pipe(
  gulp.dest(function(f) {
  return  f.base;
 })
 );
});

gulp.task('default', function() {
  return  gulp.watch('**/*.md', gulp.series(['markdown']));
});</code>
```

What is happening here?

1.  We are watching for changes to any Markdown file in our workspace, i.e. the current folder open in VS Code.
2.  We take the set of Markdown files that have changed, and run them through our Markdown compiler, `gulp-markdown-it`.
3.  We now have a set of HTML files, each named respectively after their original Markdown file. We then put these files in the same directory.

### Step 3: Run the gulp default Task[#](https://code.visualstudio.com/docs/languages/markdown#_step-3-run-the-gulp-default-task)

To complete the tasks integration with VS Code, we will need to modify the task configuration from before to run the default Gulp task we just created. You can either delete the `tasks.json` file or empty it, only keeping the `"version": "2.0.0"` property. Now execute **Run Task** from the global **Terminal** menu. Observe that you are presented with a picker listing the tasks defined in the gulp file. Select **gulp: default** to start the task. We allow you to scan the output for compile problems. Since we only want to convert the Markdown file to HTML, select **Never scan the build output** from the presented list. At this point, if you create and/or modify other Markdown files, you see the respective HTML files generated and/or changes reflected on save. You can also enable [Auto Save](https://code.visualstudio.com/docs/editor/codebasics#_save-auto-save) to make things even more streamlined.

If you want to make the **gulp: default** task the default build task executed when pressing Ctrl+Shift+B, run **Configure Default Build Task** from the global **Terminal** menu and select **gulp: default** from the presented list. The final `tasks.json` file will then look like this:

```
<code style="box-sizing: border-box; font-family: Menlo, Monaco, Consolas, &quot;Courier New&quot;, monospace !important; font-size: inherit; padding: 0px; color: inherit; background-color: transparent; border-radius: 0px; white-space: pre-wrap; tab-size: 2;">{
  // See https://go.microsoft.com/fwlink/?LinkId=733558
  // for the documentation about the tasks.json format
  "version": "2.0.0",
  "tasks": [
 {
  "type": "gulp",
  "task": "default",
  "problemMatcher": [],
  "group": {
  "kind": "build",
  "isDefault": true
 }
 }
 ]
}</code>
```

### Step 4: Terminate the gulp default Task[#](https://code.visualstudio.com/docs/languages/markdown#_step-4-terminate-the-gulp-default-task)

The **gulp: default** task runs in the background and watches for file changes to Markdown files. If you want to stop the task, you can use **Terminate Task** from the global **Terminal** menu.

Next steps[#](https://code.visualstudio.com/docs/languages/markdown#_next-steps)
--------------------------------------------------------------------------------

Read on to find out about:

-   [CSS, SCSS, and Less](https://code.visualstudio.com/docs/languages/css) - Want to edit your CSS? VS Code has great support for CSS, SCSS, and Less editing.

Common questions[#](https://code.visualstudio.com/docs/languages/markdown#_common-questions)
--------------------------------------------------------------------------------------------

### Is there spell checking?[#](https://code.visualstudio.com/docs/languages/markdown#_is-there-spell-checking)

Not installed with VS Code but there are spell checking extensions. Check the [VS Code Marketplace](https://marketplace.visualstudio.com/vscode) to look for useful extensions to help with your workflow.

### Does VS Code support GitHub Flavored Markdown?[#](https://code.visualstudio.com/docs/languages/markdown#_does-vs-code-support-github-flavored-markdown)

No, VS Code targets the [CommonMark](https://commonmark.org/) Markdown specification using the [markdown-it](https://github.com/markdown-it/markdown-it) library. GitHub is moving toward the CommonMark specification, which you can read about in this [update](https://github.blog/2017-03-14-a-formal-spec-for-github-markdown/).

### In the walkthrough above, I didn't find the Configure Task command in the Command Palette?[#](https://code.visualstudio.com/docs/languages/markdown#_in-the-walkthrough-above-i-didnt-find-the-configure-task-command-in-the-command-palette)

You may have opened a file in VS Code rather than a folder. You can open a folder by either selecting the folder with **File** > **Open Folder** or navigating to the folder and typing 'code .' at the command line.

<form aria-label="Feedback" style="box-sizing: border-box; font-family: &quot;Segoe UI&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif;">

### Was this documentation helpful?

<button value="1" style="box-sizing: border-box; font-family: &quot;Segoe UI&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif; margin: 0px 5px 0px 0px; font-style: inherit; font-variant: inherit; font-weight: 600; font-stretch: inherit; font-size: 1.4rem; line-height: inherit; color: rgb(255, 255, 255); overflow: visible; text-transform: none; appearance: button; cursor: pointer; border: 1px solid rgb(255, 255, 255); padding: 5px 20px; display: inline-block; background-color: rgb(0, 102, 184);">Yes, this page was helpful</button><button value="0" style="box-sizing: border-box; font-family: &quot;Segoe UI&quot;, &quot;Helvetica Neue&quot;, Helvetica, Arial, sans-serif; margin: 0px 5px 0px 0px; font-style: inherit; font-variant: inherit; font-weight: 600; font-stretch: inherit; font-size: 1.4rem; line-height: inherit; color: rgb(255, 255, 255); overflow: visible; text-transform: none; appearance: button; cursor: pointer; border: 1px solid rgb(255, 255, 255); padding: 5px 20px; display: inline-block; background-color: rgb(0, 102, 184);">No, this page was not helpful</button></form>

7/7/2022