---
title: List of Data Quality Contacts by Collection
layout: default_toc
author: Dusty McDonald, Teresa J. Mayfield-Meyer
date: 2021-07-29
---
# List of Data Quality Contacts by Collection

This query provides a list of the collection(s) in Arctos and the email address of their active data quality contact (no email means no data quality contact).

## GitHub Issue
This query was created as a response to this Github Issue - <a href="https://github.com/ArctosDB/internal/issues/105" target="_blank">Inernal Issue #105</a>

## Code
Copy the code below and paste it into <a href="https://arctos.database.museum/tools/userSQL.cfm" target="_blank">Reports/Services > Write SQL</a> in Arctos to repeat this query

```
create table temp_dqcc as
select guid_prefix,get_address(contact_agent_id,'email') email
from collection
left outer join collection_contacts on collection.collection_id=collection_contacts.collection_id and contact_role='data quality'
order by guid_prefix
```

## Edit this Documentation

If you see something that needs to be edited in this How To, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/blob/gh-pages/_sql_cheats/no_data_quality_contact.markdown" target="_blank">here</a>. 
