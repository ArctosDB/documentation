---
title: How To Understand Deep Publication Data in Arctos
layout: default_toc
author: DLM
date: 2018-09-20
---
# How To Understand Deep Publication Data in Arctos
 
 Arctos exploits the CrossRef ecosystem to enhance publication data. Click "CrossRef Data" from publication details to get started. An overlay will pop up. Very few publications will have all of the data described below.
 
 This service works ONLY for publications with DOIs recorded in Arctos.
 
 ``
 NOTE: The initial load may be slow; many webservice requests are required to compile these data. Data are cached (for 6 months) and subsequent requests should be fast. The spinning wheel at the top of the page will disappear when the load is complete.
 ``

## Arctos Publication

Publication details are pulled for publications which are in Arctos. Note that the form requires only a DOI, and provides links for exploring related publications via the DOI system.

Publication Agents link to the Arctos Agent information portal.


## CrossRef Data

Data pulled from the CrossRef API are the core of this application. Select data are presented in a more readable format. Click the "view data" link to see fill CrossRef data in JSON format.

### Formatted Citation
The large bold text is from CrossRef in J. Mamm citation format. 

### Title
The unformatted title (when available) is provided with the "Title" label.

### Reference Count
Crossref provides a count of references used by the publication and a count of publications which reference the publication.

### Authors

Authors from the CrossRef data are displayed separately. A link to Arctos Agent is provides when both the CrossRef author and the Arctos Agent have a matching ORCID.

### Funding

Funding information is displayed when provided. Links to program awards and funder metadata are formed when possible.

## References

A list of references is displayed when provided. Note that minimal data ("1984") is provided for some references.

When a DOI is provided, CrossRef data are pulled and displayed, a link to the resource is provided, and the 'more information' link reloads teh page with that publication as the subject. A link to the Arctos publication is provided when available.

The "Auto Create" link will create Arctos publications. These are created entirely from CrossRef data, so expect formatting errors and misinterpreted data. This should be used to create publications which are likely relevant to Arctos collections (e.g., cite specimens). These are findable by the auto-inserted remark "Auto-created as suspected relevant to Arctos collections". 
[Or just click here.](https://arctos.database.museum/SpecimenUsage.cfm?action=search&publication_remarks=Auto-created%20as%20suspected%20relevant%20to%20Arctos%20collections)

## Cited By

These data are pulled from OpenCitations.net, and may not always match perfectly with the CrossRef data. Formattings, tools, and links are similar to References.

## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_how_to/deep-publications.markdown" target="_blank">here</a>.
