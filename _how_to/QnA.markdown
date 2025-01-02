---
title: Questions and Answers
author: DLM
date: 2024-07-15
original date: 024-07-15
layout: default_toc
---

# Short how-tos and such from the Arctos development team.

## Manage collection-specific code table values

From manage collection, (in the Collection Defaults section)...

<img width="538" alt="Screenshot 2025-01-02 at 15 40 44" src="https://github.com/user-attachments/assets/5e2393ce-4359-4d27-b0da-66007831ef43" />

... or from a code table (example:  <https://arctos.database.museum/info/ctDocumentation.cfm?table=ctattribute_type>), click the collection settings button:

<img width="176" alt="Screenshot 2025-01-02 at 15 39 02" src="https://github.com/user-attachments/assets/3c35ae39-6de0-4035-8db1-bbc4af2fb6b8" />

Choose a collection:


<img width="243" alt="Screenshot 2025-01-02 at 15 39 27" src="https://github.com/user-attachments/assets/dc34899b-5895-4661-b541-557eeb29b955" />

Then select values and save:

<img width="192" alt="Screenshot 2025-01-02 at 15 39 54" src="https://github.com/user-attachments/assets/e4fc9139-e6a2-4b68-a7c0-b79bef1f796d" />



## Note special use conditions for a record

Find or create an appropriate permit. Note that permits are useful documents which guide or control use; any more-formal interpretation is incorrect.

<img width="838" alt="Screenshot 2024-12-10 at 12 59 08" src="https://github.com/user-attachments/assets/03ccb48a-e1a6-44c3-8603-8e96e65d50c7">

Find or create a data loan. Note that data loans are transactions which are attached to select catalog records; any other interpretation is incorrect.

<img width="666" alt="Screenshot 2024-12-10 at 07 07 25" src="https://github.com/user-attachments/assets/a35595d2-99f4-4b2b-962e-fbf39d608bcf">


Add the permit to the transaction. (Transactions can carry any number of permits, and permits may be used by any number of transactions; reality need not be as simple as this example.)


<img width="268" alt="Screenshot 2024-12-10 at 07 08 14" src="https://github.com/user-attachments/assets/dba4376f-3832-4c7a-ace2-5f69861ed096">

Add the record to the transaction

<img width="243" alt="Screenshot 2024-12-10 at 13 02 37" src="https://github.com/user-attachments/assets/daa7f6b2-9d51-4760-825c-fb497c3042b7">

When interacting with the record (here, having found it in a query to add items to a loan), view the restriction:

<img width="190" alt="Screenshot 2024-12-10 at 13 00 54" src="https://github.com/user-attachments/assets/9a1b87f6-beb7-46a7-a858-ff59ac6c3e26">



## Locate records by specific classification data

Example: Records in the MVZ:Bird collection which are identified using a name which has term type ``CITES Appendix`` of value ``I`` in source  ``Arctos Legal``: <https://arctos.database.museum/search.cfm?guid_prefix=MVZ%3ABird&tax_trm_1=%3DI&tax_rnk_1=CITES%20Appendix&tax_src_1=Arctos%20Legal>

## Loan and Shipment Templates

To create a template open the loan create form, fill in whatever you'd like to save - all fields are optional for this - and click Templates. Choose a collection, provide a name, and click save.

To use a template, open the loan create form, click templates, and choose a template to pre-fill the form.

Users with manage_collection access may delete templates owned by their collection(s) using the button in the choose table.

Shipment templates work in exactly the same ways.




## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_how_to/QnA.markdown" target="_blank">here</a>.
