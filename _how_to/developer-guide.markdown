---
title: Arctos Developers Guide
layout: default_toc
author: DLM
date: 2019-10-15
---

# Arctos Developers Guide
Tips, tricks, and conventions for developing Arctos code

### CFML

Arctos is written primarily in [CFML](https://en.wikipedia.org/wiki/ColdFusion_Markup_Language) and HTML. 
* within ``<cfoutput></cfoutput>`` tags, ``#`` is a special character; ``#variable#`` means render variable ``variable`` as HTML. ``#`` used as text (eg, as an anchor in a URL) must be escaped. ``someURL.com#anchor`` must be written as  ``someURL.com##anchor``
* outside of ``<cfoutput></cfoutput>`` 	``#`` is just a character.

### URLS

* make internal URLs relative - ``/somePage`` never ``http://....somePage``
* use DataServices/Linkerizer to build URLs. There are currently three classes of URL supported:
    * no class-->default browser behavior
    * external-->"pop out" image appended, open in new window
    * newWinLocal-->"info" image appended, open in new window (use for links to arctos.museum information pages such as code tables)

### CSS
* when possible, use /includes/style.css for styling. (Directions for minimizing are inline.)
* for one-off use, in-page CSS (``<style></style>`` tags) is acceptable but less preferred
* avoid inline styling (``<div style="...."></div>``); this makes it very difficult to change things and keep a consistent look and feel

### Recommended Code Editors
 
#### Sublime Text

DLM's weapon of choice

#### Atom

## Component Loaders

(ref: https://github.com/ArctosDB/dev/issues/110)

* all user-supplied fields should be text, which is more portable. Handlers must check and cast as appropriate.


## Identifier Convention

* internal identifiers are primary keys or tables, are integers, and should be named ``something_id``
* GUIDs are generally primary keys made GUID-ish, begind with ``https://arctos.database.museum/``, and should be referred to as ``somethingID`` (Note that DDL is not case sensitive and case will often be lost.)
* "DWC Triplets" ("local" record identifiers still widely referred to as GUID) should be referred to as "triplet" when reluctantly used. (See also https://github.com/orgs/ArctosDB/discussions/5310)

## Datasource

Arctos uses various datasources for various reasons. Most queries should be one of two entries:

* Datasource ``user_login`` logs in to the database as the Arctos user. This connection must be supplied with valid credentials.
* Datasource ``cf_codetables`` is a special pre-authenticated user who has SELECT on ct* tables. This user should be used for all possible connections which SELECT from codetables, for performance reasons, and these queries should always be set to cache. The query name should always be the name of the code table to further support caching. For example:

``` 
<cfquery name="ctdatum" datasource="cf_codetables" cachedwithin="#createtimespan(0,0,60,0)#">
   select datum from ctdatum order by datum
</cfquery> 
```

## Expand Select

This toggles MULTIPLE for a SELECT of id "accn_status":

```
<span data-ctl="accn_status" class="ui-icon ui-icon-arrow-4-diag expandoSelect"></span>
```

## Button-Links

Button + HREF

```
<a href="somepage.cfm"><input type="button" class="lnkBtn" value="Some Text"></a>
```

## Code Table Definer

```
<span class="infoLink" onclick="getCtDocVal('cttaxon_name_type','taxon_name_type');">Define</span>
```

where ``cttaxon_name_type`` is the relevant code table and ``taxon_name_type`` is the ID of the element being defined.

Or as a label

```
<label class="likeLink" onclick="getCtDocVal('ctcataloged_item_type','cataloged_item_type');" for="cataloged_item_type">
   Catalog Item Type
</label>
```

## Pick/select Inputs

* prefix placeholder with 'type+tab to pick ....'
* CSS class: pickInput
    * after success: goodPick
    * after fail: badPick

## Color Codes

(see css file for current defintion)

"Arctos blue": --arctosdarkblue

ARCTOS BODY
* --arctoslightblue

TEXT
* Fonts (all, including Section Label title): --arctosdarkblue
* helpLinks and Hypertext --arctoslinkcolor
* Hover text --arctoslinkhovercolor
* Visited Hypertext --arctosvisitedlinkcolor


QUERY BLOCK STRIPEY GRID
* Color 1/odds (darker): --arctosdarkstripecolor
* Color 2/evens (lighter): --arctoslightstripecolor

HIGHLIGHTS
* target: --arctoshighlightcolor

BUTTONS
* Search/Submit Query: input.schBtn #82B8EA 
* Customize: input.cstmBtn #C9D2DC
* Quit/Clear: input.qutBtn #FFFFFF
* Choose/Pick: input.picBtn #A7E8FF
* All/Link: input.lnkBtn #89B2C1
* Save: input.savBtn #F5C03D
* None/Delete: input.delBtn #f99f67

FOOTER
* SuperFooterDiv background #113d64 
* MainFooterDiv background #BBD3DB

BANNER/LOGIN Terms box
* yellow: #5FC03D

## Logos

Logos are in the images folder of the /ArctosDB/arctos-assets/ repository.

## IPT Mapping

* Adding New Terms - any time a new field is added to the Darwin Core Archive, that field MUST go at the end of the list, otherwise, all of the mappings that come after wherever it is added will be offset by one term and the data will fail to publish.

## last_usr and last_chg

Some tables have a lastuser and lastdate field, which generally exist to be picked up by subsequent actions particularly when a script is running on behalf of a user. These **should** default to meaningful values when a human is pushing buttons, but PG's environment can be a little wonky (and the test and prod DBs occasonally do not share settings). Best practice is to provide these values explicitly:

* ``last_usr=<cfqueryparam value="#session.username#" cfsqltype="cf_sql_varchar">``
* ``last_chg=<cfqueryparam value="#DateConvert('local2Utc',now())#" cfsqltype="cf_sql_timestamp">``



## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_how_to/developer-guide.markdown" target="_blank">here</a>.
