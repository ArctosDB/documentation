---
title: Higher Geography
layout: default_toc
author: Dusty McDonald
date: 2024-12-15
---


![](https://raw.githubusercontent.com/ArctosDB/documentation-wiki/gh-pages/tutorial_images/Bear%20Work%20in%20Progress.JPG)


# Geography

Geography has been defined (https://github.com/ArctosDB/internal/issues/366) in Arctos to reflect the administrative nature of asserted geography data. For example, many marine-focused collections wish to assert both marine (where the event took place) and terrestrial (eg perhaps the adjacent land from which permits are issued) geography for various reasons, while there is little or no overlap in spatial definitions of these places.

## Structure

### geog_auth_rec_id

Primary key, internal, not stable.

### continent

(Awaiting definition by the Arctos Geography Committee)

### ocean

(Awaiting definition by the Arctos Geography Committee)


### sea

(Awaiting definition by the Arctos Geography Committee)


### country

(Awaiting definition by the Arctos Geography Committee)


### state_prov

(Awaiting definition by the Arctos Geography Committee)


### county

(Awaiting definition by the Arctos Geography Committee)


### quad

(Awaiting definition by the Arctos Geography Committee)


### feature

References [ctfeature](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctfeature)

(Awaiting definition by the Arctos Geography Committee)


### island_group

References [ctisland_group](https://arctos.database.museum/info/ctDocumentation.cfm?table=ctisland_group)

(Awaiting definition by the Arctos Geography Committee)


### island

(Awaiting definition by the Arctos Geography Committee)


### source_authority

(Awaiting definition by the Arctos Geography Committee)


### geog_remark

(Awaiting definition by the Arctos Geography Committee)


### higher_geog

Generated concatenation of comma-sepated terms (in the order above, as of this writing). Serves as a (unique) 'handle' for the data object; what's entered during data entry.





## Creation Guidelines

(Geography should not be created or modified until the Arctos Geography Committee has established guidelines and updated this document.)

# Spatial

Spatial data are maintained separately from geography, and may be used to failitate search or suggest spatial affiliation.



## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_documentation/higher-geography.markdown" target="_blank">here</a>.
