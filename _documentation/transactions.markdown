---
title: Transactions
layout: default_toc
---

# Transactions


Transactions are actions that effect the coming and going of Cataloged
Items, and parts thereof. 
[Accessions](/documentation/accession.html)
permanently bring cataloged items into a collection,
[Loans](/documentation/loans/) record
movement and usage of cataloged items, and Borrows record items from
other collections lent, and in your collection’s temporary custody. 
These three types of transactions share several fields in common, and
those fields are treated on this page.



## Nature of Material

`Trans . Nature_of_Material VARCHAR2(4000) not null`


 is a brief textual description of the accession
or loan. Quantities can be approximate if accession material is not
being unpacked prior to storage. For example, "About 300 frozen small
mammals collected during the summer of 2004 in Denali State Park."

## Public Flag

By default, transactions (except identifier/"number") are internal and only available to the originating collection. Setting this flag to true
makes some transaction data publicly available.

## Trans Date

Trans date is an ISO8601 date field describing the date the transaction took place (usually began).

## Remarks

`Trans . Trans_Remarks VARCHAR2(4000) null`


 is a place for expanding a description of the conditions of
acceptance, or for instructions in processing the material. For example,
"Take 50 gram subsamples for fatty-acid analysis."

## Transaction Agents

Agents involved in transactions (
[Accessions](/documentation/accession.html), 
[Loans](/documentation/loans.html), and [Borrows](/documentation/borrows.html) ) are stored in table trans_agent.


## Transaction Agent Role

A [Code Table](http://arctos.database.museum/info/ctDocumentation.cfm?table=CTTRANS_AGENT_ROLE) describes the various roles
Agents have in Transactions.

## Next Number

Arctos can by request suggest the "next" transaction identifier (eg, loan number) if the existing data support such a calculation. File an Issue to request this functionality. Minimum requirements are the transaction type, format of the suggestion, and collection(s) to which the suggestion applies.

## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_documentation/transactions.markdown" target="_blank">here</a>.
