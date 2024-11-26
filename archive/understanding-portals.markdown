---
title: index How To Understand Portals (Deprecated)
author: DLM
layout: default_toc
---

# Portals (Deprecated)

See https://github.com/ArctosDB/documentation-wiki/issues/302

Portals provide specific types of access to specific datasets (generally collections) in Arctos.

## Background

Arctos uses Virtual Private Databases (VPDs) to partition collections. A VPD is a virtual container around rows in a table to which
specific users may be granted specific rights. From a user's perspective, the rows to which they've been granted access are all that exist; 
their viewpoint would not change if other collections were on another server on another system to which they do not have access. 

## Users

Unlike other systems, the Arctos UI has the capability to log into the database as specific users. Every operator is a user, and as above 
users may be granted specific roles to specific partitions.  When a user goes to Arctos a session is established and they are logged into
a specific account. 

## Roles

Arctos has two "types" of roles: access and permission. Access roles grant a user access to a VPD. Permission roles grant a user specific 
operations on the data to which they have access. Examples:

* A user who has only UPDATE permission on "sometable" can update the records in "sometable." 
However, without VPD access, "sometable" contains nothing from their perspective.
* A user who has only "some_collection" access can access the "some_collection" VPD partition - in which nothing will exist for them 
without a permission role.
* A user who has UPDATE permission on "sometable" *and* "some_collection" VPD access can update the rows in "sometable" which are 
owned by "some_collection." (Which would be awkward, because they can't SEE those data without also having SELECT explicitly granted!)

That is, what a user can see and do is defined by the intersection of their permissions and access.

### Portals

Portals are simply public-access shared users. The default account is "public" which has SELECT access on selected tables. For example,
 the "public" user has full access to FILTERED_FLAT (the summary/query table from which restricted information has been removed) and no 
 access to FLAT (the "internal" summary table which contains encumbered information). Each portal has an associated user. An institution
 with two collections would generally have three portals:
 
 * A "Collection1" portal with SELECT permission on Collection1 data in public tables
 * A "Collection2" portal with SELECT permission on Collection2 data in public tables
 * An institutional portal, with SELECT permission on Collection1 and Collection2 data in public tables
 
#### Portal Roles

Portal users are granted SELECT on public tables. Internal table (such as transactions) do not exist for portal users.
 
 
### Operators

Each Arctos Operator (agent with more than SELECT access) is a user. As such, when logged in they are explicitly granted their own permissions.
To access portals, a user must log out of their operator account (which would log them into the default "public" account) and then
click a link to a portal (which would log them in as the portal's associated public user).

#### Operator Roles

Operators are explicitly assigned roles by their supervisors. These roles have been bundled for convenience - for example, the MANAGE_SPECIMENS
 role allows INSERT and UPDATE and DELETE on table ATTRIBUTES, but only INSERT and UPDATE on IDENTIFICATION. (That is, students can create and
 manage identifications, but they cannot remove them.) Operator roles include PUBLIC, which provides read access to assigned collection's data.
 
## Links

Links to portals may be found at [http://arctos.database.museum/home.cfm](http://arctos.database.museum/home.cfm)

## Escaping Portals

You may switch from a portal user to the generic public user by going to [http://arctos.database.museum/all_all](http://arctos.database.museum/all_all)

## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_how_to/understanding-portals.markdown" target="_blank">here</a>.
