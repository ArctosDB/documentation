---
title: How To Github - Using Github Issues to Improve Arctos 
layout: default_toc
author: Dusty McDonald
date: 2016-06-06
---

# The Issue Process: How to Make Arctos Work for You

* Improvements to Arctos can come from any Arctos user. Suggested improvements can include simple coding bug fixes, the addition/deletion of 
data fields or menu items, new forms/buttons/functions to streamline collection processes - anything that will help Arctos users better 
manage and access Arctos data/specimens/objects.


* Changes to Arctos are submitted, discussed, prioritized, and tracked to completion 
using [Issues in GitHub](https://github.com/ArctosDB/arctos/issues). Once an Issue is created it will be reviewed by the Arctos Working Group. 


* Issues that do not require a discussion (bug fixes or broken forms/functions) will be resolved by Arctos programmers. 


* An Issue requiring discussion will be considered by the Arctos Working Group, the Issue author, and other interested users - 
Issues and discussions are open to all. The discussion of an Issue is best tracked as comments of the Issue. 
Each Issue that is created is number and considered active until Closed. You can reply to comment via email if you "Watch" a 
repository in Github. Read more about using [GitHub Issues](https://guides.github.com/features/issues/).

## How to File an Issue

* You need to create a username and password to log into Github 
(see "[How to Use GitHub for Arctos](https://github.com/ArctosDB/documentation-wiki/wiki/How-to-Use-Github-for-Arctos)") before you 
can file an Issue. 


* Use this link <https://github.com/ArctosDB/arctos/issues/> to access Arctos Issues.


* ALWAYS FIRST Search for existing Issues to be certain your Issue does not already exist. If a similar Issue already exists, 
you can comment on it, but please do not change the subject of an Issue in a comment.


* If you want to create a new Issue, click the green "New Issue" button in the upper right of the Issues list. Enter a short 
but clear title, and a description of the Issue in the text box where it says "Leave a comment." Click "Submit new issue" 
to assign the new Issue a number. Be clear and verbose in explaining the need and intended goals; provide specific examples,
 screenshots, or anything else which might help us understand what you wish to accomplish.
 
 
### Issue Protips
 
 Use these pointers to streamline getting the solution you need.
 
 * Tell us your overall goals. We can help only if we understand what you're trying to accomplish in sufficient detail. This will often involve an explanation of why the goal is important - "we want to record *_data_* because researchers need it for *_purpose_*."
 
 * Tell us *what* you hope to accomplish, not (only) *how* you hope to do so. We will get to how, but beginning the conversation with something like a [Product requirements document](https://en.wikipedia.org/wiki/Product_requirements_document) will generally lead to more robust solutions and avoid  [target fixation](https://en.wikipedia.org/wiki/Target_fixation).
 
 * Use templates. We have templates for common tasks, they specify the most common information we need. (Issues regarding how to make them better are always welcome.)
 
 * Include enough information for us to fully understand and replicate the problem or request. This includes but is not limited to
     * Data as uploaded (ZIPped to attach)
     * URLs
     * Specific sequence of clicks to get to a point of interest
     * Copy-paste of error messages (particularly the ErrorID - a UUID like ``795B1D17-0461-4A03-B6DC1314448ED77F``)
     * Screenshots
     * Arctos usernames of involved persons
     
 * Make sure you're in the right place. Most Issues should be filed in the "Arctos" repository, [https://github.com/ArctosDB/arctos/issues](https://github.com/ArctosDB/arctos/issues).
 
 

 
## Managing Issues

### Overview


Development tasks are encountered in the order listed on [https://handbook.arctosdb.org/how_to/How-to-organize-Issues.html](https://handbook.arctosdb.org/how_to/How-to-organize-Issues.html); if your Issue is not in one of those lists, we're probably not seeing it. Upvotes may be used to prioritize within a priority label. Note that text within the body of an Issue DOES NOT assign labels or milestones; these must be specifically selected using the tools on the Issue management page. All Arctos users should have a local AWG representative who can help properly categorize Issues.


### For Anyone

* Anyone can submit a new Issue or comment on an existing Issue. Github Issues are the preferred user-developer communication channel.
* Everyone with an interest in the development of Arctos should be participating in the Issue process. Your comments, however brief, and upvotes 
(👍) help us understand concerns and prioritize development.
* Please stay on track. Open new Issues for new subjects.
* Close Issues when they've served their purpose. 
* Re-open Issues if necessary, and leave a comment when you do. Sometimes unresolved Issues are closed, usually due to misunderstandings. 

### For ArctosDB Admin

* "Users" of the ArctosDB organization can manage Issues, meaning that they can do one of several things: 

 * Assign an "Assignee" - When filing an issue, leave Assignee blank. It's fair game for everyone to ignore "assigned" issues.

 * Assign a [Milestone](https://github.com/ArctosDB/arctos/milestones). Every Issue should be assigned a Milestone (see Guidance below).

 * Assign a [Label](https://github.com/ArctosDB/arctos/labels) to an Issue (see Guidance below).

 * Change the Status of an Issue. All resolved Issues should be marked as Closed.
 * Upvote (use the 👍 option) Issues for prioritization.

### Guidance on Assigning [Milestones](https://github.com/ArctosDB/arctos/milestones)

* _Needs Discussion_: The path to implementation is unclear and requires discussion by involved parties, the Arctos Working Group, and/or the broader Arctos Group. If an Issue is important to you, you should participate in these discussions.

* _Next Task_: The development needed is well-defined and accepted; just needs code written. Everything under this Milestone should have a Priority label; please add one if necessary.

* _Active Development_: Code is being written. Use this as development begins; make sure an Assignee is listed.

* _Wish List_: Major development, or development requiring major funding.

* _Wont Fix_: The Issue has closed without action. Leave verbose comments when using this.

### Guidance on Assigning [Labels](https://github.com/ArctosDB/arctos/labels)

Priority Labels

 * _Priority-Critical_: Issue is causing major problems; corrupting data, crashing servers, making specimens un-findable, etc.

 * _Priority-High_: Issue is actively preventing progress.

 * _Priority-Normal_: Standard Issue.

 * _Priority-Low_: Needs to be fixed/implemented/discussed, eventually.

Classification Labels

 * _Type-Form/Function_: Front-end Issue that has to do with either an interface form or specific functionality of Arctos. These types of Issues may include: Bug - defective code (e.g., the "save" button does not save); Enhancement - a request for additional or improved functionality (e.g., an idea for improving efficiency); Performance - a request for tuning (e.g., a query times out).

 * _Type-Data/Database_: Back-end Issue that refers either to specific data (e.g., data migration issue, code table spelling error) or the database itself (e.g., data table structure, security, etc.).

Functional Labels

 * There are different kinds of "Function-Thing" labels to help categorize Issues. For example, an Issue on how Arctos functions with regard to places or events (including georeferencing) should be assigned a "Function-Locality/Event/Georeferencing" Label.

### Useful Filters

* ["Active Development" Issues](https://github.com/ArctosDB/arctos/issues?q=is%3Aopen+is%3Aissue+milestone%3A%22Active+Development%22) are those which we're working on right now. This should be assigned only by the person who intends to address the Issue.
* ["Next Task" Issues](https://github.com/ArctosDB/arctos/issues?q=is%3Aopen+is%3Aissue+milestone%3A%22Next+Task%22) are those which are ready for implementation. Please leave a comment or thumbs-up (👍) to help us prioritize.
    * [Critical](https://github.com/ArctosDB/arctos/issues?q=is%3Aopen+is%3Aissue+milestone%3A%22Next+Task%22+label%3APriority-Critical)
    * [High](https://github.com/ArctosDB/arctos/issues?utf8=%E2%9C%93&q=is%3Aopen+is%3Aissue+milestone%3A%22Next+Task%22++label%3APriority-High)
    * [Normal](https://github.com/ArctosDB/arctos/issues?utf8=%E2%9C%93&q=is%3Aopen+is%3Aissue+milestone%3A%22Next+Task%22+label%3APriority-Normal)
    * [Low](https://github.com/ArctosDB/arctos/issues?utf8=%E2%9C%93&q=is%3Aopen+is%3Aissue+milestone%3A%22Next+Task%22+label%3APriority-Low)
* ["Needs Discussion" Issues](https://github.com/ArctosDB/arctos/issues?q=is%3Aopen+is%3Aissue+milestone%3A%22Needs+Discussion%22) are those for which sufficient information to proceed is not available. Please add a comment to the label as a means of discussion.
* [WishList Issues](https://github.com/ArctosDB/arctos/issues?q=is%3Aopen+is%3Aissue+milestone%3A%22Wish+List%22) are those which, at the time of last evaluation, we don't have resources to develop.
* [Uncategorized Issues](https://github.com/ArctosDB/arctos/issues?q=is%3Aopen+is%3Aissue+no%3Amilestone) require a Milestone.

## Edit this Documentation

If you see something that needs to be edited in this document, you can create an issue using the link under the search widget at the top left side of this page, or you can edit directly <a href="https://github.com/ArctosDB/documentation-wiki/edit/gh-pages/_how_to/How-to-Use-Issues-in-Arctos.markdown" target="_blank">here</a>.
