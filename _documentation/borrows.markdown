title: Borrows
layout: default_toc
---

# Borrows

Loans are transcations that document any receipt of objects by a collection, temporary or permanent, including objects that are loaned with the intention of being destroyed or permanently transferred from another institution or collection. When objects are removed, a Loan should be created.

An object "exchange" between collections is two transactions: A loan and an accession. This arrangement well reflects the reality of incompleted exchanges, and takes advantage of the fact that we are dealing with both outgoing objects and incoming objects.

## Borrow Fields

### Borrow Number

`Loan . Loan_Number VARCHAR2(255) not null`

A Loan "number" is a string identifying the loan. The format usually
follows local tradition (*e.g.*, YYYY:nnn:Collection) but is
uncontrolled.

Arctos offers "next loan number" suggestions when a collection's data can support them. File an Issue to activate this functionality.

### Type

`Loan . Loan_Type VARCHAR2(25) null`

Loan type is a [code-table](http://arctos.database.museum/info/ctDocumentation.cfm?table=CTLOAN_TYPE) controlled vocabulary. If multiple Types apply, consider separate loans for separate Types, or
enter the most important one (*i.e.*, "returnable").

#### Data loans

Data Loans document data usage, and are generally used when a
project downloads data from Arctos without examining specimens. Data
loans form a special relationship between a loan and a cataloged item,
rather than a loan and a specimen part. Data loans are not meant as a
replacement for "digital" loans, in which a specimen part is imaged (or
otherwise digitized), as "digital" loans concern physical objects and
handling specimens. Subsequent usage of digital media (including that
generated in "digital" loans) may best be recorded as data loans.
Curators may wish to create a new loan number series for data loans,
although this is not required. This entry documents creation of a data
loan for illustrative purposes.

1.  Found publication vaguely citing Arctos
2.  Created publication agents in Arctos
3.  Since the available PDF was a reprint, used the DOI to look up
    original publication information
    (<http://www.google.com/search?q=DOI%3A+10.1111%2Fj.1472-4642.2008.00547.x>)
4.  Created Publication in Arctos
5.  Added Media to the publication
6.  Created Arctos loan of type "data"
7.  Downloaded data loan template
8.  Searched Arctos for scientific names cited in publication
9.  Downloaded results, copied catalog numbers to data loan template.
10. Filled in rest of values in data loan template, copy/paste to
    all cells. Saved as CSV.
11. Uploaded to data loan loader, clicked OK a couple times.
12. Created project, added loan, publication, and media created for
    publication
    
    <div class="separator" style="clear:both;text-align:center">
    <img src="https://sites.google.com/site/arctosdb/_/rsrc/1302031427955/howto/dataloan/screenshot_%202011-04-05%20at%2012.23.05%20PM.png" width="320" height="51" />
    </div>
    
Total time: \~10 minutes, mostly spent researching and creating Agents. Result:
<http://arctos.database.museum/project/different-climatic-envelopes-among-invasive-populations-may-lead-to-underestimations-of-current-and-future-biological-invasions>

The collections used, even though there was no formal loan request and
no physical specimen usage, receive quantifiable credit for specimen
data used. Future Hieracium added to Arctos will not be included in this
loan, so it will be possible to quickly identify specimens which could
not have been used, even though the lack of citations in the paper makes
it impossible to determine which specimens were actually used.
Additionally, if current Hieracium specimens are later determined to be
some other species, those data will remain as part of the loan, perhaps
explaining yet-undetected anomalies in the publication.

### Status

`Loan . Loan_Status VARCHAR2(20) not null`

Loan Status is essentially the degree to which the transaction has been completed. The values comes from a [code-table controlled vocabulary](http://arctos.database.museum/info/ctDocumentation.cfm?table=CTLOAN_STATUS).

### Loan Agents

`Trans_Agent . Trans_Agent_ID NUMBER(22) not null`

See [Transaction Documentation](/documentation/transactions.html#transaction-agents) for agent information.

### Nature of Material

`Trans . Nature_of_Material VARCHAR2(4000) not null`

A description summarizing the overall content of
the loan. This description will appear on the loan invoice. It should be
explicit and concise, but it does not need include details on a
specimen-by-specimen basis.

### Instructions

`Loan . Instructions VARCHAR2(4000) null`

Directions to the borrower on such things as storage
and return of the loaned items.

### Description

`Loan . Description VARCHAR2(4000) null`

*I don’t know? Why do we need another text field in
addition to Nature of Material and Remarks?*

### Remarks

`Trans . Trans_Remarks VARCHAR2(4000) null`

Any annotations that will not be included on the Loan
invoice.

### Initiated Date

`Trans . Trans_Date DATE(7) null`

Initiated Date is the [date](/documentation/dates) on which preparation of the loan began. A
default value would be the date on which the loan was first recorded in
the database.

### Due Date

`Loan . Return_Due_Date DATE(7) null`

Due Date is the [date](/documentation/dates) that a loan of the Type Returnable is expected
to be returned to the lending collection. This date may be used to
search for overdue loans, and/or to generate automated reminders to the
appropriate agents.

### Shipping Date

`Shipment . Shipped_Date DATE(7) null`

Shipping Date is the [date](/documentation/dates) that the loaned material was shipped from
the collection issuing the loan. The Shipping Date should be consistent
with any documentation provided by the carrier, *e.g.,* a waybill, bill
of lading, etc.

### Receipt Acknowledged

`Borrow . Received_Date DATE(7) null`

Receipt Acknowledged is the [date](/documentation/dates) the agent receiving the loan
submitted acknowledgment of its arrival to lending collection.

### Returned Date

`Loan . Closed_Date DATE(7) null`

Returned, or Closed, Date is the [date](/documentation/dates) that a loan of the type Returnable was received back at the
collection from which the loan was issued.

## Permits

A loan may be authorized under one or more
[permits](/documentation/permits), and these may include both the senders and to
the recipients. Such authorizations should be recorded by associating
the loan with a permit that must be already be in the database.
Recording this information may be critical to reporting to the
permit-issuing authority, and hence a legal requirement for conducting a
loan.

## Projects

A loan is almost always made in support of one or more
[projects](/documentation/projects), and it is in project descriptions that the
scientific justification for the loan should be described.

## Deleting Items

In general, an item which has gone out on loan should never be removed
from the loan. Delete functionality exists only to correct mistakes –
when an item was added to a loan but not shipped, for example. Loan
items (parts) may not be deleted from the database. Item Disposition
and/or [Container](/documentation/container) information is used to signify that an item has been
returned (or sent out on another loan). Maintaining this history is
vital to recording collection activity, and for building Projects, which
are transaction-based.
