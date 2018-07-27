#### Australian Government Linked Data Working Group

# URI Guidelines v2.0
#### July 20 2018

*This document is a second and very different version of the* Guidelines *produced by the Australian Government Linked Data Working Group. See *[the guidelines repository](https://github.com/AGLDWG/TR/tree/master/guidelines) *for previous versions.*

#### TODO
1. update all reference numbers [x]
1. complete part 8.
1. refer to new ideas about cataloguing in parts 10 & 11

## Table of Contents
1. [Conformance](#Conformance)
2. [Introduction](#Introduction)
3. [URI Registration](#URIRegistration)
4. [URI Allocation Types](#URIAllocationTypes)
5. [Datasets](#Datasets)
6. [Definitional Resources](#Definitional)
7. [Top-Level Registers](#TopLevelRegister)
8. [Second-Level Registers](#SecondLevelRegister)
9. [References](#References)
10. [Appendix A: Dataset Linked Data requirements](#app-a)
11. [Appendix B: Definitional resource modelling requirements](#app-b)
11. [Appendix C: Lodging and validating Dataset metadata](#app-c)

## 1. <a id="Conformance"></a> Conformance
The key words *MUST*, *MUST NOT*, *REQUIRED*, *SHOULD*, *SHOULD NOT*, *RECOMMENDED*, *MAY*, and *OPTIONAL* in this document are to be interpreted as defined in [[IETF-1997](#ref-IETF-1997)].

Roles associated with this catalogue acting as a 'Metadata Registry', *Overall Registration Authority*, *Registrar*, *Executive Committee*, *Control Committee*, *Overall Stewardship Organization*, *Steward*, *Overall Submitting Organization*, *Submitter*, *All others*, *Read-only user*, are to be interpreted as defined in [[ISO-2015](#ref-ISO-2015)].

URI patterns are expressed using Augmented Backus-Naur Form, as defined in [[IETF-2008](#ref-IETF-2008)].

Resource status codes are taken from [[17](#ref-17)] and are re-presented by the AGLDWG at [[18](#ref-18)].

## 2. <a id="Introduction"></a>Introduction    
Government departments and agencies assign identifiers to many things they are responsible for - e.g. datasets, classification concepts, hospitals, equipment, etc. These identifiers are then used when referring to or making statements about particular things. For example, when referring to a road closure, the identifier (e.g. "M5") will be used to inform the public or when referring to a particular census Mesh Block, its identifier, perhaps "80006300000" will be used.

Government published, public sector information (PSI), usually about the things agencies are responsible for, is intended to be re-used by many, initially perhaps unknown, applications over time to maximise its value to the nation. For this reason, it is important that elements of it are able to be identified and accessed in consistent ways for long periods (perhaps multiple decades).

The Australian Government Linked Data Working Group (AGLDWG) advocates the use of Linked Data [[W3C-2018](#ref-W3C-2018)] as a particular set of technologies to be used for Internet-distributed, machine-readable data and, due to this, advocates the use of Linked Data URIs for identifiers for things.

### 2.1 Uniform Resource Locators (URIs)
Linked Data uses Uniform Resource Identifiers (URI) which are part of a single, global, identification system used on the World Wide Web, similar to telephone numbers in a public switched telephone network. We are all familiar with URIs at work due to their use for addresses in browsers for web pages. URIs are a key technology to support Linked Data by offering a generic mechanism to identify *things*. In order to publish data in a Linked Data fashion, government needs to represent the identifiers they use for things using URIs.

Sir Tim Berners-Lee who created many aspects of the World Wide Web we now take for granted also defined principles for the use of URIs with Linked Data [[TBL-2009](#ref-TBL-2006)]. This document builds on those principles which, summarised are:

##### 2.1.1 Use HTTP URIs
Addressing two of the four principles, *'use URIs'* and *'use HTTP URIs', *governments and their agencies publishing Linked Data ***MUST*** provide HTTP URIs as identifiers for resources, in order to support reuse and data integration/linking on the Web in a Linked Data fashion. HTTP URIs enable URIs to be "looked-up" or "dereferenced", which in turn provides access, via a Web browser, to a representation of the resource identified by these URIs.

#### 2.1.2 Provide a machine-readable representation of the resource identified by the URI
In order to enable HTTP URIs to be "dereferenceable", data publishers have to set up the necessary infrastructure (e.g. HTTP servers) to serve representations or descriptions of the resources (e.g. a human-readable HTML representation or a machine-readable RDF/XML representation). For it to be considered Linked data, a publisher ***MUST*** publish the data using RDF (i.e., to define explicitly the meaning of all data elements) and ***MUST*** publish at least one machine-readable representation of it (e.g. RDF/XML, JSON-LD, Turtle) via the HTTP URI identifying the resource.

Requirement | Description | Conformance
--|--|--
<a id="req-1"></a>[Req 1] | Use HTTP URIs so that the Linked Data dataset URI can be resolved. | ***MUST***
<a id="req-2"></a>[Req 2] | Provide at least one machine-readable representation in RDF at the Linked Data dataset URI. | ***MUST***

Beyond confirming adherence to these principles for Australian government Linked Data, this document provides instruction on how to structure URIs for recognition and support by the AGLDWG and thus use of the persistent URI subdomain `linked.data.gov.au`.

## 3. <a id="URIRegistration"></a>URI Registration
The AGLDWG has had the URI subdomain `linked.data.gov.au` dedicated to persistent identifiers for Linked Data resources. This is to be able to supply infinitely many persistent URIs for Linked Data to any agency that are free from things which break URIs' persistence, such as agency name changes and responsibility changes in government. This subdomain is protected by a Memorandum of Understanding signed by the managing agency, the Digital Transformation Agency and 5 agencies interested in Linked Data [[AGLDWG-2018](#ref-AGLDWG-2018)] which came into effect in May, 2018.

Due to the central management by the AGLDWG of this resource and its requirement to be shared among many agencies, URIs allocated using it need to be registered to avoid collisions (agencies wanting the same URIs for different things) and also orphans (URIs once registered for which ownership information is lost). Additionally, previous approaches to URI allocation by the AGLDWG that did not require registration resulted in ungoverned URIs.

The AGLDWG notes item registration as both commonplace for shared government resources (viz. registration of datasets within [data.gov.au](https:data.gov.au)) and also for URI-based identifiers (viz. [purl.org](http://purl.org) and [w3id.org](https://w3id.org/)).

The AGLDWG requires all allocated URIs to be registered with the group and provides guidance below on what types of URIs may be registered, what the process for registration is and what information is required for registration.


## 4. <a id="URIAllocationTypes"></a>PID URI Types
Presently the AGLDWG recognises four types of items for which PID URIs may be requested:

1. Dataset
2. Definitional Resource
3. Top-Level Register
4. Second-Level Register

More types of items may be added in the future. Such an addition will require this document to be updated.

URIs for Datasets are created within the *Dataset Register*, for definitional resources within the *Def Register* and for Top-Level Register items within the *Top-Level Register*. This Top-Level Register contains both the Dataset Register and the Def Register as subregisters. Second-Level Register items are created within individual Datasets, as detailed in [Section 8](#SecondLevelRegisterURIs).

The next four sections of this document describe how URIs for these four classes of items are formulated and the processes to apply for them.


## 5. <a id="Datasets"></a>Datasets
Dataset can have URIs are the URIs that identify an entire Linked Data dataset. These URIs are somewhat analogous to the URIs used to indicate datasets in the [data.gov.au](https://data.gov.au) dataset catalogue (e.g. <https://data.gov.au/dataset/rottnest-ferries-underway-temperature> indicating the "Rottnest Ferries Underway Temperature" dataset) but they have more requirements placed on them than those in `data.gov.au` do. Where `data.gov.au` dataset URIs may be granted when certain metadata standards are met, for dataset URI allocation within `linked.data.gov.au`, datasets must ensure that **ALL** the data they contain is Linked Data.

Requirement | Description | Conformance
--|--|--
<a id="req-3"></a>[Req 3] | Dataset URIs must link only to datasets that contain only Linked Data | ***MUST***

The tests for what constitutes Linked Data and thus a Linked Data dataset are articulated in [Appendix A](#app-a).

### Dataset PID URI pattern
The pattern for Dataset PID URIs is:

```
dataset-uri ::=  protocol "://linked.data.gov.au/dataset/" dataset-id
protocol ::= "http" | "https"
dataset-id ::= *(ALPHA | DIGIT | "-")
```

Where `dataset-id` is a shortened form of the dataset title.

An example is that a Linked Data dataset titled "Geocoded National Address File" (G-NAF) could use the `dataset-id` of "gnaf" and thus make the `dataset-uri` of:

`http://linked.data.gov.au/dataset/gnaf`


### Registration Process
For this This process outline uses terminology from ISO/IEC 11179 [[ISO-2015](#ref-ISO-2015)] with specific roles in italics. The AGLDWG as a whole plays the roles of *Overall Registration Authority* and *Overall Stewardship Organization*. The Recommendations subgroup of the AGLDWG plays the role of  and may also play the role of *Controlling Committee*. The status terms used are those of the registry Ontology's status vocabulary (original resource [[17](#ref-17)], republished by the AGLDWG as [[18](#ref-18)])

* *Submitting Organization* requests an allocation for a dataset URI by creating a complete catalogue record for a dataset in the AGLDWG LD Resource Catalogue with status `submitted`.
* *Controlling Committee* inspects request and approves unless there is an obvious issue. Catalogue record status set to `approved`.
* *Steward* performs a test to verify the dataset consists only of Linked Data
* *Steward* implements URI redirect to the hosted dataset, catalogue record status set to `stable`.
* *Submitting Organization* is free to use allocated URIs

In the event of more than one request for the same `dataset-id`, application precedent wins, so the first application for a particular `dataset-id`, if successful, will be awarded it. Precedents is determined by date of application lodgement, not date of application completion.

Requirement | Description | Conformance
--|--|--
<a id="req-4"></a>[Req 4] | For a particular dataset-id to be allocated, the applicant must be the first applicant for it whose application is subsequently found eligible for that dataset-id | ***MUST***


### Required Metadata
Metadata to be supplied for the registration of a Linked Data dataset, and thus the allocation of a URI for it, must constitute a valid record for a dataset within the AGLDWG LD Resource Catalogue. Record validity is determined using the process outlined in [Appendix C](#app-c).

Entries in the AGLDWG LD Resource Catalogue are public from submission onwards.


## 6. <a id="Definitionals"></a>Definitional Resources
Definitional Resources are Linked Data vocabularies, vocabulary terms, ontologies, ontology terms and potentially other, Linked Data, data model items. Currently, as per Datasets, URI patterning is provided by the AGLDWG at the whole-of-resource level (i.e. whole ontology or whole vocabulary) with URIs for subcomponents such as vocabulary terms or ontology class definitions to be implemented by the definitional resource managers, at their discretion.

### Definitional resource PID URI pattern
The pattern for Definitional PID URIs is:

```
definitional-uri ::=  protocol "://linked.data.gov.au/def/" definitional-id
protocol ::= "http" | "https"
definitional-id ::= *(ALPHA | DIGIT | "-")
```

Where `definitional-id` is a shortened form of the definitional resource's title.

An example is that an ontology used to deliver content for a Linked Data implementation of the "Geocoded National Address File" (G-NAF) could use the `definitional-id` of "gnaf" and thus make the `definitional-uri` of:

`http://linked.data.gov.au/def/gnaf`

Another example is that a vocabulary established listing all the types of citizenship status of people in Australia titled "Citizenship Status" could use the `definitional-id` of "citstatus" and thus make the `definitional-uri` of:

`http://linked.data.gov.au/def/citstatus`


### Registration Process
The AGLDWG plays role of *Steward* and may also play the role of *Controlling Committee*.

* *Submitting Organization* requests an allocation for a dataset URI by creating a complete catalogue record for a definitional resource in the AGLDWG LD Resource Catalogue with status `submitted`.
  * if the RDF source of the resource a single file, the *Submitting Organization* should upload the source to the AGLDWG LD Resource Catalogue for hosting
* *Controlling Committee* inspects request and approves unless there is an obvious issue. Catalogue record status set to `approved`.
* *Steward* performs a test to verify the dataset consists only of Linked Data
* *Steward* implements URI redirect to the hosted dataset, catalogue record status set to `stable`.
* *Submitting Organization* is free to use allocated URIs


### Required Metadata
Metadata to be supplied for the registration of a Linked Data defenitional resource, and thus the allocation of a URI for it, must constitute a valid record for such within the AGLDWG LD Resource Catalogue. Record validity is determined using the process outlined in [Appendix C](#app-c).

Entries in the AGLDWG LD Resource Catalogue are public from submission onwards.

## 7. <a id="TopLevelRegisterURIs"></a>Top-Level Register URIs
Top-level Registers are an index of individual Linked Data objects, promoted to the 'top' of `linked.data.gov.au` for high visibility. Such registers formulated using very basic information - the identity of the register itself (given via its URI), metadata according to the Registry Ontology [[17](#ref-17)] listing the class(es) of items within it and potentially Registry Ontology links to sub pages of the register. lists of particular classes of LD objects that both allow shorter URI allocation than URIs from datasets and also allow items within them to not use URIs deriving from them. As with datasets and definitional resources registered with the AGLDWG for URI allocation, top-level registers require metadata to be lodged so that the content and ownership of the register is known and can be managed.

Since top-level registers are designed to promote and aggregate assessed in order to determine the appropriateness of the requested URI to the class(es) of objects to be listed in the register.

A simple example:

A *Submitting Organization* wishes to have a URI allocated for a top-level register of items of class *widget* and requests `linked.data.gov.au/widget/`. First the *Submitting Organization* will have to have published at least one dataset containing *widgets*, perhaps `linked.data.gov.au/dataset/ds1` containing the (second-level) register `linked.data.gov.au/dataset/ds1/widget/`. The AGLDWG will check that no `widget/` top-level register already exists and, if not, determine if the path segment `widget/` is a fair representation of the items to be listed in that register. Fairness could stem from the name 'widget' approximating the class identity of the items in the register and a minimal chance of the path segment leading users to understand some meaning other than that intended by the *Submitting Organization*, perhaps as a result of commonly used terms in the LD community.

A more complex example about inappropriate naming:

A *Submitting Organization*  wishes to allocate `linked.data.gov.au/service/` for a collection of government services to members of the public. The *Submitting Organization* has published a dataset containing a register of items of class `srv:Service` where 'srv' is a government business ontology. Here the AGLDWG cannot easily approve the request given the generic nature of 'service' which could easily be misconstrued by a user; perhaps they expect a register of Web Service objects.

A federated register example:

A *Submitting Organization*, in this case the Royal Australian Navy (RAN), wishes to allocate `linked.data.gov.au/ship/` for a list of ships that they have published in multiple datasets, `linked.data.gov.au/dataset/ds1/ship/` & `linked.data.gov.au/dataset/ds2/ship/`. The RAN will have to ensure that the allocated register resolves to a collection of ships from both datasets.

Where multiple *Submitting Organization* s wish to combine their data into a single top-level register, they must arrange for federated register presentation, not the AGLDWG.

A multi-class example:

A *Submitting Organization* wishes a top-level register for items of class A and class B. There is some real-world logic making such an allocation sensible so the *Submitting Organization* requests the top-level register `linked.data.gov.au/classAB/` which is approved. A better request though would be for a register of `linked.data.gov.au/classC/` where class C is a superclass of both class A and B.

### Use and non-use of Register URI for contained items
A *Submitting Organization* may request a top-level register such as `linked.data.gov.au/classA/` and then present items within that class with URIs such as `linked.data.gov.au/classA/1`, `linked.data.gov.au/classA/2` etc. but may also present items with un-related URIs within the register as long as the class of item (discoverable via de-referenceable RDF) accords with the class(es) for which the register was allocated. The AGLDWG may check the classes of items within a top-level register using automated means.

### Subregisters
If a *Submitting Organization* wishes to use a top-level register already allocated for new items according with the class(es) for with the register was allocated, they have two options:

1. arrange with the original *Submitting Organization* to have their items included in the register
2. request a module within the top-level register for their items

Modules requested within a top-level register will be presented as sub-registers of the top-level register. Items within

Requirement | Description | Conformance
--|--|--
<a id="req-3"></a>[Req 3] | Dataset URIs must link only to Linked Data datasets | ***MUST***

The tests for what constitutes Linked Data and thus a Linked Data dataset are articulated in [Appendix 1](#app-a).

### Dataset URI pattern
The pattern for allocating Dataset URIs is:

```
dataset-uri ::=  protocol "://linked.data.gov.au/dataset/" dataset-id
protocol ::= "http" | "https"
dataset-id ::= *(ALPHA | DIGIT | "-")
```

Where `dataset-id` is a shortened form of the dataset title.

An example is that a Linked Data dataset titled "Geocoded National Address File" (G-NAF) could use the `dataset-id` of "gnaf" and thus make the `dataset-uri` of:

`http://linked.data.gov.au/dataset/gnaf`

### Registration Process

### Required Metadata
Metadata to be supplied for the registration of a Linked Data register, and thus the allocation of a URI for it, must constitute a valid record for such within the AGLDWG LD Resource Catalogue. Record validity is determined using the process outlined in [Appendix C](#app-c).

Entries in the AGLDWG LD Resource Catalogue are public from submission onwards.


## 8. <a id="SecondLevelRegisterURIs"></a>Second-Level Register URIs


## 9. <a id="References"></a>References

[W3C-2018] <a name="ref-W3C-2018"></a> World Wide Web Consortium, "Linked Data", web page, 2018. <https://www.w3.org/standards/semanticweb/data>, accessed 2018-07-27.

[TBL-2006] <a name="ref-TBL-2006"></a>Berners-Lee, Tim "Linked Data", web page, 2006. <http://www.w3.org/DesignIssues/LinkedData.html>, accessed 2018-06-07.  

[AGLDWG-2018] <a name="ref-AGLDWG-2018"></a>Australian Government Linked Data Working Group "Governance", web page, 2018. <http://www.linked.data.gov.au/governance>, accessed 2018-07-27.

[CAB-2010] <a name="ref-CAB-2010"></a>Cabinet Office, "Designing URI Sets for the UK Public Sector", web page, 2010. <https://www.gov.uk/government/publications/designing-uri-sets-for-the-uk-public-sector>, accessed 2018-06-07.  

[3] <a name="ref-3"></a>World Wide Web Consortium "223 Best Practices URI Construction", wiki web page, 2012. <http://www.w3.org/2011/gld/wiki/223_Best_Practices_URI_Construction>, accessed 2018-06-07.  

[//]: # TODO: remove next reference [4] as broken  
[4] Defra, UK Linked Data,<a href="http://location.defra.gov.uk/resources/linked-data/">http://location.defra.gov.uk/resources/linked-data/</a>  

[5] <a name="ref-5"></a>World Wide Web Consortium "Data Catalog Vocabulary (DCAT)", W3C Recommendation, 16 January 2014. <https://www.w3.org/TR/vocab-dcat/>, accessed 2018-06-07.  

[6] <a name="ref-6"></a>Dublin Core Metadata Initiative "DCMI Metadata Terms", web page, 2012. <http://www.dublincore.org/documents/dcmi-terms/>, accessed 2018-06-07.  

[7] <a name="ref-7"></a>Internet Engineering Task Force "RFC6570: URI Template", proposed standard, 2012. <http://tools.ietf.org/html/rfc6570>, accessed 2018-06-07.  

[8] <a name="ref-8"></a>Fielding, Roy T. "[httpRange-14] Resolved", archived email, 2005. <http://lists.w3.org/Archives/Public/www-tag/2005Jun/0039.html>, accessed 2018-06-07.  

[9] <a name="ref-9"></a>World Wide Web Consortium "Cool URIs for the Semantic Web", W3C Interest Group Note, 03 December 2008. <http://www.w3.org/TR/cooluris/>, accessed 2018-06-07.  

[10] <a name="ref-10"></a>Internet Engineering Task Force "RFC2616: Hypertext Transfer Protocol -- HTTP/1.1", Request for Comment, 1999. <http://www.ietf.org/rfc/rfc2616>, accessed 2018-06-07.  

[IETF-1997] <a name="ref-IETF-1997"></a>Internet Engineering Task Force, Network Working Group "Key words for use in RFCs to Indicate Requirement Levels", Request for Comments: 2119, 1997. <http://www.ietf.org/rfc/rfc2119>, accessed 2018-06-07.

[12] <a name="ref-12"></a>World Wide Web Consortium "RDF 1.1 Concepts and Abstract Syntax", W3C Proposed Recommendation, 09 January 2014. <http://www.w3.org/TR/rdf11-concepts/>, accessed 2018-06-07.  

[IETF-2008] <a name="ref-IETF-2008"></a>Internet Engineering Task Force, Network Working Group "Internet Standard 68: Augmented BNF for Syntax Specifications: ABNF". Internet Engineering Task Force, 2008. <https://tools.ietf.org/html/std68>, accessed 2018-06-07.  

[ISO-2015] <a name="ref-ISO-2015"></a>International Organization for Standardization / International Electrotechnical Commission "ISO/IEC 11179, Information Technology -- Metadata registries (MDR)", standard. <http://metadata-standards.org/11179/>, accessed 2018-06-07.

[//]: # TODO: create
[15] <a name="ref-15"></a>Australian Government Linked Data Working Group "AGLDWG profile of DCAT 2018", Web Ontology Language standard profile. <http://linked.data.gov.au/def/dataset>, accessed 2018-06-07.

[16] <a name="ref-16"></a>World Wide Web Consortium "RDF Schema 1.1", W3C Recommendation, 25 February 2014. <http://www.w3.org/TR/rdf-schema/>, accessed 2018-07-22.

[17] <a name="ref-17"></a>Reynolds, Dave "Registry ontology", Version 0.2. OWL Ontology,  2012-11-11 <http://epimorphics.com/public/vocabulary/Registry.html>, accessed 2018-07-22.

[18] <a name="ref-18"></a>Australian Government Linked Data Working Group, "Status Vocabulary". SKOS Vocabulary, 22 July 2018. <http://test.linked.data.gov.au/def/status>, accessed 2018-07-22.

[19] <a name="ref-19"></a>World Wide Web Consortium "Data Catalog Vocabulary (DCAT)", W3C Recommendation, 16 January 2014. <https://www.w3.org/TR/vocab-dcat/>, accessed 2018-07-22.

## 10. <a id="app-a"></a>Appendix A: Dataset Linked Data requirements
Datasets submitted to the AGLDWG for registration, and thus URI allocation, must be valid Linked Data. What this means is that the dataset must:

1. have all the data elements within the dataset discoverable via Linked Data
  * elements of the data may themselves not be in Linked Data formats, for example results from a Web Feature Service request, but all data elements identified within the dataset must be discoverable via Linked Data methods such as the *follow-your-nose* link-following to navigate from a dataset to its registers, to sub-registers, and on to individual items
2. contain registers of all data elements
  * some method must be available to discover and use a register of all of the data elements contained within the dataset

## 11. <a id="app-a"></a>Appendix B: Definitional resource modelling requirements
Definitional resources (ontologies and vocabularies) submitted to the AGLDWG for registration, and thus URI allocation, must be valid RDFS documents adhering to the RDFS specification [[16](#ref-16)].

Other AGLDWG initiatives might require other systems adherence for definitional resources (e.g. OWL or SKOS) but the AGLDWG will always be able to register RDFS resources.

## 12. <a id="app-b"></a>Appendix C: Lodging and validating registered resource metadata
Resources submitted to the AGLDWG for URI allocation are required to have metadata supplied in order to enable resource management, including cataloguing. This is specified as, at the time of this Guideline's first issuing, metadata that completes a simple profile of the DCAT Vocabulary's [[19](#ref-19)] metadata for a Catalogue Record, with some additions for status management.

Currently all resources requiring URIs must have supplied:

* [`dct:title`](http://www.dublincore.org/documents/dcmi-terms/#terms-title)
* [`dct:description`](http://www.dublincore.org/documents/dcmi-terms/#terms-description)
* [`dct:creator`](http://www.dublincore.org/documents/dcmi-terms/#terms-creator)
  * the resource creator, not the creator of the URI allocation requests
* [`dcat:contactPoint`](https://www.w3.org/TR/vocab-dcat/#Property:dataset_contactPoint)
  * contact point for the resource, not the URI request

* dateSubmitted [`dct:dateSubmitted`](http://www.dublincore.org/documents/dcmi-terms/#terms-dateSubmitted)
* dataAccepted [`dct:dateAccepted`](http://www.dublincore.org/documents/dcmi-terms/#terms-dateAccepted)


1. metadata entered into the AGLDWG LD Resource Catalogue pertaining to the type of item requested (deataset, definitional, register).
  * if the
2. metadata must pass validation against the AGLDWG's profile of the DCAT 2018 dataset vocabulary [[15](#ref-15)]
  * validation will happen automatically on submission of the AGLDWG Dataset Register's New Dataset form or on lodgement of an RDF document with the AGLDWG Dataset Register's New Dataset document API endpoint

See the documentation on the AGLDWG Dataset Register for further explanations:
