---
title: Component Loaders
author: Teresa J Mayfield-Meyer
date: 2021-07-28
layout: default_toc
---
# Component Loaders and Unloaders

Component Loaders are an ecosystem of tools which asynchronously 

Data can be added to and in some cases removed from existing catalog records from a single flat (non-relational) file, a text file in which all data for an individual concept to be added to or removed from a single cataloged item are in a single row. This file can be created with any convenient client-side application. The file is then loaded into a similarly structured table on the server, and a server-side application (the component loader) parses the columns from each row into the relational structure of the database. The process provides an independent layer of data checking before new information is incorporated into the database proper. Original data that are received in electronic format may require minimal manipulation; you can sometimes merely add the necessary columns to build a file in the component-loading format.

**Component Loader templates should be downloaded from the appropriate component loader tool in Arctos. All other means, including this documentation, may produce non-current data which will be rejected.**

 - The standard method for moving data into any component loader is by importing data from csv directly into the component loader tools. However, component loaders may be populated as part of bulkloading. 

 - You may mix accessions, collections, or anything  else in a single component load.

 - The component loaders may not handle every eventuality that may ever occur while entering additional data. Use [status](#status) to mark records for further review. Records in any component loader that were populated from the bulkloader will be tied to the bulkloader records with UUIDs.

 - Error messages should include more than enough information to allow you to locate and correct the problem. If that isn’t the case, [contact us](https://arctosdb.org/join-arctos/contacts-support) with the error message and a description of the action that caused the error message.

 - Arctos is case-sensitive. JOHN DOE is not the same value as John Doe. Leading and trailing spaces and other non-printing characters matter.

 - The web-based applications may not work well for very large loads. [Contact us](https://arctosdb.org/join-arctos/contacts-support) if you’re having problems.

## Fields
Component loader fields differ based upon the information being loaded. For more on any particular component loader, see Page Documentation on the Arctos Tool Page for the component loader. Some things hold true accross all component loaders.

Be sure anything coming from other applications (especially Microsoft products) has not changed field length, precision,
or other attributes. Watch dates and non-integer numbers (such as decimal latitude) most closely.

### Status

All component loaders include a status field that is NOT part of the component loader template (but you can add it before loading if you like). This field can be NULL or include any text that helps you to organize information in the component loader. There is one special provision for this field:

#### autoload

Entering "autoload" in the status field sets the record to load.

### Primary Key Warning

Some values may be replaced by or require primary keys: `locality_id`, `entered_by_agent_id`, `collecting_event_id`, etc. These are internal database identifiers that exist only for convenience, and may be updated, transferred to another data object, or removed for seemingly arbitrary reasons and without warning. They’ll probably work over short time-periods, but we offer no guarantees.

## Permissions

Permissions vary across tools. Check Component Loader Status or the Directory for details.


## Processing

Once a component loader record is marked to load by making ``status`` autoload, a script periodically attempts to parse the record into the normalized core Arctos structure. This may result in two things: 

 - the record is added to the associated catalog record and marked for cache refresh, or
 - an error is returned in the ``status`` column


A Component Loader Status tool will report status, and allow privileged users to change run order.
   
Records which successfully load must be refreshed in the cache before appearing in the user interfaces. Records are  refreshed in the order they enter the queue. This process often takes less than one minute, but in the case of many thousands of records being queued can take up to several days. ``Reports/Services>View Statistics>FLAT Status`` provides a summary of the state of the cache, and may be useful in estimating processing time.

Note that there is a period of time between successful loading and the cache being refreshed where records are not visible in any user interface.

Records that do not successfully load remain in the component loader. They must be downloaded, deleted from the component loader, edited and reloaded to correct any issues. Editing within the component loader is not currently available.

## Edit this Documentation

If you see something that needs to be edited in this Documentation, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly [here](https://github.com/ArctosDB/documentation-wiki/blob/gh-pages/_documentation/componentloader.markdown).
