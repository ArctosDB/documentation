---
title: Publications
layout: default_toc
---

# Publications

Publications are included in Arctos to document the significance of
specimens. These associations also enhance publications by making the
work documented by publications more reproducible. Where specimens have
been [cited](/documentation/specimen-citations)
in a publication, this fact can be recorded as an explicit relationship
between a particular specimen and a particular page within a
publication. Where no such explicit relationship exists, publications
can be related to a [Project](/documentation/projects).

## Full Citation

`Publication.Full_Citation VARCHAR(4000) not null`

 is the textual description of a publication formatted
as it would appear in a bibliography. Typically this would include
authors (also potentially [separate data elements](#authors)), year of
publication (also a [separate data element](#published-year)), title,
journal name, and pages. Examples:

-   John J. Burns and Francis H. Fay. 1970. Comparative morphology of
    the skull of the ribbon seal, *Histriophoca fasciata*, with remarks
    on systematics of Phocidae. Journal of Zoology, London 161:363-394.
-   Jockusch E. L., D. B. Wake, K. P. Yanev. 1998. New species of
    slender salamanders, *Batrachoseps* (Amphibia: Plethodontidae), from
    the Sierra Nevada of California. Contributions in Science, Natural
    History Museum of Los Angeles County 472:1-17.

Though data can be keyboarded directly, the expectation is that Full
Citations will often be inserted directly from sources in which they are
already formatted. Such insertions should be examined for accuracy,
clarity and completeness. The following guidelines apply to titles:

The titles of journals and books have all major words capitalized.

-   Example: **The Small Mammals of the Great Plains.**

For journal articles and book chapters, capitalize only the first letter
of the title and proper names. Punctuate the end of the title with a
period unless it is otherwise punctuated.

-   Example: **The small mammals of the Great Plains.**
-   Example: **Naked mole-rats: why are they so weird?**

Italic text in titles should be marked up with the HTML italic tags
(&lt;i&gt; and &lt;/i&gt;).

-   Example: **The rat, &lt;i&gt;Rattus rattus&lt;/i&gt;, in Alaska.**
-   Renders as: **The rat, *Rattus rattus*, in Alaska.**

Special characters should be inserted in
[Unicode](http://www.alanwood.net/unicode/index.html) and (as above)
formatting should be handled with HTML tags.

-   Example: **Temporal records of d&lt;sup&gt;13&lt;/sup&gt;C and
    d&lt;sup&gt;15&lt;/sup&gt;N in North Pacific pinnipeds.**
-   Renders as: **Temporal records of d^13^C and d^15^N in North
    Pacific pinnipeds.**

## Short Citation

`Publication.Short_Citation VARCHAR(4000) not null`

 is typically authorship and year, the way
publications are cited when included in the text of other publications. Except in the case of "et al.," these should contain no punctuation or
formatting.

-   Jockusch et al. 1998
-   Burns and Fay 1970
-   Welsh 1968

## Publication Type

`Publication.Publication_Type VARCHAR2(21) not null`

[`ctPublication_Type`](http://arctos.database.museum/info/ctDocumentation.cfm?table=CTPUBLICATION_TYPE)

 describes the nature of the publication, and
vocabulary is
[controlled](http://arctos.database.museum/info/ctDocumentation.cfm?table=CTPUBLICATION_TYPE).

## Published Year

`Publication.Publication_Year NUMBER(4) not null`

 is the year in which the publication occurred. It is
a four-digit integer, *e.g*., 1985.

## Peer Review Flag

`Publication.Is_Peer_Reviewed_FG NUMBER(1) not null`

 should be set to false for publications which have
not undergone a formal peer review process, such as dissertations.

## DOI

`Publication.DOI VARCHAR(4000), null`


**DOIs** ([Digital Object Identifiers](http://www.doi.org/)) are CrossRef-issued DOIs which are applied to publications by publishers. These are capable of pulling data for use in creating the publication, and should be recorded with a publication when they are available. Including these identifiers will automatically create resolvable links to the publication, and will provide access to CrossRef's very powerful ecosystem.


Include only the actual IDs rather than a more complete link (which may get changed). The following is a DOI:

-   **10.1111/j.1365-294X.2005.02461.x**

The following are examples of formats that **contain** DOIs, but are **not** DOIs:

-   **dx.doi.org/10.1111/j.1365-294X.2005.02461.x**
-   **DOI:10.1111/j.1365-294X.2005.02461.x**.

## PMID


`Publication.PMID VARCHAR(4000), null`

**PMIDs** ([PubMed Identifiers](http://www.ncbi.nlm.nih.gov/pubmed/)) should be recorded with a publication when they are available if a CrossRef DOI is not available. Including these identifiers will automatically create resolvable links to the publication, but are not useful in creating publications and cannot serve as a bridge to more information.

## DataCite DOI


`Publication.DATACITE_DOI VARCHAR(4000), null`

**DataCite DOIs** ([Digital Object Identifiers](http://www.doi.org/)) are DataCite-issued DOIs which are applied to various data by various organizations. Including these identifiers will automatically create resolvable links to the whatever was assigned a DOI (often some representation of the publication), but are not useful in creating publications and cannot serve as a bridge to more information.

Include only the actual IDs rather than a more complete link (which may get changed). The following is a DOI:

-   **10.1111/j.1365-294X.2005.02461.x**

The following are examples of formats that **contain** DOIs, but are **not** DOIs:

-   **dx.doi.org/10.1111/j.1365-294X.2005.02461.x**
-   **DOI:10.1111/j.1365-294X.2005.02461.x**.


## Authors

`Publication_Agent.Publication_Agent_ID NUMBER not null (primary key)`

`Publication_Agent.Agent_ID NUMBER not null (foreign key = Agent.Agent_ID)`

`Publication_Agent.Publication_ID NUMBER not null (foreign key = Publication.Publication_ID)`

All of the above, as [Agents](documentation/agent) can be
linked to Publications. Though authorship is expressed in Full
Citation, Agents who are associated with other activities in Arctos,
such as [Loans](documentation/loans), [Projects](documentation/projects), and specimen collecting, should be linked to
their Publications. It is not necessary to create or link all authors
as publication agents. Agent Name formatting is unimportant as
formatted agent names are part of the full citation.

## Author Role

`Publication . Author_Role varchar2(255), not null`

[`ctAuthor_Role`](http://arctos.database.museum/info/ctDocumentation.cfm?table=CTAUTHOR_ROLE)

 indicates whether the agent is an actual author, or an editor of the publication. Vocabulary is
[controlled](http://arctos.database.museum/info/ctDocumentation.cfm?table=CTAUTHOR_ROLE).

## Creating Publications

Publications can be created in Arctos by two methods:
1. The relevant data can be keyboarded into the form, or
1. the DOI and/or PMID can be entered and then fetched by the form to automatically fill in most of the citation data from the Internet resources, CrossRef and NCBI’s PubMed.

Once these data are in the form, they can be appropriately
edited, and relevant [Agents](documentation/agent) selected as authors. The latter of these
two methods is the faster, but some publications, especially older ones,
will not have DOIs or PMIDs.

As an example of the second method, say there’s been a loan of (very)
old moth specimens to Maria E. McNamara and her graduate student Derek
E. G. Briggs. This (theoretical) loan results in a (real) publication –
[Fossilized Biophotonic Nanostructures Reveal the Original Colors of
47-Million-Year-Old
Moths](http://www.plosbiology.org/article/info%3Adoi%2F10.1371%2Fjournal.pbio.1001200).
The publication includes additional authors who are not in Arctos, were
not part of the loan, and who are not important to demonstrating the
usefulness of our collections.

There is a DOI given in the publication. Copy that, open the "create
publication" form in Arctos. Paste the DOI
(10.1371/journal.pbio.1001200) excluding any prefix ("doi:" and
"http://dx.doi.org/" are common) into the appropriate box, and click "\[
crossref \]."

<img src="http://arctosdb.files.wordpress.com/2011/11/screen-shot-2011-11-28-at-11-57-58-am.png"  width="640"
height="356" />

The DOI lookup service was able to obtain metadata, and everything you
see above is the result of that one click. If you click "create
publication" at this point, you would create a usable publication to
which Citations could be attached, and which could be a part of
Projects.

Here, however, we wish to capture agent information for at least the two
authors to whom we’ve made our earlier (fake) loan. During the CrossRref
lookup, Arctos has first looked for agents who match the string provided
by DOI, then for agents who MIGHT match the string provided by DOI. All
names – not just preferred – are considered. A maximum of five
"suggestions" are returned for each of the first five authors.

The first agent returned by the DOI service is Maria E. McNamara. There
is no agent with the exact name "Maria E. McNamara" in Arctos, but there
are three agents with last name "McNamara," all suggested in the first
line of the blue Agents grid. We happen to know that "Marie Englewood
McNamara" is correct, so we click that entry to select her.

The second author, who we also care about because he was on the loan, is
"Derek E. G. Briggs." Derek is also a pre-existing Arctos agent, and
that agent happens to have an exact-match agent string available. Arctos finds and suggests only this agent, and again one click is all
that’s necessary to add him to the publication.

<img src="http://arctosdb.files.wordpress.com/2011/11/screen-shot-2011-11-28-at-12-09-13-pm.png"  width="268"
height="312" />

The third author, Patrick J. Orr, does not have an exact name match in
Arctos, and does not have a last name match in Arctos, so the system has
gone off looking for agents with any string matching "Orr." In this
case, the results are not useful and can simply be ignored. If Patrick
J. were deemed important, he would need to be added to Agents and
selected in the standard way. If there were six "Orr" agents, Patrick
J. might still not show up in the suggest list, but could be found in
the standard way of picking agents. Take-home message: The agent
suggestions are just suggestions. Sometimes they’re useful, and
sometimes they’re not. Make no assumptions from them.

If we select the two suggested agents and create the publication….

<img src="http://arctosdb.files.wordpress.com/2011/11/screen-shot-2011-11-28-at-12-21-10-pm.png"  width="640"
height="356" />

<img src="http://arctosdb.files.wordpress.com/2011/11/screen-shot-2011-11-28-at-12-12-38-pm.png"  width="640"
height="223" />

we can then locate it by any name of either of two the authors who we
added

<img src="http://arctosdb.files.wordpress.com/2011/11/screen-shot-2011-11-28-at-12-14-04-pm.png"  width="265"
height="242" />

or anything from the "full citation,"

<img src="http://arctosdb.files.wordpress.com/2011/11/screen-shot-2011-11-28-at-12-15-16-pm.png"  width="230"
height="246" />

including the authors that we did not explicitly include

<img src="http://arctosdb.files.wordpress.com/2011/11/screen-shot-2011-11-28-at-12-16-30-pm.png"  width="233"
height="222" />

but we **cannot** find the publication by authors (as "Participants")
that we did not link to the publication.

<img src="http://arctosdb.files.wordpress.com/2011/11/screen-shot-2011-11-28-at-12-17-20-pm.png"  width="252"
height="245" />

results in

<img src="http://arctosdb.files.wordpress.com/2011/11/screen-shot-2011-11-28-at-12-17-51-pm.png"  width="640"
height="172" />

We could have used PMID (PubMed ID) rather than DOI to roughly the same
affect. Note that PMID and DOI are apparently independently created and
do not return the same values ("Maria E. McNamara" vs. "Maria E(no-dot)
McNamara," etc.).

<img src="http://arctosdb.files.wordpress.com/2011/11/screen-shot-2011-11-28-at-12-24-20-pm.png"  width="640"
height="351" />

Formatting from either source is occasionally horrible, and you are
encouraged to use the formatting tools provided (or your method of
choice) to rid citations of things like ALL CAPS and missing or
excessive punctuation.

Most of the time, using DOI or PMID will create better (as in fewer
mistakes) publications with much less work than keyboarding. The
service is, however, not magic and you, the operator, are responsible
for the results. Your collections may have additional guidelines as to
what agents to include, or how to format publications.

You may create [Media](media) to link publications with arbitrary
Internet documents. Please not that these linkages are notoriously
fragile, and do not serve as a suitable replacement for DOIs.

## Finding DOIs for existing publications

Arctos provides tools to find publications lacking DOIs, and to locate
DOIs for those publications. If you are an operator with
mange_publication rights you will receive missing DOI notifications in
publication search results and the publication edit screen. In most
cases, adding a DOI is simply a matter of clicking the button, letting
the service work, and saving. Please leave a remark as suggested (the
semi-standardized format facilitates search) if you are unable to locate
a DOI for a publication.

## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_documentation/publications.markdown" target="_blank">here</a>.
