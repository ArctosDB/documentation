---
title: How To Github - Contribute to the Arctos Handbook
layout: default_toc
author: Michelle Koo, Teresa J. Mayfield-Meyer
date: 2018-05-04, 2023-07-26
---
# How To Github - Contribute to the Arctos Handbook

There are four kinds of content on the Arctos Handbook:

* **Best Practices**, which offer details on how experienced collections handle data and workflow decisions
* **Documentation**, which describes specific data tables and/or types and defines data fields
* **How-to Guides**, step-by-step instructions on how to do specific tasks in Arctos
* **Resources**, for tutorials by the Arctos community and teaching guides that use Arctos

Arctos Handbook content can be created or edited by anyone who is a member of the ArctosDB "Users" team on Github (see "[How to Github: Getting Started with GitHub for Arctos](https://handbook.arctosdb.org/how_to/How-to-Use-Github-for-Arctos.html)"). That team has "write" access to the ArctosDB/documentation-wiki repository in GitHub. Anyone can view the content, but you need to be added to the "Users" team by an Arctos administrator in order to make changes. Arctos users who want the ability to create or edit the Handbook or create or Edit Documentation and "How-to Guides" should email arctos-working-group-officers@googlegroups.com with your Arctos login name and Github login to request to be added to the Github Users group.

We encourage Curators/Collection Managers to engage students in writing "How-to Guides." However, students will not be able to post them to the wiki site; instead, they will need to submit the content to a member of the ArctosDB "Users" team (e.g., their supervisor) who can then post the content.

![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Bear%20Pro.jpg) **Pro Tips**

