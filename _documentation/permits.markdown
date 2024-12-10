---
title: Permits
layout: default_toc
---

# Permits

Permits are any documentation authorizing activity or guiding usage. Permits are linked to transactions ([Accessions](/documentation/accession), [Loans](/documentation/loans), and [Borrows](/documentation/borrow)). Permits may be "issued by" governmental agencies, landowners, registrations (e.g., CITES), donors, administrators, or anyone else. Permits may carry any level of authority (including none), and apply to any (or no) context or jurisdiction. 

A permit can be linked to any number of transactions, and any number of permits may be liked from a single transaction.


# Permit

Table Permit is the core table.

## permit_id

internal key, not exposed

## issued_date

The day the permit was issued, or the first day that it is valid. This is a DATE datatype, not ISO8601; only day-precision is allowed.

## exp_date

The day on which the permit is no longer valid. This is a DATE datatype, not ISO8601; only day-precision is allowed. Used to automatically notify the permittees of the approaching expiration.


## permit_num


Permit Number or Permit Identifier is an identifying text string. This is often assigned by the agency issuing the
permit. Permit number is a required field; enter any suitable value which will help in locating the permit when such an 
identifier has not been provided by the issuer.

## use_condition

Use Condition ([ctuse_condition](http://arctos.database.museum/info/ctDocumentation.cfm?table=ctuse_condition))is a very brief summary of the conditions imposed by a permit, meant to be displayed in various contexts to guide necessary research.

## use_condition_summary 

Use Condition Summary is an elaboration of use_condition; it should sufficiently convey to most users most of the time what the permit requires. (For more complex situations, the permit itself should be consulted.)

## permit_remarks

These can be anything that extends the definition of the permit or the conditions under which it applies.

# permit_agent

Table permit_agent links permits with agents.

## permit_agent_id

internal key, not exposed

## permit_id

references permit.permit_id

## agent_id

references agent.agent_id

## agent_role

References [ctpermit_agent_role](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctpermit_agent_role)

# permit_type

Table permit type refines permits. A permit may have any number of types, each optionally associated with a regulation.

## permit_type_id

internal key, not exposed

## permit_id

references permit.permit_id


## permit_type

The kind of activity authorized by the permit. References [ctpermit_type](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctpermit_type)

## permit_regulation

The regulation under which the permit was issued. References [ctpermit_regulation](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctpermit_regulation)



# About

## Renewals

Renewals should be entered as a new permit. A shortcut button is provided on the edit forms.

## How To

Instructions for doing specifc tasks related to Permits in Arctos (please note that "under construction" icons on pages indicate that the documentation may be incomplete or out-of-date):

 - [How To Create a Permit](https://handbook.arctosdb.org/how_to/How-to-Create-a-Permit.html)


## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_documentation/permits.markdown" target="_blank">here</a>.
