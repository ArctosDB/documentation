---
title: How To Manage Excel for Arctos
layout: default_toc
author: Teresa J. Mayfield-Meyer, Michelle Koo
date: 2023-09-28
---

# How To Manage Excel for Arctos

## Why Use Excel for Arctos?

Excel is a widely used tool for managing data in tables and many people managing data use it as a mechanism for getting data from one system to another. It is often the default tool for opening [.csv](https://en.wikipedia.org/wiki/Comma-separated_values) files (which are the kind of files you get when you download data from Arcots). Excel is user-friendly (mostly) and ubiquitous, almost everyone has access to this program either on their personal computer or on a computer at work. Excel can work for you, but at times it seems like it might be at odds with you. This How To provides insight into ways you can make Excel work better when it comes to uploading data or using downloaded data.

## Uploading Data 

### Dates 

* Enter a date into Excel… 

<img src="../images/classic-uploads/2012/03/screen-shot-2012-03-07-at-11-35-26-am.png"  width="131"
height="84" />

* Leave the field. Evil magic happens. 

<img src="../images/classic-uploads/2012/03/screen-shot-2012-03-07-at-11-35-34-am.png"  width="151" height="91"
sizes="(max-width: 151px) 100vw, 151px"
srcset="../images/classic-uploads/2012/03/screen-shot-2012-03-07-at-11-35-34-am.png 151w, ../images/classic-uploads/2012/03/screen-shot-2012-03-07-at-11-35-34-am-150x91.png 150w" />

* Instead - Format Cells… 

<img src="../images/classic-uploads/2012/03/screen-shot-2012-03-07-at-11-35-46-am.png"  width="304" height="325"
sizes="(max-width: 304px) 100vw, 304px"
srcset="../images/classic-uploads/2012/03/screen-shot-2012-03-07-at-11-35-46-am.png 304w, ../images/classic-uploads/2012/03/screen-shot-2012-03-07-at-11-35-46-am-281x300.png 281w, ../images/classic-uploads/2012/03/screen-shot-2012-03-07-at-11-35-46-am-250x267.png 250w, ../images/classic-uploads/2012/03/screen-shot-2012-03-07-at-11-35-46-am-168x180.png 168w" />

* with a custom date format 

<img src="../images/classic-uploads/2012/03/screen-shot-2012-03-07-at-11-36-25-am.png"  width="543" height="551"
sizes="(max-width: 543px) 100vw, 543px"
srcset="../images/classic-uploads/2012/03/screen-shot-2012-03-07-at-11-36-25-am.png 543w, ../images/classic-uploads/2012/03/screen-shot-2012-03-07-at-11-36-25-am-296x300.png 296w, ../images/classic-uploads/2012/03/screen-shot-2012-03-07-at-11-36-25-am-48x48.png 48w, ../images/classic-uploads/2012/03/screen-shot-2012-03-07-at-11-36-25-am-250x254.png 250w, ../images/classic-uploads/2012/03/screen-shot-2012-03-07-at-11-36-25-am-177x180.png 177w, ../images/classic-uploads/2012/03/screen-shot-2012-03-07-at-11-36-25-am-493x500.png 493w" />

* Everyone is happy! 

<img src="../images/classic-uploads/2012/03/screen-shot-2012-03-07-at-11-36-38-am.png"  width="100" height="102"
sizes="(max-width: 100px) 100vw, 100px"
srcset="../images/classic-uploads/2012/03/screen-shot-2012-03-07-at-11-36-38-am.png 100w, ../images/classic-uploads/2012/03/screen-shot-2012-03-07-at-11-36-38-am-48x48.png 48w" />

### Saving to CSV

When saving from Excel, save as CSV UTF-8 (Comma delimited)(*csv) --  the ```UTF-8``` format is important!

![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Excel/Save_as_csv_utf8.jpg)

### Non-printing Characters (noprint errors)

If you get an error that includes "noprint" this indicates that there is a non-printable character in a field that is described in the rest of the "noprint" quote. These can include non-ASCII characters and trailing or double spaces. Here are some strategies for dealing with data in Excel so that you can clean up or avoid "noprint" errors.

* Use the TRIM function on messy data to remove many non-printable characters.
* Use the "strip junk" option in Arctos if it available.
* Try [this](https://github.com/ArctosDB/documentation-wiki/issues/160#issuecomment-718037471). 

## Downloading Data 

### Non-ASCII Characters

Arctos supports Non-ASCII characters, which makes it nice for [Española Animal Control](https://arctos.database.museum/agent/21254695) but when you download data and open the file in Excel, you get 

`EspaÃ±ola Animal Control`

which isn't exactly useful. Here are two solutions:

#### Import the Data to Excel

Don't just open the CSV with Excel. Do this instead.

1. Open Excel then go to Data Menu
2. Under Get Data, select From Text/CSV.
3. Select the CSV file that you want to open.
4. Select File Origin = 65001: Unicode (UTF-8) from the drop-down list.
5. Select the delimiter, in this case it is comma.
6. Select Data Type Detection = Do not detect data types (This will keep your dates in whatever format they came out!)
7. Select Load to create the Excel data. 

 - adapted from [Microsoft Community Forum Answer](https://answers.microsoft.com/en-us/msoffice/forum/all/how-do-you-openimport-a-csv-file-with-unicode/5614e250-47c4-4577-8638-a809996e2356)

#### Convert the .csv to ANSI

1. On a Windows computer, open the CSV file using Notepad (Tip: change from Text Documents (*.txt) to All Files (*.*) in the file type in order to find your .csv).
2. Click "File > Save As".
3. In the dialog window that appears - select "ANSI" from the "Encoding" field and "All Files (*.*)" from the Save as type field. Then click "Save".
4 . That's all! Open this new CSV file using Excel - your non-ASCII characters should be displayed properly.

 - adapted from [YCBM Knowledgebase](https://support.youcanbook.me/article/502-how-can-i-get-excel-to-properly-display-special-characters-in-the-data-export)

#### Exporting from Excel
Same as import rules: if exporting as an CSV ensure that the format is ```65001: Unicode (UTF-8)```. If you imported in that format, then you are set. If you are starting from XLSX or other format then be sure to select UTF-8 when you Save As 'CSV'

## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_how_to/How-to-Excel-for-Arctos.markdown" target="_blank">here</a>.