>Documentation pages are written in [Markdown](https://guides.github.com/features/mastering-markdown/), which is dead simple 
to learn. [Here's a cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

## Create New Content

* First, login to GitHub.
* Go to the [documentation-wiki repository](https://github.com/ArctosDB/documentation-wiki/).

Majority of users will be adding to the _How-to_ pages since Documentation is usually reserved for the Arctos Programmers to define the data tables. Below will cover editing and creating content online within your browser (we're using _Chrome_).

To edit offline and more advanced editing, consult [_How to Get the Most Out of Arctos-Github Editing_](https://handbook.arctosdb.org/how_to/How-to-Get-the-Most-from-Arctos-Github-Editing.html#how-to-get-the-most-out-of-arctos-github)

* Enter the directory `_how_to` in the repository
  * if you get lost in the repo, be sure to click on "< > Code " tab to navigate back to the main section
* Press "**Create new file**" in the upper right.
* Give it a name and end it with the extension `.markdown`.  All "How-to Guide" titles should start with "How to .." to distinguish tutorials from other Arctos documentation. 
  - Keep titles short 
  - Avoid punctuation or special characters (e.g., parentheses, commas, colons, dashes, slashes, etc.) because the page title is used to format the URL.
  - **Remember to give your page the `.markdown` extension when naming it!** The extension will automatically place the web editor and most local clients in the right edit mode to assist you.
* In the text box, create your new content. The first lines need to be the front matter which must look like this:

```markdown
---
title: How To Do Anything in Arctos
layout: default_toc
---
```

The Arctos Handbook supports a few other Front Matter attributes. We also support `author` and `date` as an attribute, that, when present, show on the rendered page. An example that (as of this writing) is live on the Handbook site is:

```yaml
---
title: Agents
layout: default_toc
author: ArctosDB
date: 2016-12-01
---
```

As an important note, **if you do not include front matter on your page, the page will fail to compile, and will return a 404 Page Not Found error**. The title you provide is what shows up on the index pages.

* Headers are used for organization and navigation. Start with a title preceded by a single hash (\#). Subsequent sections are given double-hashes (\#\#). Text can be bulleted by single asterisks (\*). Use "Markdown" to format your content (see [Markdown definition](https://en.wikipedia.org/wiki/Markdown) and [Markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet). Click on the help (question mark) icon to get some suggestions for doing headers, lists etc.    

    The important things to remember are:

    1. All paragraphs must have a blank space between them, eg,

        >```md
        > blah blah
        >
        > blah blah new paragraph
        >```

        This is also true when transitioning paragraph types, such as code blocks or blockquotes.

    2. Numbered and bulleted lists are generated automatically. Just start with `1. ` and every subsequent number will iterate (regardless of actual numerical progression, so 1, 1, 1 will become 1, 2, 3). Bullets can be a single asterisk or a dash.

    3. Table-of-Contents entries are generated at headers. Headers are created by leading with one or more `#`. For example:

        >```md
        > # Page title
        >
        > This is a page about stuff and things
        >
        > ## First subheading
        >
        > This is actually a really interesting topic.
        >
        > ### Sub-subheading
        >
        > You see, ....
        >
        > ## Second subheading
        >```

        Note that simply *emphasized text* (via `*emphasized text*`) nor **bold text** (via `**bold text**`) will generate either a table of contents entry or an HTML anchor to link to. ***Do not simply use bold text for sections!!***

* To add an image, see below.   
* Save the page!
* Pages will dynamically appear on the How to Index page and be searchable on the Arctos Handbook site now.
  - If you edited a documentation page, the update will not be automatic; if you're comfortable editing HTML directly, you can insert it into the appropriate index page (eg, for a page in `_documentation`, the `_documentation/index.html` file), or otherwise ask dustymc@gmail.com, mkoo@berkeley.edu, or ccicero@berkeley.edu to take care of it for you.

### Edit Existing Content

* Login to GitHub.
* Go to the [documentation-wiki repository](https://github.com/ArctosDB/documentation-wiki/wiki)., main Code tab
* Find the page you want to edit by clicking on Find File next to the Clone or Download button. Type key words next to the documentation-wiki prompt. IMPORTANT: separate words with hyphens for the search to find titles correctly, e.g.
  "how-to-edit-documentation"
*Select the file you have chosen
* Click on "Edit" in the upper right.
* Make your changes on the page. DO NOT EDIT a title because that will change the URL and thus affect linked pages.
* Save the page!


## General notes

### Relative links

When creating relative links, Github Markdown will recognize the following:

```md
Link to [this here page](/how_to/page.html)
```
and form a URL relative to the site's base url. Ours is 'https://handbook.arctosdb.org'

### Titles

**DO NOT EDIT** an existing title because that will change the URL and thus affect linked pages.

### Add a Table

In the page where you want to insert a table, follow the guide for [Organizing Data into Tables in Github](https://help.github.com/articles/organizing-information-with-tables)


### Add Images

- Give the image a URL: In a new tab, go to the [documentation-wiki `uploads` folder](https://github.com/ArctosDB/documentation-wiki/tree/gh-pages/images/uploads), and click the "upload files" button.
  - If you want to use the same tab, be sure to commit your progress, first.
- Drag and drop the image or browse your computer for the image(s) and click the "commit changes" button.
- Click on the desired image to preview it
- Click on the "Download" button to get the raw URL. **If the URL does not begin with `https://raw.githubusercontent.com`, the link *will not work*.** Copy this URL to your clipboard.
- Go to back to the page where you want to add the image, and click on the image icon above the text box. Insert the URL. Only the URL (not the image) will show up in the text box. In raw Markdown, you can specify an image with `![](URL_OF_IMAGE_HERE)`.
- Hit the preview button to ensure you've correctly included the image
- Commit your changes

### Add Videos

* Create a YouTube Video using the Arctos login: arctos.database@gmail.com.
* Email the database administrator for the password.
* Add the link to the page.

![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Bear%20Pro.jpg) **Pro Tip**
## Text editors

If you want to work on markdown content offline or just not in a browser, there are a number of great text editors to use. Here are some FREE favorites:    

* [Atom](https://atom.io/) (PC, MacOS, Linux, free)
* [Brackets](http://brackets.io/) (MacOS, PC, free from Adobe)
* [Notepad ++](https://notepad-plus-plus.org/) (PC, free)
* [Text Wrangler](http://www.barebones.com/products/textwrangler/) (MacOS, free)


Try using [Github Desktop](https://desktop.github.com/) if you want to sync your work with the [documentation-wiki repository](https://github.com/ArctosDB/documentation-wiki/) locally. For more details, consult [_How to Get the Most Out of Arctos-Github Editing_](/how_to/How-to-Get-the-Most-from-Arctos-Github-Editing.markdown).

#### Search Terms
create documentation  
edit documentation  
create How To  
edit How To  

## Video Tutorials
[Make a quick edit to a How To](https://youtu.be/vj9HQylTiA0)

## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_how_to/How-to-Contribute-Content-to-Arctos-Handbook.markdown" target="_blank">here</a>.
