#### Australian Government Linked Data Working Group

# URI Guidelines v2.0
#### (June 06 2018)

*This document is a second and very different version of the* Guidelines *produced by the Australian Government Linked Data Working Group. See *[the guidelines repository](https://github.com/AGLDWG/TR/tree/master/guidelines) *for previous versions.*


## Table of Contents
1. [Conformance](#Conformance)
2. [Introduction](#Introduction)
3. [URI Registration](#URIRegistration)
4. [URI Allocation Types](#URIAllocationTypes)
5. [Dataset URIs](#DatasetURIs)
6. [Definitional URIs](#DefinitionalURIs)
7. [Top-Level Register URIs](#TopLevelRegisterURIs)
8. [Second-Level Register URIs](#SecondLevelRegisterURIs)
9. [References](#References)
10. [Appendix A: Dataset Linked Data requirements](#app-a)
11. [Appendix B: Lodging and validating Dataset metadata](#app-b)

## 1. <a id="Conformance"></a> Conformance
#### The key words *MUST*, *MUST NOT*, *REQUIRED*, *SHOULD*, *SHOULD NOT*, *RECOMMENDED*, *MAY*, and *OPTIONAL* in this document are to be interpreted as defined in [[11](#ref-11)].
#### URI patterns are expressed using Augmented Backus-Naur Form, as defined in [[13](#ref-13)]
#### Registration process roles are to be interpreted as defined in [[14](#ref-14)]

## 2. <a id="Introduction"></a>Introduction
[//]: # entities in original replaced with things due to confusion over word entity
[//]: # digital things - dataset, classification concepts - added as they are in use and likely targets of URIs      
Government departments and agencies assign identifiers to many things they are responsible for - e.g. datasets, classification concepts, hospitals, equipment, etc. These identifiers are then used when referring to or making statements about particular things. For example, when referring to a road closure, the identifier (e.g. "M5") will be used to inform the public or when referring to a particular census Mesh Block, its identifier, perhaps "80006300000" will be used.

[//]: # reference the PC report or similar  
Government published, public sector information (PSI), usually about the things agencies are responsible for, is intended to be re-used by many, initially perhaps unknown, applications over time to maximise its value to the nation. For this reason, it is important that elements of it are able to be identified and accessed in consistent ways for long periods (perhaps multiple decades).

The Australian Government Linked Data Working Group (AGLDWG) advocates the use of Linked Data [[1](#ref-1)] as a particular set of technologies to be used for Internet-distributed, machine-readable data and, due to this, advocates the use of Linked Data URIs for identifiers for things.

### 2.1 Uniform Resource Locators (URIs)
Linked Data uses Uniform Resource Identifiers (URI) which are part of a single, global, identification system used on the World Wide Web, similar to telephone numbers in a public switched telephone network. We are all familiar with URIs at work due to their use for addresses in browsers for web pages. URIs are a key technology to support Linked Data by offering a generic mechanism to identify *things*. In order to publish data in a Linked Data fashion, government needs to represent the identifiers they use for things using URIs.

Sir Tim Berners-Lee who created many aspects of the World Wide Web we now take for granted also defined principles for the use of URIs with Linked Data [[2](#ref-2)]. This document builds on those principles which, summarised are:

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
The AGLDWG has had the URI subdomain `linked.data.gov.au` dedicated to persistent identifiers for Linked Data resources. This is to be able to supply infinitely many persistent URIs for Linked Data to any agency that are free from things which break URIs' persistence, such as agency name changes and responsibility changes in government. This subdomain is protected by a Memorandum of Understanding signed by the managing agency, the Digital Transformation Agency and 5 agencies interested in Linked Data [[3](#ref-3)] which came into effect in May, 2018.

Due to the central management by the AGLDWG of this resource and its requirement to be shared among many agencies, URIs allocated using it need to be registered to avoid collisions (agencies wanting the same URIs for different things) and also orphans (URIs once registered for which ownership information is lost). Additionally, previous approaches to URI allocation by the AGLDWG that did not require registration resulted in ungoverned URIs.

The AGLDWG notes item registration as both commonplace for shared government resources (viz. registration of datasets within [data.gov.au](https:data.gov.au)) and also for URI-based identifiers (viz. [purl.org](http://purl.org) and [w3id.org](https://w3id.org/)).

The AGLDWG requires all allocated URIs to be registered with the group and provides guidance below on what types of URIs may be registered, what the process for registration is and what information is required for registration.


## 4. <a id="URIAllocationTypes"></a>URI Allocation Types
Presently the AGLDWG recognises *at least* four types of URIs that may be registered using `linked.data.gov.au`:

1. Dataset
2. Definitional Resource
3. Top-Level Register
4. Second-Level Registers

The next four sections of this document deal with these types of URI. Further types may be added in the future.


## 5. <a id="DatasetURIs"></a>Dataset URIs
Dataset URIs are the URIs that indicate an entire Linked Data dataset. These URIs are somewhat analogous to the URIs used to indicate datasets in the [data.gov.au](https://data.gov.au) dataset catalogue (e.g. <https://data.gov.au/dataset/rottnest-ferries-underway-temperature> indicating the "Rottnest Ferries Underway Temperature" dataset) but they have more requirements placed on them than those in `data.gov.au` do. Where `data.gov.au` dataset URIs may be granted when certain metadata standards are met, for dataset URI allocation within `linked.data.gov.au` datasets must ensure that **ALL** the data they contain is Linked Data.

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

An example is that a Linked Data titled "Geocoded National Address File" (G-NAF) could use the `dataset-id` of "gnaf" and thus make the `dataset-uri` of:

`http://linked.data.gov.au/dataset/gnaf`


### Registration Process
This process outline uses terminology from ISO/IEC 11179 [[4](#ref-4)] with specific roles in italics. The AGLDWG plays the role of *Steward* and may also play the role of *Controlling Committee*.

* *Submitting Organization* requests an allocation for a dataset URI by lodging valid dataset metadata
* *Controlling Committee* inspects request and approves unless there is an obvious issue
* *Steward* publishes supplied metadata in the public dataset catalogue
* *Steward* performs a test to verify the dataset consists only of Linked Data
* *Steward* implements URI redirect to the hosted dataset
* *Submitting Organization* is free to use allocated URIs

In the event of more than one request for the same `dataset-id`, application precedent wins, so the first application for a particular `dataset-id`, if successful, will be awarded it. Precedents is determined by date of application lodgement, not date of application completion.

Requirement | Description | Conformance
--|--|--
<a id="req-4"></a>[Req 4] | For a particular dataset-id to be allocated, the applicant must be the first applicant for it whose application is subsequently found eligible for that dataset-id | ***MUST***


### Required Metadata
Metadata to be supplied for the registration of a Linked Data dataset, and thus the allocation of a URI for it, must constitute a valid record within the AGLDWG's Dataset Register. Record validity is determined using the process outlined in [Appendix B](#app-b).

Valid metadata will be used to create a public catalogue entry for the dataset.


[//]: # TODO: Simon to add  
## 6. <a id="DefinitionalURIs"></a>Definitional URIs
Definitional URIs are allocated for Linked Data vocabularies, vocabulary terms, ontologies, ontology terms and potentially other, Linked Data, data model items.


### Definitional URI pattern

The pattern for allocating Definitional URIs is:

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

* *Submitting Organization* requests an allocation for a definitional resource URI by lodging a valid definitional resource
* *Controlling Committee* inspects request and approves unless there is an obvious issue
* is the resource a "small" resource, less than 1MB:
  * *Steward* publishes the definitional resource in the public definitional resource catalogue
* *Steward* performs a test to verify the dataset consists only of Linked Data
* *Steward* implements URI redirect to the hosted dataset
* *Submitting Organization* is free to use allocated URIs

*Submitting Organization* requests a URI allocation for a definitional resource
Controlling Committee inspects request, approves unless an obvious issue
Steward registers supplied metadata in def catalogue
Steward establishes a master repository for the ont/voc
If ont: Steward builds HTML version of ontology for display
If voc: Steward requires display of voc from Submitting Organization (e.g. ANDS RVA)
If ont, Steward hosts display copy of ontology on AGLDGW server and redirects allocated URI to it
If voc, Steward redirects URIs to voc host
Submitting Organization can update the ontology via Pull Requests to the master repository which will be reviewed
by Controlling Committee

### Required Metadata


## 7. <a id="TopLevelRegisterURIs"></a>Top-Level Register URIs
### Registration Process

### Required Metadata


## 8. <a id="SecondLevelRegisterURIs"></a>Second-Level Register URIs

[//]: # TODO: update all reference numbers
## 9. <a id="References"></a>References
[1] <a name="ref-1"></a>Berners-Lee, Tim "Linked Data", web page, 2006. <http://www.w3.org/DesignIssues/LinkedData.html>, accessed 2018-06-07.  

[2] <a name="ref-1"></a>Cabinet Office, "Designing URI Sets for the UK Public Sector", web page, 2010. <https://www.gov.uk/government/publications/designing-uri-sets-for-the-uk-public-sector>, accessed 2018-06-07.  

[3] <a name="ref-3"></a>World Wide Web Consortium "223 Best Practices URI Construction", wiki web page, 2012. <http://www.w3.org/2011/gld/wiki/223_Best_Practices_URI_Construction>, accessed 2018-06-07.  

[//]: # TODO: remove next reference [4] as broken  
[4] Defra, UK Linked Data,<a href="http://location.defra.gov.uk/resources/linked-data/">http://location.defra.gov.uk/resources/linked-data/</a>  

[5] <a name="ref-5"></a>World Wide Web Consortium "Data Catalog Vocabulary (DCAT)", W3C Recommendation, 16 January 2014. <https://www.w3.org/TR/vocab-dcat/>, accessed 2018-06-07.  

[6] <a name="ref-6"></a>Dublin Core Metadata Initiative "DCMI Metadata Terms", web page, 2012. <http://www.dublincore.org/documents/dcmi-terms/>, accessed 2018-06-07.  

[7] <a name="ref-7"></a>Internet Engineering Task Force "RFC6570: URI Template", proposed standard, 2012. <http://tools.ietf.org/html/rfc6570>, accessed 2018-06-07.  

[8] <a name="ref-8"></a>Fielding, Roy T. ""[httpRange-14] Resolved", archived email, 2005. <http://lists.w3.org/Archives/Public/www-tag/2005Jun/0039.html>, accessed 2018-06-07.  

[9] <a name="ref-9"></a>World Wide Web Consortium "Cool URIs for the Semantic Web", W3C Interest Group Note, 03 December 2008. <http://www.w3.org/TR/cooluris/>, accessed 2018-06-07.  

[10] <a name="ref-10"></a>Internet Engineering Task Force "RFC2616: Hypertext Transfer Protocol -- HTTP/1.1", Request for Comment, 1999. <http://www.ietf.org/rfc/rfc2616>, accessed 2018-06-07.  

[11] <a name="ref-11"></a>Internet Engineering Task Force, Network Working Group "Key words for use in RFCs to Indicate Requirement Levels", .</a> Request for Comments: 2119, 1997. <http://www.ietf.org/rfc/rfc2119>, accessed 2018-06-07.

[12] <a name="ref-12"></a>World Wide Web Consortium "RDF 1.1 Concepts and Abstract Syntax", W3C Proposed Recommendation, 09 January 2014. <http://www.w3.org/TR/rdf11-concepts/>, accessed 2018-06-07.  

[13] <a name="ref-13"></a>Internet Engineering Task Force, Network Working Group "Internet Standard 68: Augmented BNF for Syntax Specifications: ABNF". Internet Engineering Task Force, 2008.   <https://tools.ietf.org/html/std68>, accessed 2018-06-07.  

[14] <a name="ref-14"></a>International Organization for Standardization / International Electrotechnical Commission "ISO/IEC 11179, Information Technology -- Metadata registries (MDR)", standard. <http://metadata-standards.org/11179/>, accessed 2018-06-07.

[//]: # TODO: create
[15] <a name="ref-15"></a>Australian Government Linked Data Working Group "AGLDWG profile of  DCAT 2018", Web Ontology Language standard profile. <http://linked.data.gov.au/def/dataset>, accessed 2018-06-07.


## 10. <a id="app-a"></a>Appendix A: Dataset Linked Data requirements
Datasets submitted to the AGLDWG for registration, and thus URI allocation, must be valid Linked Data. What this means is that the dataset must:

1. have all elements of the data with the dataset discoverable via Linked Data navigation
  * elements of the data may themselves not be in Linked Data formats, for example results from a Web Feature Service request, but all data elements identified within the dataset must be discoverable via Linked Data methods such as the *follow-your-nose* link-following method to navigate from registers to sub-registers to individual items
2. contain registers of all data elements
  * some method must be available to discover and use a register of all of the data elements contained within the dataset


## 11. <a id="app-b"></a>Appendix B: Lodging and validating Dataset metadata
Datasets submitted to the AGLDWG Dataset Register are required to have metadata presented in the following ways:

1. metadata must be presented in an RDF format OR entered into the AGLDWG Dataset Register using the New Dataset form
2. metadata must pass validation against the AGLDWG's profile of the DCAT 2018 dataset vocabulary [[15](#ref-15)]
  * validation will happen automatically on submission of the AGLDWG Dataset Register's New Dataset form or on lodgement of an RDF document with the AGLDWG Dataset Register's New Dataset document API endpoint

See the documentation on the AGLDWG Dataset Register for further explanations:

[//]: # TODO: implement at least a bare-bones register
* [AGLDWG Dataset Register](http://linked.data.gov.au/dataset/)



# OLD GUIDELINES DOC FOLLOWING

## <a name="DatasetURIs" id="DatasetURIs"></a>2. Linked Data dataset URIs

For the purpose of this document a *Linked Data dataset* published within the data.gov.au domain is defined as a collection of data, each with supporting metadata, published and maintained under the data.gov.au domain, available as RDF, and accessible through dereferenceable HTTP Universal Resource Identifiers (URIs).<br />HTTP URIs, a component of the World Wide Web, provides a means of uniquely identifying a 'Thing' (or 'Resource') in this case a *Linked Data dataset*. *Linked Data datasets* provide the opportunity to share common meaning and common identifiers across the public sector, and to provide comprehensive and reliable identifiers for a collection of 'Things' such as the hospitals, schools or roads in a region, climate data for a specific year etc.

A Linked Data dataset consists of:

<ol>
 <li>the URI to identify the set</li>
 <li>metadata to describe its quality characteristics</li>
 <li>a URI that references a list of resources (*Identifier URIs* and *Document URIs*) defined in the Linked Data dataset</li>
 <li>references to *Ontology URIs* which define the concept and relationships used within the Linked Data dataset</li>
</ol>


<br />For the *Linked Data dataset URI* the following pattern is proposed. The pattern notation used in this document is based on the &ldquo;URI Template&rdquo; specification defined in RFC6570 [7]. In addition square brackets '[' and ']' are used to introduce optional components and a star, i.e. '*' following such a bracket component allows arbitrary repetition of the group (zero or more times).<br />

Requirement | Description | Conformance
--|--|--
<table border="1" cellspacing="0" cellpadding="0">
 <tr>
  <td width="80" valign="top"><b>[no 3]</b></td>
<td width="150" valign="top">***Dataset URI***</td>
  <td width="398" valign="top">The *Dataset URI* ***MUST ***contain the string 'dataset', and an appropriate identifier **{datasetid}** describing the nature of the 'Dataset'.

<i>URI Pattern</i><br />**/dataset/{datasetid}**

*Example* **/dataset/schools**</td>
<td width="100" valign="top"><b><i>MUST</i></b></td></tr>
</table>


Datasets are often hierarchically structured, i.e. there exists a superset that consists of multiple parts, for example, a dataset for schools that consist of a dataset for primary schools and secondary schools. Multiple hierarchies may co-exist, for example a dataset for schools may also consist of datasets for public and independent schools. For modelling this hierarchy we propose the use of path segments in the *URI*:

Requirement | Description | Conformance
--|--|--
<table border="1" cellspacing="0" cellpadding="0">
<tr>
   <td width="80" valign="top"><b>[no 4]</b></td>
   <td width="150" valign="top">***Modularised Dataset URI***</td>
<td width="398" valign="top">Optionally, it can also be hierarchically structured with an arbitrary number of path segments that are denoted with the identifier **{module} **below.

<i>URI Pattern</i><br />**/dataset[/{module}]*/{datasetid}**

*Example* **/dataset/act/schools**</td>
<td width="100" valign="top"><b><i>SHOULD</i></b></td>
</tr>
</table>


**Metadata requirements for Linked Data datasets**<br />For expressing the *metadata to describe the quality characteristics* of a dataset the use of DCAT (Data Catalog Vocabulary) [5] is ***RECOMMENDED***, a vocabulary that provides terms and patterns for describing RDF datasets. Consequently, a *Linked Data dataset URI* ***SHOULD ***be a member of the class dcat:Dataset.


For modularised datasets, each module ***SHOULD ***be a member of the dcat:Catalog class. All datasets within a module ***SHOULD*** be referenced with a dcat:dataset property from the *URI* that describes the module (i.e. a member of the dcat:Catalog class). This *Catalogue URI* ***SHOULD*** be dereferenceable at the top-level path segment of the module. For example, for the modularised<b> /dataset/act/schools </b>dataset, the dcat:Catalog *URI* is<b> /dataset/act </b>that references the schools dataset and all other datasets within this module with the dcat:dataset property.<br /> Summarising, the specific guidelines for adding metadata to Linked Data datasets are:

Requirement | Description | Conformance
--|--|--
<table border="1" cellspacing="0" cellpadding="0">
<tr>
   <td width="80" valign="top"><b>[no 5]</b></td>
<td width="478" valign="top">
A Linked Data dataset URI is defined as a member of the class dcat:Dataset of the Data Catalog Vocabulary (DCAT).</td>
<td width="100" valign="top"><b><i>SHOULD</i></b></td></tr>
<tr>
   <td width="80" valign="top"><b>[no 6]</b></td>
<td width="478" valign="top">
For modularised datasets, the top-level module is declared as a member of the dcat:Catalog class with all datasets within this module referenced through a dcat:dataset property.</td>
<td width="100" valign="top"><b><i>SHOULD</i></b></td></tr>
<tr>
   <td width="80" valign="top"><b>[no 7]</b></td>
<td width="478" valign="top">
A Linked Data dataset has one or many publishers defined through the Dublin Core [6] dct:publisher property.</td>
<td width="100" valign="top"><b><i>SHOULD</i></b></td></tr>
<tr>
    <td width="80" valign="top"><b>[no 8]</b></td>
<td width="478" valign="top">
A Linked Data dataset defines its license with the Dublin Core dct:license property.</td>
<td width="100" valign="top"><b><i>SHOULD</i></b></td></tr>
</table>


<br/>**Dataset ROOT**<br />The &ldquo;dataset root&rdquo; URI containing the string 'dataset' ***SHOULD*** reference a list of all Linked Data datasets in the domain.

Requirement | Description | Conformance
--|--|--
<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="80" valign="top"><b>[no 9]</b></td>
    <td width="478" valign="top">The *Dataset ROOT URI* (i.e. http://{domain}.linked.data.gov.au/dataset) results in a list of all *Dataset URIs* in its {domain}.</td>
<td width="100" valign="top"><b><i>SHOULD</i></b></td></tr>
</table>


<br />**General design principles**  The following table summarises the guidelines proposed in the previous paragraphs and introduces further general design principles for publishing Linked Data datasets that are derived from existing good practices [1,2,3,4] and revised to meet some specific requirements for the Australian public sector:

Requirement | Description | Conformance
--|--|--
<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="100" valign="top"><b>[no 10]</b></td>
    <td width="467" valign="top">Provide a human-readable representation in HTML at the *Dataset URI*.</td>
    <td width="100" valign="top">***MUST***</td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 11]</b></td>
    <td width="467" valign="top">If multiple representations exist, provide a means of discovering specific URIs for each of the available representations.</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 12]</b></td>
    <td width="467" valign="top">The license for inspection or use of the Linked Data dataset shall be provided using a common vocabulary.</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 13]</b></td>
    <td width="467" valign="top">The metadata for a Linked Data dataset should be provided using a common vocabulary and contain the expected longevity and maintenance plans for the *Dataset URI*.</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 14]</b></td>
    <td width="467" valign="top">The current technical implementation of a data publication system should not be visible in or otherwise affect the URI for a Linked Data dataset.</td>
    <td width="100" valign="top">***SHOULD NOT***</td>
  </tr>
</table>

## <a name="h.yhbu9svf0ixu" id="h.yhbu9svf0ixu"></a>3. Domain structure


linked.data.gov.au currently supports 26 sub-sub-domain names to be used for Linked Data datasets that are defined according to the top level of the Australian Governments' Interactive Functions Thesaurus (AGIFT)<a href="#_ftn1" name="_ftnref1" title="" id="_ftnref1"> </a>. The supported sub-domain names are:

<table border="0" cellspacing="0" cellpadding="0">
  <tr><td>business.linked.data.gov.au</td><td>(BUSINESS SUPPORT AND REGULATION)</td></tr>
  <tr><td>communications.linked.data.gov.au</td><td>(COMMUNICATIONS)</td></tr>
  <tr><td>communityservices.linked.data.gov.au</td><td>(COMMUNITY SERVICES)</td></tr>
  <tr><td>culture.linked.data.gov.au</td><td>(CULTURAL AFFAIRS)</td></tr>
  <tr><td>defence.linked.data.gov.au</td><td>(DEFENCE)</td></tr>
  <tr><td>education.linked.data.gov.au</td><td>(EDUCATION AND TRAINING)</td></tr>
  <tr><td>employment.linked.data.gov.au</td><td>(EMPLOYMENT)</td></tr>
  <tr><td>environment.linked.data.gov.au</td><td>(ENVIRONMENT)</td></tr>
  <tr><td>finance.linked.data.gov.au</td><td>(FINANCE MANAGEMENT)</td></tr>
  <tr><td>internationalrelations.linked.data.gov.au</td><td>(INTERNATIONAL RELATIONS)</td></tr>
  <tr><td>governance.linked.data.gov.au</td><td>(GOVERNANCE)</td></tr>
  <tr><td>health.linked.data.gov.au</td><td>(HEALTH CARE)</td></tr>
  <tr><td>immigration.linked.data.gov.au</td><td>(IMMIGRATION)</td></tr>
  <tr><td>indigenous.linked.data.gov.au</td><td>(INDIGENOUS AFFAIRS)</td></tr>
  <tr><td>infrastructure.linked.data.gov.au</td><td>(CIVIC INFRASTRUCTURE)</td></tr>
  <tr><td>justice.linked.data.gov.au</td><td>(JUSTICE ADMINISTRATION)</td></tr>
  <tr><td>maritime.linked.data.gov.au</td><td>(MARITIME SERVICES)</td></tr>
  <tr><td>primaryindustry.linked.data.gov.au</td><td>(PRIMARY INDUSTRIES)</td></tr>
  <tr><td>recreation.linked.data.gov.au</td><td>(SPORT AND RECREATION)</td></tr>
  <tr><td>resources.linked.data.gov.au</td><td>(NATURAL RESOURCES)</td></tr>
  <tr><td>science.linked.data.gov.au</td><td>(SCIENCE)</td></tr>
  <tr><td>security.linked.data.gov.au</td><td>(SECURITY)</td></tr>
  <tr><td>statistics.linked.data.gov.au</td><td>(STATISTICAL SERVICES)</td></tr>
  <tr><td>tourism.linked.data.gov.au</td><td>(TOURISM)</td></tr>
  <tr><td>trade.linked.data.gov.au</td><td>(TRADE)</td></tr>
  <tr><td>transport.linked.data.gov.au</td><td>(TRANSPORT)</td></tr>
</table>


The publisher of a Linked Data dataset can chose the sub-domain they feel is appropriate for the entities contained within the dataset. If it is unclear  which sub-domain is appropriate for a particular Linked Data dataset the <a href="http://naa.gov.au/agift/search.htm">National Archives search tool</a> can be used to help identify the government function matching most closely with the domain of the entities  contained in the Linked Data dataset.

Requirement | Description | Conformance
--|--|--
<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="100" valign="top"><b>[no 15]</b></td>
    <td width="467" valign="top">All Linked Data datasets published under linked.data.gov.au use a sub-domain of linked.data.gov.au to identify all entities within the Linked Data dataset.</td>
    <td width="100" valign="top">***MUST***</td>
  </tr>
</table>


Agencies can request to be the custodian for one of the 25 sub-domains. It is expected that custodians have a robust, secure and highly available hosting environment in place. This is particularly important when the custodian of a sub-domain is also administering redirects for modules under this sub-domain and that are provisioned by other agencies. Where a number of agencies supply content for a single sub-domain (e.g. environment.linked.data.gov.au is likely to be used by multiple agencies publishing Linked Data datasets) it may be worth exploring the use of an independent proxy service, which is highly available, and with the single purpose of redirecting traffic to the appropriate infrastructure hosting the dataset.


For choosing the sub-domain name for a Linked Data dataset the following principles have been defined which are based on existing good practice and revised to meet the requirements for datasets in the Australian public sector:<br />

Requirement | Description | Conformance
--|--|--
<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="100" valign="top"><b>[no 16]</b></td>
    <td width="467" valign="top">**linked.data.gov.au** is the base domain for Linked Data datasets that are promoted for re-use.</td>
    <td width="100" valign="top">***MUST***</td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 17]</b></td>
    <td width="467" valign="top">The government function (e.g. 'education',    'environment', 'health', 'defence', 'location') according to the top level of the Australian Governments' Interactive Functions Thesaurus (AGIFT) is included in the domain name of the URI.</td>
    <td width="100" valign="top">***MUST***</td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 18]</b></td>
    <td width="467" valign="top">The name of the department or agency currently responsible for a dataset ***SHALL NOT*** be used in persistent URIs (unless it happens to match the function in AGIFT).</td>
    <td width="100" valign="top">***MUST NOT***</td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 19]</b></td>
    <td width="467" valign="top">The sub-domain supports a direct response (note: this may be implemented as a redirect to department/agency servers from the sub-domain).</td>
    <td width="100" valign="top">***MUST***</td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 20]</b></td>
    <td width="467" valign="top">The sub-domain are maintained in perpetuity.</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
</table>

## <a name="h.blxw9q9b2rlf" id="h.blxw9q9b2rlf"></a>4. URI patterns</h2>

A URI can be used to denote a resource, which is either an Information Resource, or a *Non-Information Resource*. For example, a document, which describes a person including their name, address etc., is an *Information Resource*. The actual person (in the real-world) is a *Non-Information Resource*. Since *Information Resources* (documents, images, datasets etc.) can be served directly, the server returns a representation of the current state of the resource and sends it back to the client, with the HTTP response code 200 OK. *Non-Information Resources* cannot be dereferenced directly, so the server responds by pointing the client to another URI, which is for an information resource which describes the original (non-information) resource, and sets the HTTP response code to 303 See Other.

The following table describes the resource types for which a URI pattern guideline is defined. Section 5 then defines how the server implementing the pattern should resolve these URIs.

Requirement | Description | Conformance
--|--|--
<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="212" valign="top">**Type of Resource**</td>
    <td width="155" valign="top">**Type of URI**</td>
    <td width="367" valign="top">**Definition**</td>
  </tr>
  <tr>
    <td width="212" valign="top">A real-world 'Thing'<br />
        ***(Non-Information Resource)***</td>
    <td width="155" valign="top">***Identifier URI***</td>
    <td width="367" valign="top">Identifies some physical or abstract real-world thing that may be referred to in statements.<br />
        ***Example of physical real-world 'Things':*** a person, a school, a road, a museum etc.<br />
        ***Example of abstract real-world 'Things':***  
        a government sector, an ethnic group etc.</td>
  </tr>
  <tr>
    <td width="212" valign="top">A regular document<br />
        ***(Information Resource)***</td>
    <td width="155" valign="top">***Document URI***</td>
    <td width="367" valign="top">Identifies a document that may be referred to in statements. The *Document URI* should resolve directly to a document on the Web.</td>
  </tr>
  <tr>
    <td width="212" valign="top">Definitions of characteristics of a Real-world 'Thing'<br />
        ***(Information Resource)***</td>
    <td width="155" valign="top">***Ontology URI***</td>
    <td width="367" valign="top">Definition of concepts and relations contained within ontologies that define characteristics of a real-world 'Thing'.<br />
        **Example of a definition of a real-world 'Thing':** a 'Person' class with properties such as a 'firstname', 'lastname', 'social security number', 'address', etc.<br />
        'Ontology URIs' can be looked up and return a definition or a set of definitions about a real-world thing, e.g. the 'Person' class URI will return the set of properties listed above.</td>
  </tr>
</table>


In the following section guidelines for the URI patterns for the different resource types are proposed.


For *Non-Information Resources*, i.e. *Identifier URIs*, there are two URI patterns that are commonly used in the Linked Data Web: *Hash URIs* and* Slash URIs. *Different patterns are proposed for each of these. The HTTP protocol allows resources denoted by *Slash URIs* to be accessed directly, so these are often more effective, but *Hash URIs* are easier to deploy in practice, because only one URI is to be dealt with on the server. Several factors will determine which publishing method is best in a given use case.


Figure 1 provides a decision tree defining tests to best decide between the two publishing methods.
<ol>
 <li>The first test is whether the data publisher also has control of the sub-domain in which the dataset is published. If an agency is publishing a Linked Data dataset in a sub-domain for which it is not the custodian, *Hash URIs **SHOULD ***be used. This recommendation is made to simplify the management of redirects.</li>
 <li>Similarly, if the custodian of a sub-domain is publishing a Linked Data dataset, but does not have full control over its publishing infrastructure (i.e. they cannot set up redirects on their own web servers), *Hash URIs* ***MAY ***be used.</li>
 <li>If either are possible, i.e. if the Linked Data dataset is published by the custodian of the sub-domain and the custodian has full control over its publishing infrastructure, the size of dataset should be taken into consideration for deciding if *Slash URIs* or *Hash URIs* are used. Although there is no definitive threshold, if the dataset only includes up to a couple of hundred entities and is not expected to grow much further in the future, a *Hash URI *pattern ***MAY ***be used for its simplicity. For anything that is considerably bigger and/or is expected to grow significantly in the future, the use of *Slash URIs* is ***RECOMMENDED***.</li>
</ol>
![Decision tree for choosing publishing method](https://dl.dropboxusercontent.com/u/45222368/decision_tree.png)

<p align="center">Figure 1: Decision tree for choosing publishing method


***Hash URIs***
 URIs can contain a &ldquo;*fragment identifier&rdquo;*, an optional special part that is separated from the rest of the URI by a hash symbol (&ldquo;#&rdquo;). An example of a &ldquo;Hash URI&rdquo; is: **http://education.linked.data.gov.au/resource/schools#2060**. Hash URIs generally identify a secondary resource, subordinate to the main resource, which requires a different processing response. For example, in a web page or linear text document, the fragment identifier typically denotes a position within the page or document, so the browser usually scrolls to that point in the document. In RDF the fragment identifier can be used to point to a subordinate resource. When a *Hash URI* is dereferenced the HTTP protocol requires the fragment part to be stripped off before passing the URI to the server. This means that the server cannot interpret the part after the hash directly. Thus, the presence of a hash in RDF documents can be used to denote other *Non-Information Resources* within the same document without creating ambiguity, as this subordinate URI will never be served directly by the browser. For example, when the URI **http://education.linked.data.gov.au/resource/schools#2060 **denoting the school with the identifier 2060 (*Non-Information Resource*) is requested in a browser, the response will be **http://education.linked.data.gov.au/resource/schools**, which is the *Document URI* describing this and potentially other resources.

***Slash URIs***
 The second solution for a URI path structure to serve several distinct resource types is the use of so called &ldquo;Slash URIs&rdquo; for both, the *Document URI* and the *Identifier URI*, but to use a special HTTP status code, &ldquo;303 See Other&rdquo;, to give an indication that a requested *Identifier URI* is not a regular Web document, i.e. *Non-Information Resources*. This style was proposed in W3C's Technical Architecture Group in its httpRange-14 resolution document [8]. For example, if the *Slash URI* **http://education.linked.data.gov.au/id/school/2060** identifying a particular school (*Non-Information Resource*) is requested in a browser, the Web server is configured to answer requests to all these URIs with a &ldquo;303 See Other&rdquo; status code and a Location HTTP header that provides the URL of a document (*Information Resource*) that represents the resource, i.e. a redirect from **http://education.linked.data.gov.au/id/school/2060** to **http://education.linked.data.gov.au/doc/school/2060**.<br />

 The interested reader is referred to the W3C Note on &ldquo;Cool URIs for the Semantic Web&rdquo; [9] for a more in-depth discussion on the difference between the two.

The following table proposes guidelines for the URI patterns for *Slash URIs* and *Hash URIs*.****<br />

Requirement | Description | Conformance
--|--|--
<table border="1" cellspacing="0" cellpadding="0">
 <tr>
   <td width="135" valign="top" rowspan="2">***Identifier URI***</td>
    <td width="110" valign="top">**[no 21a]**</td>
    <td width="312" valign="top">*Slash URI pattern*<br />For *Slash URIs* the *Identifier URI* ***SHOULD ***contain the token 'id', a reference to its concept membership {type} and a local name {name} of the 'Thing'.<br />

**/id/{type}/{name} → /id/school/2060*** [Canberra Grammar]*
      </td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
  <tr>
    <td width="120" valign="top">**[no 21b]**</td>
    <td width="312" valign="top">*Hash URI pattern*<br />For *Hash URIs* the *Identifier URI* ***SHOULD*** contain the token 'resource' followed by an appropriate identifier that ***SHOULD ***be the same as the one used for the dataset, i.e. the {datasetid} and a fragment identifier {name} to name the 'Thing' locally.<br />

**/resource/{datasetid}#{name} → /resource/schools#2060*** [Canberra Grammar*</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
  <tr>
    <td width="135" valign="top" rowspan="2">***Document URI***</td>
    <td width="120" valign="top">**[no 22a]**</td>
    <td width="312" valign="top">*Slash URI pattern*  For *Slash URIs* the URI pattern for a *Document URI* ***SHOULD ***contain the token 'doc', a reference to its concept membership {type} and a local name {name} of the 'Thing'.<br />

        **doc/{type}/{name} → doc/school/2060  ***[Document about Canberra Grammar]*</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
  <tr>
    <td width="120" valign="top">**[no 22b]**</td>
    <td width="312" valign="top">*Hash URI pattern*  For *Hash URIs* the *Document URI* ***SHOULD ***contain the token 'resource' followed by an appropriate identifier that ***SHOULD ***be the same as the one used for the dataset, i.e. the {datasetid}. The *Document URI **MAY ***contain multiple *Identifier URIs* that can be distinguished from the document they are defined in by their fragment identifier.< br/>

**/resource/{datasetid}#{name} → /resource/schools#2060*** [Document that contains information about Canberra Grammar (among potentially other resources)]*</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
  <tr>
    <td width="135" valign="top" rowspan="3">***Ontology URI***</td>
    <td width="120" valign="top">**[no 23a]**</td>
    <td width="312" valign="top">The use of a *Hash URI *pattern *is **RECOMMENDED ***for *Ontology URIs* for its simplicity.</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
<tr>
    <td width="120" valign="top">**[no 23b]**</td>
    <td width="312" valign="top">Definition of concepts and relations ***SHOULD ***be denoted by the 'def' keyword followed by the ontology name {scheme}, followed by the concept or relationship name {concept}. If the {concept} name is omitted the whole ontology (vocabulary) should be returned.


        **/def/{scheme}#{concept} → /def/school#phaseOfEducation***  [The class definition of phaseOfEducation]*

If instances of classes, i.e. the actual entities (*non-information resources*) are modelled as part of the ontology (for example, code lists, finite sets of entities) in a *Hash URI pattern* the URIs used for the entities ***SHOULD ***still follow the *Identifier URI* pattern.</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
<tr>
    <td width="120" valign="top">**[no 23c]**</td>
    <td width="312" valign="top">If instances of classes, i.e. the actual entities (*non-information resources*) are modelled as part of the ontology (for example, code lists, finite sets of entities) the URIs used for the entities ***SHOULD ***still follow the *Identifier URI* pattern and not the *Ontology URI* pattern described here.</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
</table>

**Modularising URIs**  

 Sets of resources may be grouped in modules denoted by URIs that contain an arbitrary number of path segments to indicate a dataset hierarchy as described in Section 2. For each URI type, i.e. for *Identifier URIs*, *Document URIs* and *Ontology URIs *an (optional) [**{module}/]*** step can indicate the module the particular resource belongs to. If a dataset is part of a module all resources within this dataset ***MUST ***use the same path segment. For example, if no federal identifiers exist for schools, a state may introduce a dataset about schools within a module, i.e. /**dataset/act/schools** where **act** is the **{module}** and **schools** the **{datasetid}**. Schools identified within this module ***MUST ***then use the **act **module, e.g. **/act/id/school/2060** for the Canberra Grammar school (see also in the table below).

<table border="1" cellspacing="0" cellpadding="0">
 <tr>
    <td width="100" valign="top"><b>[no 24]</b></td>
    <td width="467" valign="top">If a dataset is part of a module all resources within this dataset ***MUST*** use the same path segment.</td>
    <td width="100" valign="top">***MUST***</td>
  </tr>
</table>


Classifications other than a state or the administering authority can form the basis of identifiers of modules. For example, primary and secondary education or public and independent schools could all be distinguished by a separate module, e.g. **/dataset/act/primary/public/schools** and **/dataset/act/primary/independent/catholic/schools**, **/dataset/act/primary/independent/anglican/schools** etc. where **act**, **primary**, **public**, **independent**, **catholic **and **anglican **are all module names, whereas **schools **denotes the datasets in each respective module. However, different type of schools can also be grouped in sub-datasets of a state-wide or even of a federal school dataset resulting, for example, in a path structure like **/dataset/schools/publicSchools** or **/dataset/schools/independentSchools** where **schools **is a federal dataset including all schools in Australia and **publicSchools** and **independentSchools **a sub-dataset including all independent schools in Australia. The decision on how to structure datasets will be use-case specific. However, individual resources ***MAY ***belong to more than one module, and therefore may be identified by more than one URI, each related to a different context.

The following table defines the guidelines for how to modularise different URI types.<br />


<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="135" valign="top" rowspan="2">***Identifier URI***</td>
    <td width="110" valign="top">**[no 25a]**</td>
    <td width="312" valign="top">*Slash URI pattern*  
        **/[{module}/]*/id/{type}/{name} → /act/id/school/2060***  [Canberra Grammar defined in the schools dataset of the act module]*</td>
    <td width="100" valign="top">***SHOULD***</td>
</tr>
  <tr>
    <td width="110" valign="top">**[no 25b]**</td>
    <td width="312" valign="top">*Hash URI pattern*<br />
        **/[{module}/]*/resource/{datasetid}#{name} → /act/resource/schools#2060***     [Canberra Grammar defined in the schools dataset of the act module]*</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>

  <tr>
    <td width="135" valign="top" rowspan="2">***Document URI***</td>
    <td width="110" valign="top">**[no 26a]**</td>
    <td width="312" valign="top">*Slash URI pattern*  
        **/[{module}/]*/doc/{type}/{name} → /act/doc/school/2060***  [Document about Canberra Grammar defined in the school dataset of the act module]*</td>
    <td width="100" valign="top">***SHOULD***</td>
</tr>
  <tr>
    <td width="110" valign="top">**[no 26b]**</td>
    <td width="312" valign="top">*Hash URI pattern*  
        **/[{module}/]*/resource/{datasetid} → /act/resource/schools***  [Document in the act module that contains among other resources information about Canberra Grammar]*</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
  <tr>
    <td width="135" valign="top" rowspan="2">***Ontology URI***</td>
    <td width="110" valign="top">**[no 27]**</td>
    <td width="312" valign="top">**/[{module}/]*/def/{scheme}#{concept} → /act/def/school#phaseOfEducation**  
        *[The class definition of phaseOfEducation in the context of the act module]*</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
</table>
## <a name="h.wfjxm50byvq" id="h.wfjxm50byvq"></a>5. Publishing URIs

A URI may identify a resource in a dataset without ever being resolved or dereferenced. However, following the Linked Data principles, a URI ***MUST ***be resolvable using the HTTP protocol as defined in rule no 1, making it essentially a URL. As URIs in this document are resolved in a sub-domain of linked.data.gov.au, the URI pattern chosen for a dataset has to be registered with linked.data.gov.au in order to be resolvable as a URL.

**Registering URIs with linked.data.gov.au**
 The URI for a dataset, in particular the chosen sub-domain, module and datasetid, have to be registered with linked.data.gov.au. Currently, this process requires one to send an email to <a href="mailto:agldwg-working@lists.csiro.au">agldwg-working@lists.csiro.au</a> (the core working group of the AGLDWG mailing list), but a Web-enabled management tool is considered for the future.

Depending on the publishing method, different URI path structures have to be registered.

**Hash URIs**
 For Hash URIs only the *Dataset URI* has to be registered:<br />
 **{domain}**.linked.data.gov.au/dataset**[/{module}]***/**{datasetid}**

The physical location of the document results from this Dataset URI, i.e.:<br />
 **{domain}**.linked.data.gov.au/**[/{module}]***/resource/**{datasetid}**

**Slash URIs**
 Since datasets published in a *Slash URI** ***pattern will typically not physically reside on linked.data.gov.au servers, the physical location of the dataset on an agency server has to be registered with linked.data.gov.au. For *Slash URIs* two scenarios have to be distinguished, (1) a custodian of the linked.data.gov.au sub-domain in question is publishing a new Linked Data dataset, or (2) an agency that is NOT the custodian of a linked.data.gov.au sub-domain is requesting to publish a new Linked Data dataset under this sub-domain that is managed by someone else.

**Custodian of the linked.data.gov.au sub-domain:**  
 The custodian of a linked.data.gov.au sub-domain only has to register new modules, i.e. the following URIs have to be registered:

**{domain}**.linked.data.gov.au/dataset**[/{module}]***/<br />
 **{domain}**.linked.data.gov.au/**[/{module}/]***/id/<br />
 **{domain}**.linked.data.gov.au/**[/{module}/]***/doc/<br />
 **{domain}**.linked.data.gov.au/**[/{module}/]***/def/

For each of these URIs the storage location, i.e. the IP address or the hostname, of the data that will be served by these URIs has to be registered with linked.data.gov.au.

Datasets that are published under existing modules or in the top-level URI path, i.e. directly under **{domain}**.linked.data.gov.au/id/, **{domain}**.linked.data.gov.au/doc/ or **{domain}**.linked.data.gov.au/def/ do not need to be registered.

**Agencies that are NOT the custodian of the respective linked.data.gov.au sub-domain:**
 Agencies that are not the custodian of the sub-domain can only request a new module within the sub-domain in question, i.e. they cannot publish datasets under the top-level URI path **{domain}**.linked.data.gov.au/id/, **{domain}**.linked.data.gov.au/doc/ or **{domain}**.linked.data.gov.au/def/. The Dataset URI has to be registered as above:

**{domain}**.linked.data.gov.au/dataset**[/{module}]***/**{datasetid}**<br />
 **{domain}**.linked.data.gov.au/**[/{module}/]***/id/<br />
 **{domain}**.linked.data.gov.au/**[/{module}/]***/doc/<br />
 **{domain}**.linked.data.gov.au/**[/{module}/]***/def/

For each of these URIs the storage location, i.e. the IP address or the hostname, of the data that will be served by these URIs has to be registered with linked.data.gov.au.

If the module name has already been assigned, alternative URI paths will be proposed to the requester.

**Resolving URIs**
 *Content negotiation* is a mechanism defined for HTTP that makes it possible to serve different versions of a resource representation at the same URI. Different client applications have different preferences on the data format and language which can be indicated in the HTTP header of the request. For example, a browser usually requests HTML, localized with a natural language such as English or Chinese, while Semantic Web software usually requests RDF. The server then selects the best match, perhaps from its file system, or by generating the desired content on demand, and sends it back to the client.<br />
 For dereferencing HTTP URIs there are standard patterns [8] that distinguish between the different resource types. The following paragraphs introduce guidelines for the resolving of the different URI types in the linked.data.gov.au domain.<br />


 **Resolving Identifier URIs**
 To conform to the Linked data principles [1], a URI for a real-world 'Thing' must resolve to a document that contains information about that thing. This principle poses different requirements on the architecture, depending on if a *Hash URI Pattern* or *Slash URI Pattern* is used to identify the resource.

<table border="1" cellspacing="0" cellpadding="0">
 <tr>
  <td width="135" valign="top" rowspan="2">***Resolving Identifier URIs***</td>
  <td width="110" valign="top">**[no 28a]**</td>
  <td width="312" valign="top">*Slash URI pattern* For *Slash URIs* a &ldquo;303 See Other&rdquo; status code ***SHOULD*** be issued for requests for** /id/{type}/{id} **with a response redirecting to ** /doc/{type}/{id} **. This indicates to the user that the requested resource is a *Non-Information Resource*, while redirecting the user to the document for the 'Thing', i.e. the *Information Resource*. Content-negotiation can be used to decide on the specific representation that is returned to the user for the document.</td>
  <td width="100" valign="top">***SHOULD***</td>
</tr>
 <tr>
  <td width="110" valign="top">**[no 28b]**</td>
  <td width="312" valign="top">*Hash URI pattern* For *Hash Identifier URIs* the storage location for **/resource/{datasetid}#{id}** ***SHOULD*** be **/resource/{datasetid}**. As the fragment part in the Hash URI **/resource/{datasetid}#{id}** is stripped off by the HTTP protocol, this is the default storage location and there is no need to setup a redirect.</td>
  <td width="100" valign="top">***SHOULD***
</tr>
</table>

Rule No 28b makes the *Hash Identifier URI *pattern very easy to implement while largely maintaining Linked Data principles. In this setting, the ***document storage location*** is also the *Document URI*, whereas any *Identifier URI* within this document uses the storage location plus a fragment identifier for identifying its *Non-Information Resource*. For example, if the Identifier URI is **http://education.linked.data.gov.au/resource/schools#2060**, the **#2060** is stripped off and the document is returned, using the *Document URI* **http://education.linked.data.gov.au/resource/schools**.<br />

**Resolving Document URIs**
 A *Document URI* will resolve to  the most appropriate representation as defined by the content-type(s) in the  'Accept' header of an HTTP request. The guidelines are similar for *Hash URIs* and *Slash URIs*.<br />

<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="100" valign="top"><b>[no 29]</b></td>
    <td width="467" valign="top">If the RDF and HTML representations of the resource do not differ in  terms of their information content, the use of the file extension is ***RECOMMENDED ***to distinguish the different representations, e.g. .html, .rdf, .owl.</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 30]</b></td>
    <td width="467" valign="top">If file extensions are used to distinguish between different representations, the type ***MAY NOT*** be explicitly stated in any other part of the URI, e.g.** /doc/school/2060.rdf** rather than** /doc/rdf/school/2060.rdf**.</td>
    <td width="100" valign="top">***SHOULD NOT***</td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 31]</b></td>
    <td width="467" valign="top">If the RDF and HTML representations of the resource differ  substantially, i.e. they are not two versions of the same document but different documents altogether, a &ldquo;303  See Other&rdquo; redirect in combination with a content-negotiation ***SHOULD ***be set up that points to two separate *Document URIs*. In this case the use of a token indicating the file type in the *Document URI* is ***RECOMMENDED***, e.g. ** /doc/school/2060 ** redirects to ** /doc/rdf/school/2060.rdf **for the RDF representation and to** /doc/html/school/2060.html **for the HTML representation.</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 32]</b></td>
    <td width="467" valign="top">To denote different versions of documents, a 'date' token ***SHOULD ***be used for the *Document URIs* to indicate that the information is valid on, or from, a particular date. For example, **/doc/html/2012/school/2060** can be used as a *Document URI* for the school dataset that is current as of 2012.<br /></td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
</table>


**Resolving *Ontology URIs***  
  *Ontology URIs* are a special kind of *Document URI* where the document type is always RDF or OWL. Thus, for ontologies that only contain schema-level definitions (i.e. classes/properties) there is no need for content negotiation or redirects. For example, for classes and properties in a *Hash URI *ontology with the pattern **/def/{scheme}#{concept}**, the hash is automatically stripped off resulting in **/def/{scheme}**, the *Document URI*.



If instances are included in the same file as the classes and properties, the URI scheme of these instances should follow the *Identifier URI* pattern as described in Section 4, resulting in the following guideline.

<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="100" valign="top"><b>[no 33]</b></td>
    <td width="467" valign="top">For ontologies using a *Hash URI *scheme that include both, schema-level (i.e. classes/properties) and instance-level information, the file should be stored in two locations,** /def/{scheme} **and **/resource/{type}** in order to allow proper resolving of *Document URIs* and *Identifier URIs* defined in the ontology.</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
</table>

## <a name="h.h7mypgxdds0" id="h.h7mypgxdds0"></a>6. URI naming conventions


 In the recently published RDF1.1 W3C recommendation [12] URIs were replaced in favour of their internationalized version, the so called Internationalized Resource identifier (IRI) that allows to contain characters from the Universal Character Set (Unicode/ISO 10646), including Chinese or Japanese kanji, Korean, Cyrillic characters, etc. However, considering that government documents in Australia are mostly published in the English language the use of URIs for naming resources in Linked Data datasets is ***RECOMMENDED*** as defined by rule no 1.

**Character Sets used in URI**

<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="100" valign="top"><b>[no 34]</b></td>
    <td width="467" valign="top">For *Linked Data dataset URIs*, ASCII characters ***SHOULD ***be used, i.e. the numbers from 0-9, the uppercase and lowercase English letters from A to Z, and some special characters.</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 35]</b></td>
    <td width="467" valign="top">Accented letters, diacritical and special language characters ***SHOULD NOT***be used in URIs.</td>
    <td width="100" valign="top">***SHOULD NOT***</td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 36]</b></td>
    <td width="467" valign="top">Spaces in URIs are ***NOT RECOMMENDED***.</td>
    <td width="100" valign="top">***NOT RECOMMENDED***</td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 37]</b></td>
    <td width="467" valign="top">URIs are case-sensitive apart from the domain name. However, using upper/lower case as a differentiating factor in URIs is ***NOT RECOMMENDED***.</td>
    <td width="100" valign="top">***NOT RECOMMENDED***</td>
  </tr>
</table>

**Naming resources**
<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="100" valign="top"><b>[no 38]</b></td>
    <td width="467" valign="top">English ***SHOULD ***be exclusively used for naming resources, unless the  real-world thing is commonly known in English by its native name (e.g. aboriginal name).</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
</table>

<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="135" valign="top" rowspan="2">***Dataset URI***</td>
    <td width="110" valign="top"><b>[no 39a]</b></td>
    <td width="312" valign="top">Lower case ***MUST*** be used for the entire URI path up to the {datasetid} part. No particular recommendations are made for the {datasetid} part, which can use any casing as deemed appropriate for the domain.</td>
    <td width="100" valign="top">***MUST***</td>
  </tr>
  <tr>
    <td width="110" valign="top"><b>[no 39b]</b></td>
    <td width="312" valign="top">Datasets denote a collection of real-world 'Things' and thus ***SHOULD ***use the plural for the {datasetid}, e.g. **/dataset/schools**.</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
  <tr>
    <td width="135" valign="top" rowspan="6">***Identifier URI***</td>
    <td width="110" valign="top"><b>[no 40a]</b></td>
    <td width="312" valign="top">Existing identifiers ***MUST ***always be reused    when applicable (even if they are not compliant with the rules on the use of special characters, whitespaces, ... as stated above).</td>
    <td width="100" valign="top">***MUST***</td>
  </tr>
  <tr>
    <td width="110" valign="top"><b>[no 40b]</b></td>
    <td width="312" valign="top">Lower case ***MUST*** be used for the entire URI path up to the {name} part. No particular recommendations are made for the {name} part, which can use any casing as deemed appropriate for the domain.</td>
    <td width="100" valign="top">***MUST***</td>
  </tr>
  <tr>
    <td width="110" valign="top"><b>[no 40c]</b></td>
    <td width="312" valign="top">A singular name ***SHOULD ***always be used for naming one particular physical or abstract real-world thing, except if the word to be used for the thing is only available as plural (e.g. series, species).</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
  <tr>
    <td width="110" valign="top"><b>[no 40d]</b></td>
    <td width="312" valign="top">The plural ***SHOULD ***always be used for naming a set/list of real-world 'Things', e.g. **/id/school/independentSchools** to identify a list of all independent schools in a dataset.</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
  <tr>
    <td width="110" valign="top"><b>[no 40e]</b></td>
    <td width="312" valign="top">Acronyms ***SHOULD ***all be in upper cases or    all in lower cases.</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>
  <tr>
    <td width="110" valign="top"><b>[no 40f]</b></td>
    <td width="312" valign="top">A de-identified scheme ***SHOULD ***be used for    persons, i.e. do not include the name of the person in the URI.</td>
    <td width="100" valign="top">***SHOULD***</td>
  </tr>

  <tr>
    <td width="135" valign="top">***Ontology URI***</td>
    <td width="522" valign="top" colspan="3">For class names and property names in *Ontology URIs* no formatting guidelines are made. Common practise in ontology engineering is to use either lower or upper camel case, e.g. **/def/phaseOfEducation** or **/def/PhaseOfEducation, **or dashes/underscores as word separators, e.g. **/def/phase_of_education**</td>
  </tr>
</table>
<h1><a name="h.depmzbrccojw" id="h.depmzbrccojw"></a>7. HOW-TO publish a Linked Data dataset on linked.data.gov.au</h1>

In this section a walk-through example is presented on how to publish a Linked Data dataset on linked.data.gov.au. The instructions presented are based on the example school dataset that was used throughout the document. For the example, let us assume a state government agency governing the educational portfolio in the Australian Capital Territory is to publish the &ldquo;Locations of all ACT schools&rdquo; in a Linked Data fashion. Currently, a CSV version of this dataset is available at <a href="http://www.data.gov.au/dataset/location-of-act-schools">http://www.data.gov.au/dataset/location-of-act-schools</a> published by the Department of Education and Training (ACT).
## <a name="h.kdopiiao7s23" id="h.kdopiiao7s23"></a>Choose Sub-Domain</h2>

First, an appropriate sub-domain for the dataset has to be chosen. For the &ldquo;Location of ACT schools&rdquo; the **&ldquo;education&rdquo; **sub-domain or **&ldquo;governance&rdquo; **sub-domain seem appropriate, depending on the level of detail in the dataset and its relation to other datasets. Let us assume, the **&ldquo;education&rdquo; **sub-domain is chosen for the example ACT school dataset.
## <a name="h.de8w7gz2pkor" id="h.de8w7gz2pkor"></a>Choose a path structure (module)</h2>

Next, it has to be decided if the dataset is appropriate to be included in the top-level of the respective sub-domain, e.g. **education.linked.data.gov.au/dataset/** or if it is better placed within a module, i.e. an additional path structure that is added to the URI to denote the datasets domain of discourse. The sub-levels of the AGIFT classification of functions in the Australian Government can be consulted to make a decision on the appropriate module. If the dataset is a state dataset, the appropriate state identifier should be used in the module name, i.e. **education.linked.data.gov.au/dataset/act/** in the ACT school example.
## <a name="h.2jjsxvokqhq1" id="h.2jjsxvokqhq1"></a>Decide on publishing method</h2>

Next, the publishing agent has to decide on the publishing method to use. The decision tree proposed in Figure 1 in Section 4 can be consulted to help in deciding whether to use *Hash URIs* or *Slash URIs*. In the case of the ACT school dataset, *Hash URIs **MAY ***be used regardless whether the published is the custodian of the education.linked.data.gov.au sub-domain, as the dataset includes only 100 entities and is not expected to grow significantly in the future. For the remainder of this guide, let us assume *Hash URIs* are used.
## <a name="h.wrrkhndzriqm" id="h.wrrkhndzriqm"></a>Register URI path with linked.data.gov.au</h2>

Once the sub-domain and module have been chosen, a name (datasetid) for the dataset has to be chosen and the URI path has to be registered with linked.data.gov.au. As outlined above, an email has to be sent to <a href="mailto:agldwg-all@lists.csiro.au">agldwg-all@lists.csiro.au</a> to requests a URI, in our example:

**http://education.linked.data.gov.au/dataset/act/schools**

If the URI is already assigned, an alternative URI will be proposed to the requester. Let us assume the URI is successfully registered for the remainder of this example.

## <a name="h.hkdkg9p0mutu" id="h.hkdkg9p0mutu"></a>Develop the dataset</h2>

Once the URI path is registered, the Linked Data dataset can be developed. As a Hash URI pattern was chosen, entities within this dataset will be identified with URIs such as: **http://education.linked.data.gov.au/act/resource/schools#2060**, denoting Canberra Grammar school.

## <a name="h.kwb19j7bistv" id="h.kwb19j7bistv"></a>Publish the dataset on data.gov.au</h2>

When finished the Linked Data dataset is uploaded to the linked.data.gov.au servers through the CKAN system. The system will automatically create the metadata that will be accessible at the Dataset URI, i.e. at **http://education.linked.data.gov.au/dataset/act/schools**. The metadata will also include a reference to the storage location, which will be **http://education.linked.data.gov.au/act/resource/schools.rdf**.




 <p><a href="#_ftnref1" name="_ftn1" title="" id="_ftn1"> </a> See http://agift.naa.gov.au/
