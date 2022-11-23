---
title: Reports
author: ArctosDB
date: 2022-09-30
layout: default_toc
---

# Reports

Arctos has a built-in user-customizable reporter. It's pretty great.

## Language

The reporter uses CFML, HTML, and CSS, generally to produce PDF's through a browsers print-to-PDF functionality. Extensive documentation for each of these languages is widely available.

## Input

The reporter generally accepts the results of queries, or identifiers passed on from containers or transaction. This is readily expandable to most anything; file an Issue.

### Static Data

It should be considered good design to build fully dynamic reports which can continue to function when things like addresses and institutional nomenclature change, or work across collections and institutions. Such reports require little maintenance, while reports which include static text require constant upkeep, and are prone to containing incorrect data when changes are not reflected in reports.

## Output

Output is generally either PDF-friendly HTML for labels, or CSV for consumption by external applications. However, it is possible to produce most anything that can be pushed through a browser.

## Fields

The reporter has the following structure:

* ``Report Name`` is the primary report identifier and must be unique. We recommend all lower-case ASCII characters (eg "myreport"), but at least locally any unique string will work.
* ``Report Type`` is for categorization and sorting.
* ``Accepts Variable`` controls what reports are avaiable when printing, and allows report selection to include only reports which work with the current data. Details are provided below.
* ``Report Description`` should contain enough information for anyone to understand why this report exists and how to use it.
* ``Used By Collections`` is used to filter and sort. This does not control access; all reports may be used by all collctions.
* ``Report CFM`` is (sorta) dynamic HTML, with query and processing capability.
* ``Report CSS`` is code that controls the page layout. It's generally better manage separately, but can be included in the cfm section in ``style`` tags as well.


## Accepts Variable

Accepts Variable controls what reports are avaiable when printing, and allows report selection to include only reports which work with the current data. 
The variable should be used in the SQL for selecting records (examples below). Supported values:

* ``table_name``: temporary/cache table name of last catalog record search. This will always contain collection_object_id, which may be used to join to catalog records or flat. This is almost always the best choice for catalog record based labels.
* ``collection_object_id``: a list of cataloged_item (or flat and filtered flat) collection_object_ids.
* ``transaction_id``: a list of transaction (or loan, borrow, or accn) transaction_ids.
* ``container_id``: a list of container IDs. May be be used to print container labels, or by joining to parts, catalog records.


### About Lists

Note that 1 is always an acceptable list length, and is most common for things like loan forms. However, the reporter will accept comma-separated lists of identifiers of virtually any length. Printing labels for a thousand hand-selected containers is easily accomplished.

## Editors

Reports may be edited in the browser fields, but it is often better to use a more specialized editor, and copy to the browser. We use sublime with postgresql and cfml packages; many, many other choices are available.

## Getting Data

### SQL
 
PostgreSQL-flavored SQL is the primary mechanism to retrieve data from the database. 

#### Variables
SQL Input variables must be enclosed in hash marks, like "#table_name#".

### Functions

Many functions exist in Arctos. These can be used to simplify SQL, filter results, or package data in expected and portable formats. These may be viewed in the DDL repository.

#### Special Note

Loan metadata/header data is relatively normalized and less-than-trivial to query, so a CF Custom Tag is available. 

````
<cf_getLoanFormInfo>
````

will return a data object under variable ``getLoan`` for any report for which ``loan.transaction_id`` is available.


### Tables

Table structure is available from the Arctos Table Browser. Cache tables FLAT (restricted access, unfiltered data) and FILTERED_FLAT (unrestricted access, filtered data) are often good easy to use sources of data, but do have limitations. Talk to your friendly local DBA if you have any questions. You may get a list of FLAT columns by entering "select * from flat where 1=2" in reports/writeSQL.

## Backups

All reports and individual reports may be downloaded as CSV, and new reports may be created from this. Save early and often; assume someone's going to delete all of your reports the very second you look away.  https://github.com/ArctosDB/arctos-assets is available for more-persistent backups; consider stashing periodic copies of 'mature' reports there.

## Clean up

Take backups, then delete any reports for which you are responsible and do not use. Huge piles of abandoned reports cause problems for everyone, and drastic action may result. (OK, not that drastic, there will be backups.)

## Printing

Use the browser's built-in print to PDF functionality. Click settings and turn off headers.

## Debugging

Variable ``debug`` default ``false`` is available to the reporter. Use open+debug to set it to true. See examples below for usage.

## Libraries

* In the CFM section of the report, ``<cfset inclPagedJs=true>`` (or ``inclPagedJs=true`` in cfscript) will make the Paged.js library avaialble to reports.


## Examples and usage

### Creating 

It is almost always best to work with the DBA team or copy an existing report to get started building a report, but all of the necessary information to start from scratch is in this doument and the Arctos Table Browser.

### Using

From transactions, containers, or catalog item search results, choose 'print any report,' select the report you wish to print (you can sort by clicking headers or search with your browser's built-in functionality), then click 'open' to execute the report. This will usually result in a HTML page which can be printed to PDF, or a CSV file which should automatically download to your selected download folder.

### Code Snippets

#### CFML

The "heavy lifting" is performed by CFML, which can be written as tags or script. Lucee is used to process, but Adobe Coldfusion is almost always functionally identical and often has better documentation.

#### HTML

HTML can be mixed freely with CFML. 
````
<p>#myvar#</p>
````
will simply print the value of ``myvar`` in a paragraph, for example.

#### CSS

We recommend CSS for layout. In general, keep it simple: Various browsers have slightly different handling of some CSS, and this tends to be much more noticeable in very new or obscure/little-used tags. (Older browsers may also have issues; developers use the current production release of Firefox, and you should too.)


#### Headers and Footers

Paged.js provides header and footer functionality, but is extremely twitchy. Fixed-size layouts and precalculated headers and footers tend to work much better than the alternatives. (And please let us know if you have a better solution, or need more JS/CSS libraries.)

#### CFML Query Objects 


````
<cfquery name="d" datasource="user_login" username="#session.dbuser#" password="#decrypt(session.epw,session.sessionKey,'AES/CBC/PKCS5Padding','hex')#">
	select field_name from table_name where key=<cfqueryparam value="#transaction_id#" SQLType="int"> 
</cfquery>
````

*  name="d" - return a query object in variable ``d``
* ``username="#session.dbuser#" password="#decrypt(session.epw,session.sessionKey,'AES/CBC/PKCS5Padding','hex')#"`` - authentication based off of your Arctos login. Messing with this can cause accounts to be locked.
* ``<cfqueryparam value="#transaction_id#" SQLType="int">`` - please use cfqueryparam rather than bare variables in queries. Sending unsanitized SQL to the database makes the DBA team nervous, and can cause accounts to be locked.

#### Debug

````
<cfif debug>
    <cfdump var="#d#">
</cfif>
````

will dump the object ``d`` - in this case the query we just performed - when the 'open+debug' option is selected (or ``debug`` is manually set to ``true``).


#### Comment
````
<!---
    this is a CFML comment
--->
````

Comments are ignored by the processor; future-you (and future everyone else!) will thank you for including lots of comments.

## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_documentation/reports.markdown" target="_blank">here</a>.
