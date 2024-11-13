---
title: GenBank
layout: default_toc
---

# Registration

Curators of Arctos collections should ~~encourage~~ require researchers using their
specimens for DNA sequences to submit GenBank accessions that cite the
specimens by ~~catalog number~~ GUID. GenBank will register Arctos institutions' GUID ("DWC Triplet" format).

If the correct and registered term is entered by the owner of the GenBank accession
under "source/specimen_voucher," then the catalog number will appear on
the GenBank sequence page as a link to the specimen record. An example
in GenBank:
<http://www.ncbi.nlm.nih.gov/nuccore/157058307?report=GenBank>

A definition of the specimen_voucher field and a link to registered collections is available at <http://www.insdc.org/controlled-vocabulary-specimenvoucher-qualifier>


If the record is not cited this way, and the owner of the GenBank
accession won’t change it, then it can still be linked by including the
GenBank accession number as an Other ID in the Arctos record. In these
cases, the nightly-update links to Arctos from GenBank will appear in
the LinkOut drop-down in GenBank accession records.

In any case, the GenBank accession numbers should be entered into Arctos
and Other IDs of type GenBank, and doing so will form HTTP links to
GenBank from the specimen detail page.

# Historical Document

In an effort to lock down the abbreviations with which we are familiar,
I have registered "UAM" and "MSB" with Biorepositories.org
(http://www.biorepositories.org/), and Berkeley has registered "MVZ."
All three of these registrations have been confirmed. So, operations
such as the Univeristy of Arkansas at Monticello will have to be more
creative than we were! I also put in a few specific collections that I
knew already had records in GenBank and listed the curators as contacts,
so some of you have been contacted by Biorepositories as part of the
confirmation process. This system may be too simplistic to survive the
many potential conflicts, but humanity has come to accept internet
domain names, so we can hope. In the meantime, what we’re doing works.
If your collection is not registered, you can either go do it at
Biorepositories, or let me know of your interest, and I will start the
process.

By including an Other ID Type of "BoLD barcode ID," Arctos records can
be also linked to records in the Barcode of Life Database (BoLD), but
please note that BoLD has no reciprocal capabilities and occasionally
changes the format of their URLs, breaking all links. 

[Chicago Workshop
Report](http://arctosdb.files.wordpress.com/2011/08/dbwgchicagoworkshopreport-final.pdf)

[Federhen et al. 2009](http://arctos.database.museum/media/10253751)

[Federhen 2014](https://www.ncbi.nlm.nih.gov/pubmed/25398905)

## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_documentation/genbank.markdown" target="_blank">here</a>.
