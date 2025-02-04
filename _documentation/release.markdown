---
title: Release Notes
author: DLM
layout: default_toc
---

# Release Notes

## 20250203

* <https://github.com/ArctosDB/dev/issues/169> - maintenance
* <https://github.com/ArctosDB/dev/issues/174> - bugfix


## 20250130


* <https://github.com/ArctosDB/dev/issues/170> - rebuild manage identification ot use component loader, split move part container to new component loader feeder
* <https://github.com/ArctosDB/dev/issues/173> - add increment existing functionality to identification tool
* <https://github.com/ArctosDB/dev/issues/119> - add ``collector.collector_remarks``




## 20250127


* <https://github.com/ArctosDB/dev/issues/166> - add media terms
* <https://github.com/ArctosDB/dev/issues/158> - add life_stage to cache
* <https://github.com/ArctosDB/dev/issues/167> - bugfix
* <https://github.com/ArctosDB/dev/issues/165> - bugfix
* <https://github.com/ArctosDB/dev/issues/168> - bugfix
* <https://github.com/ArctosDB/dev/issues/163> - maintenance


## 20250123

* <https://github.com/ArctosDB/dev/issues/39> - add units to container dimensions; rebuild and modernize underlying logic
* <https://github.com/ArctosDB/dev/issues/164> - prevent more unlicensed and inappropriately-licensed media while working towards a solution
* <https://github.com/ArctosDB/dev/issues/153> - modernization
* <https://github.com/ArctosDB/dev/issues/155> - security patch
* <https://github.com/ArctosDB/dev/issues/151> - bugfix
* <https://github.com/ArctosDB/dev/issues/154> - bugfix
* <https://github.com/ArctosDB/dev/issues/157> - bugfix



## 20250113

* <https://github.com/ArctosDB/dev/issues/144> - optimize
* <https://github.com/ArctosDB/dev/issues/149> - sanitize

##  20250108

* <https://github.com/ArctosDB/dev/issues/143> - add suborder to record search
* <https://github.com/ArctosDB/dev/issues/118> - rebuild part attributes; modernize, combine terms and datatype controls, add private/public
* <https://github.com/ArctosDB/dev/issues/145> - bugfix



## 20250102

* <https://github.com/ArctosDB/dev/issues/141> - clarify documentation
* <https://github.com/ArctosDB/dev/issues/139> - identification loader bugfix
* <https://github.com/ArctosDB/dev/issues/140> - update/version component loader template with identifiers doc link
* <https://github.com/ArctosDB/dev/issues/113> - add 'no coordinates' report
* <https://github.com/ArctosDB/dev/issues/139> - bugfix
* <https://github.com/ArctosDB/dev/issues/37> - saved search and archive create UI
* <https://github.com/ArctosDB/dev/issues/116> - update inline documentation

## 20241218

* <https://github.com/ArctosDB/dev/issues/136> - bugfix
* <https://github.com/ArctosDB/dev/issues/137> - continue separation of spatial and administrative geography data
* <https://github.com/ArctosDB/dev/issues/138> - bugfix and data cleanup
* <https://github.com/ArctosDB/dev/issues/120> - cleanup
* <https://github.com/ArctosDB/dev/issues/135> - new role write_report to better protect reports

## 20241216

* <https://github.com/ArctosDB/dev/issues/128> - continue separation of spatial and administrative data
* <https://github.com/ArctosDB/dev/issues/132> - bugfix


## 20241211

* <https://github.com/ArctosDB/dev/issues/133> - bugfix (?!) involving transaction/record intersection permissions

## 20241210

* <https://github.com/ArctosDB/dev/issues/129> - add prevent initial submit to search form, example:
	* https://arctos.database.museum/search.cfm?cat_num=14 - default bahavior, form immediately searches for passed-in parameters
	* https://arctos.database.museum/search.cfm?cat_num=14&autosubmit=false - new behavior, form loads with passed-in data filled and highlighted, but does not submit
* <https://github.com/ArctosDB/dev/issues/121> - new code table for permit use conditions
* <https://github.com/ArctosDB/dev/issues/122> - new permit structure use condition - serves as a succinct summary of what's required by the permit
* <https://github.com/ArctosDB/dev/issues/131> - make transaction identifier (eg "loan number") public
* <https://github.com/ArctosDB/dev/issues/108> - internal update


## 20241205

* <https://github.com/ArctosDB/dev/issues/124> - split geography continent/odean into two 'fields'
* <https://github.com/ArctosDB/dev/issues/126> - begin the process of moving spatial data out of 'assertable' place data
* <https://github.com/ArctosDB/dev/issues/127> - bugfix

## 20241202

* <https://github.com/ArctosDB/dev/issues/96> - require write_sql role to write sql (but belay final implementation). This will better protect the system while still allowing nearly anyone to change the parts of reports that mostly don't cause system-wide disruptions.
* <https://github.com/ArctosDB/dev/issues/115> - bugfix
* <https://github.com/ArctosDB/dev/issues/117> - minor UI adjustment
* <https://github.com/ArctosDB/dev/issues/114> - link to reports from transaction search results
   
## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_documentation/release.markdown" target="_blank">here</a>.


