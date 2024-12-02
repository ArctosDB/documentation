---
title: Authorities
layout: default_toc
---

# Authorities

Arctos maintains authorities in order to standardize content that is [shared amongst all collections using Arctos](/documentation/sharing-data-and-resources).

## Code Tables

[Code Tables](http://arctos.database.museum/info/ctDocumentation.cfm) enforce data consistency,
which results in more-usable pick lists to better provide users
with what they need, and allow more flexibility in communicating with
other data. However, these goals may not be entirely possible due to
curatorial reasons. In any conflict between ‘good data’ (*e.g.*,
consistent values) and curatorial need, curatorial need should win. (It
is often possible to revisit the data after some time in use and make
improvements then.) All Code Tables and code table data are the domain 
of the Arctos Working Group. Any proposed new
values must be submitted to the Arctos Working Group for consideration.
Any changes to existing values must be coordinated with the database
administrators.

Values should:

-   Be unambiguous. The choice between two values should always be
    clear, preferably from the values themselves.
-   Be documented. Especially in the case of values which cannot stand
    alone, clear documentation applicable to any collection which might
    use the value is critical. For example, note the distinction in
    `CTSEX_CDE` between "[not
    recorded](http://arctos.database.museum/info/ctDocumentation.cfm?table=CTSEX_CDE&field=not%20recorded),"
    "[recorded as
    unknown](http://arctos.database.museum/info/ctDocumentation.cfm?table=CTSEX_CDE&field=recorded%20as%20unknown),"
    and
    "[unknown](http://arctos.database.museum/info/ctDocumentation.cfm?table=CTSEX_CDE&field=unknown)."
-   Be universal. "A" should mean the same thing in an insect collection
    as it does in a palaeontology collection. This sometimes requires
    compromises in terminology.
-   Be consistent.

![](https://raw.Githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Bear%20Work%20in%20Progress.JPG)


## Principles

All code table values should adhere to our principles [developing document](https://docs.google.com/presentation/d/106K73W3og-iFLI9TZlfK00GtvVOJjIx5rU_43TsP49E/edit#slide=id.g24c167402f2_0_0)) in support of standardized, normalized, properly-categorized, connected, sharable "Research Grade" data.

### Reality

Arctos is a Community, and often cleaning up "legacy" data in favor of ideals is a difficult process involving local processes across hundreds of collections. We remain convinced that Arctos data are more capable of supporting deep research than anything else in existence, but we also acknowledge the realities of humans, traditions, resources, funding, etc.


## Collection-Specific Values


Many code tables are collection-specific. Operators with ``manage_collection`'' roles may select individual values for use in their collections under manage collection, or at the top of the relevant code table page. For example, parts:

![Firefox_Screenshot_2024-08-28T17-58-28 978Z](https://github.com/user-attachments/assets/62681465-ede6-41ba-8db1-a74f5161beb3)



## Rules of the Road for Code Table Terms

### General Rules for Adding Code Table Terms
 - Use predictable Punctuation  
    Allowed characters:
     - a-Z
     - 0-9
     - space
     - underscore
     - apostrophe (UTF-8) (e.g., ‘)
 - Whenever possible terms should have a published reference or citation.
 - Terms and their definitions should be as general and unambiguous as possible.

### Specific Rules for Specific Code Tables

#### Parts

 - Part names should be compatible with an ontological framework. Best practice would be a link to an ontology
 - It is preferable to create a general part that can then be refined with a modifier (e.g. girdle -> with the ability to add a modifier such as pectoral or pelvic).

## How To

Instructions for doing specifc tasks related to Authorities in Arctos

 - [How To Create and Manage Geology Attribute Terms (Code Tables)](https://handbook.arctosdb.org/how_to/How-to-Create-and-Manage-Geology-Terms.html)
 - [How to Request a Code Table Addition or Change](https://handbook.arctosdb.org/how_to/How-To-Request-A-Code-Table-Change.html)
 - [How to Manage Code Table Addition or Change Requests (for Code Table Administrators)](https://handbook.arctosdb.org/how_to/How-To-Manage-Code-Table-Requests.html)

### Taxonomy

Taxonomy is included here only for completeness. See [Taxonomy Documentation](/documentation/taxonomy) for more information.

### Geography

Geography is included here only for completeness. See [Geography Documentation](/documentation/higher-geography) for more information.

### Agents

Agents are included here only for completeness. See [Agent Documentation](/documentation/agent) for more information.

## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_documentation/authorities.markdown" target="_blank">here</a>.
