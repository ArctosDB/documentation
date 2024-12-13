---
title: How To Join Arctos
layout: default_toc
author: DLM, Michelle Koo
date: 2024-12-08
---
# How To Join Arctos

## For prospective partners


Fill out the [Prospective Collection Form](https://docs.google.com/forms/d/e/1FAIpQLSec0BuRKDGDjqxT1fRI31GbZc0TORLK6DoLjZReQfnl5iIyDA/viewform) and we will contact you.

The submitted form will go to the executive committee of the Arctos Working Group, aka Officers. One of the [officers]([AWG](https://arctosdb.org/contacts/)) will contact the submitter as soon as possible but please allow 2 weeks at most. Please email arctos-working-group-officers@googlegroups.com if you have not received a response.  


Once the prospective partner has committed to Arctos, the Arctos Director will begin the process of signing the Memorandum of Understanding (MOU) between the member institution and Arctos Consortium.

## For Arctos
			
Once the administrative steps are complete and a new member has joined Arctos, there are a number of procedures to onboard collection staff, establish collection metadata, train users, etc. The director will assign a data migration specialist or other mentor as needed as every member who joins has different circumstances and requirements. The Arctos officers will be available to:

* Facilitate communication between the new member institution, the Arctos Working Group, and Arctos staff.

* Define collections. Incoming collections are often merged or split, for example - this should be understood and agreed upon by all involved parties very early in the process. Documentation is available at [Catalog](https://handbook.arctosdb.org/documentation/catalog.html). Create a GUID_PREFIX for each collection in the institution. This is a permanent value which is used in links to specimens and should never be changed. Please take great care to ensure that the collections understand the importance of stability in this value before proceeding. Documentation is available at [Catalog](https://handbook.arctosdb.org/documentation/catalog.html). [GRSciColl](https://scientific-collections.gbif.org/) may be a useful resource when considering a new GUID Prefix. When GUID_Prefix is established, [pre-create collections](https://arctos.database.museum/Admin/pre_collection.cfm). 

* Work with the incoming Institution to provide metadata for each collection.

* Create an Operator for each collection. Documentation is [Users](https://handbook.arctosdb.org/documentation/users.html) and a How-To is available at [How To Create and Manage Your Arctos Team: Users and Operators](https://handbook.arctosdb.org/how_to/How-to-Create-your-Arctos-Team-Users-and-Operators.html). These new Operators do not need any roles or collections; this will be assigned when the collections are created.


Once collection metadata are provided and reviewed _for all collections in the institution_, Exhibit 3 of the MOU will need to be approved by the member institution and filed with their MOU.


## Existing Institutions

Existing institutions in good standing do not need to complete a Prospective Collection Request. Established Arctos database institutions that need to add a collection should proceed to "<a href="https://arctos.database.museum/Admin/pre_collection.cfm" class="external">Finalize collection creation request</a>".

1. Read through the "<a href="https://arctos.database.museum/Admin/pre_collection.cfm" class="external">Prerequisites</a>" and if anything there isn't clear or hasn't been discussed with your institution, then don't proceed.
    *Note: the "admin_user" is the admin's login name NOT their Agent name.
2. Your new GUID_prefix should be confirmed with your institution and the DBA team.
3. Your "preferred taxonomy source" should be decided ahead of creating the new collection. (There is a wide variety of taxonomy resources to choose from.) 
4. Have your Loan Policy URL copied from menu item "Manage Data," "Metadata," "Manage Collection."
5. After you've checked all the boxes, proceed.
6. Voila!  A new collection REQUEST has been created.
7. <a href="https://github.com/ArctosDB/new-collections/issues/new?assignees=&labels=&projects=&template=exisiting-institution-requesting-a-new-collection.md&title=Arctos+Institution+Name+request+to+add+a+new+collection" target="_blank" class="external">Create a new issue in the new collections Github repository</a> and add the guid_prefix(s) you've submitted.


## For DBAs

You will be contacted via GitHub by the new collection or their mentor. Data will be in table pre_collection. All subsequent communication should be through GitHub.

1. Ensure GUID_prefix is familiar, users exists, etc.
2. Create collections
3. Grant collection access, manage_collection, and global_admin to admin_user (it may be a list).
4. If a request is denied or revoked, change guid_prefix to "INVALID:{former guid_prefix}"
5. Find pending requests: ``select guid_prefix from pre_collection where guid_prefix not in (select guid_prefix from collection);``

## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_how_to/new-collection.markdown" target="_blank">here</a>.
