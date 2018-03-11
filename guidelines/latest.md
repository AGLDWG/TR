<body>

<p>Australian Government Linked Data Working Group</p>
<h1><a name="h.mzkw4ei1q3v2" id="h.mzkw4ei1q3v2"></a><strong>URI Guidelines for publishing Linked Data datasets on data.gov.au v0.3</strong></h1>
<p><strong>(March 12 2018)</strong></p>

<h2>Table of Contents</h2>
<a href="#h.hg1sj27y6ufa">Conformance</a><br />
<a href="#h.8x82ev9hlve4">1. Introduction</a><br />
<a href="#h.evgc2ceabc0u">2. Linked Data dataset URIs</a><br />
<a href="#h.yhbu9svf0ixu">3. Domain structure</a><br />
<a href="#h.blxw9q9b2rlf">4. URI patterns</a><br />
<a href="#h.wfjxm50byvq">5. Publishing URIs</a><br />
<a href="#h.h7mypgxdds0">6. URI naming conventions</a><br />
<a href="#h.depmzbrccojw">7. HOW-TO publish a Linked Data dataset on data.gov.au</a><br />
<a href="#h.1vlcemw9iv0h">References</a>

<h2><a name="h.hg1sj27y6ufa" id="h.hg1sj27y6ufa"></a>Conformance </h2>

<h4><a name="h.l9zrfrgt66h5" id="h.l9zrfrgt66h5"></a>The key words <em>MUST</em>, <em>MUST NOT</em>, <em>REQUIRED</em>, <em>SHOULD</em>, <em>SHOULD NOT</em>, <em>RECOMMENDED</em>, <em>MAY</em>, and <em>OPTIONAL </em>in this document are to be  interpreted as described in [11]. </h4>

<h2><a name="h.8x82ev9hlve4" id="h.8x82ev9hlve4"></a>1.   Introduction </h2>

<p>Uniform Resource Identifiers (URI) are a single global identification  system used on the World Wide Web, similar to telephone numbers in a public  switched telephone network. URIs are a key technology to support Linked Data by  offering a generic mechanism to identify entities (&lsquo;Things&rsquo;) or concepts in the  world. Government departments and agencies assign identifiers to all entities  ('Things') they are responsible for - e.g., hospitals, schools, roads,  equipment, etc. These identifiers are then used when referring to or making  statements about particular entities. For example, when referring to a road  closure, the identifier (e.g. M5) will be used to inform the public. In order  to publish data in a Linked Data fashion, government and governmental agencies  need to define these resource identifiers using URIs. Since public sector  information (PSI) is intended to be re-used by diverse applications, it is  important that these resource identifier URIs remain stable.<br /><br />This document provides a set of general guidelines aimed at helping  government stakeholders to define and manage URIs for &lsquo;Linked Data datasets&rsquo; and the resources described within. The URI guidelines in this document are building upon the four Linked Data principles postulated by Sir Tim Berners-Lee [1]. These principles are:<br /><br /><strong>Use HTTP URIs</strong> <br />Addressing two of the four principles, <em>&lsquo;use URIs&rsquo;</em> and <em>&lsquo;use HTTP URIs&rsquo;, </em>governments and their agencies publishing Linked Data <strong><em>MUST </em></strong>provide  HTTP URIs as identifiers for resources, in order to support reuse and data  integration/linking on the Web in a Linked Data fashion. HTTP URIs enable URIs  to be &quot;looked-up&quot; or &quot;dereferenced&quot;, which in turn provides  access, via a Web browser, to a representation of the resource identified by these URIs.</p>
<p><br /><strong>Provide a  machine-readable representation of the resource identified by the URI</strong><br />In order to enable HTTP URIs to be &quot;dereferenceable&quot;, data publishers have to set up the necessary  infrastructure (e.g. HTTP servers) to serve representations or descriptions of  the resources (e.g. a human-readable HTML representation or a machine-readable  RDF/XML representation). For it to be considered Linked data, a publisher <strong><em>MUST </em></strong>publish  the data using RDF (i.e., to define explicitly the meaning of this data) and <strong><em>MUST </em></strong>publish  at least one machine-readable representation (e.g. RDF/XML, JSON-LD, Turtle)  via the HTTP URI identifying the resource.<br /></p>

<table border="1" cellspacing="0" cellpadding="0">
  <tr>
<td valign="top" width="80"><b>[no 1]</b></td>
    <td width="573" valign="top">Use HTTP URIs so that the Linked Data dataset URI can be resolved.</td>
    <td width="100" valign="top"><strong><em>MUST</em></strong></td>
  </tr>
  <tr>
<td valign="top" width="80"><b>[no 2]</b></td>
    <td width="573" valign="top">Provide at least one machine-readable representation in RDF at the Linked Data dataset URI.</td>
    <td width="100" valign="top"><strong><em>MUST</em></strong></td>
  </tr>
</table>

<p>Beyond these principles the document defines guidance on:</p>
<ol>
  <li>Linked Data dataset URIs,</li>
  <li>Domain structures,</li>
  <li>URI patterns,</li>
  <li>Publishing URIs, and on</li>
  <li>URI naming conventions.</li>
</ol>
<h2><a name="h.evgc2ceabc0u" id="h.evgc2ceabc0u"></a>2. Linked Data dataset URIs </h2>
<p>For the purpose of this document a <em>Linked  Dataset</em> published within the data.gov.au domain is defined as a collection  of data, each with supporting metadata, published and maintained under the  data.gov.au domain, available as RDF, and accessible through dereferenceable  HTTP Universal Resource Identifiers (URIs).<br />HTTP URIs, a component of the World Wide Web, provides a means of uniquely identifying a &lsquo;Thing&rsquo; (or &lsquo;Resource&rsquo;) in this case a <em>Linked Data dataset</em>. <em>Linked Data datasets</em> provide the opportunity to share common meaning and  common identifiers across the public sector, and to provide comprehensive and  reliable identifiers for a collection of &lsquo;Things&rsquo; such as the hospitals,  schools or roads in a region, climate data for a specific year etc.<br /><br />A Linked Data dataset consists of:</p>

<ol>
  <li>the  URI to identify the set</li>
  <li>metadata  to describe its quality characteristics</li>
  <li>a  URI that references a list of resources (<em>Identifier  URIs</em> and <em>Document URIs</em>) defined  in the Linked Data dataset</li>
  <li>references  to <em>Ontology URIs</em> which define the  concept and relationships used within the Linked Data dataset</li>
</ol>

<p><br />For the <em>Linked Data dataset URI</em> the  following pattern is proposed. The pattern notation used in this document is based on the  &ldquo;URI Template&rdquo; specification defined in RFC6570 [7]. In addition square brackets &lsquo;[&lsquo; and &lsquo;]&rsquo; are used to introduce optional components and a star, i.e. &lsquo;*&rsquo; following such a bracket component allows arbitrary repetition of the group  (zero or more times).<br /></p>

<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="80" valign="top"><b>[no 3]</b></td>
<td width="150" valign="top"><strong><em>Dataset URI</em></strong></td>
    <td width="398" valign="top">The <em>Dataset URI</em> <strong><em>MUST </em></strong>contain the string &lsquo;dataset&rsquo;, and an appropriate identifier <strong>{datasetid}</strong> describing the nature of the &lsquo;Dataset&lsquo;.<br /><br /><i>URI Pattern</i><br /><strong>/dataset/{datasetid}</strong><br /><br /><em>Example</em> <br /><strong>/dataset/schools</strong></td>
<td width="100" valign="top"><b><i>MUST</i></b></td></tr>
</table>

<p>Datasets are often hierarchically structured, i.e. there exists a superset that consists of multiple parts, for example, a dataset for schools  that consist of a dataset for primary schools and secondary schools. Multiple  hierarchies may co-exist, for example a dataset for schools may also consist of  datasets for public and independent schools. For modelling this hierarchy we  propose the use of path segments in the <em>URI</em>:</p>

<table border="1" cellspacing="0" cellpadding="0">
<tr>
    <td width="80" valign="top"><b>[no 4]</b></td>
     <td width="150" valign="top"><strong><em>Modularised Dataset URI</em></strong></td>
<td width="398" valign="top">Optionally, it can also be hierarchically structured with an arbitrary number of path segments that are denoted with the identifier <strong>{module} </strong>below.<br /><br /><i>URI Pattern</i><br /><strong>/dataset[/{module}]*/{datasetid}</strong><br /><br /><em>Example</em> <br /><strong>/dataset/act/schools</strong></td>
<td width="100" valign="top"><b><i>SHOULD</i></b></td>
</tr>
</table>

<p><strong>Metadata requirements for Linked Data datasets</strong><br />For expressing the <em>metadata to  describe the quality characteristics</em> of a dataset the use of DCAT (Data Catalog Vocabulary) [5] is <strong><em>RECOMMENDED</em></strong>, a vocabulary that provides terms and patterns for describing RDF datasets. Consequently, a <em>Linked Data dataset URI</em> <strong><em>SHOULD </em></strong>be a member of the class dcat:Dataset.</p>

<p>For modularised datasets, each module <strong><em>SHOULD </em></strong>be a member of the dcat:Catalog class. All datasets within a module <strong><em>SHOULD</em></strong> be referenced with a dcat:dataset property from the <em>URI</em> that describes the module (i.e. a member of the dcat:Catalog class). This <em>Catalogue URI</em> <strong><em>SHOULD</em></strong> be dereferenceable at the top-level path segment of the module. For example, for the modularised<b> /dataset/act/schools </b>dataset, the dcat:Catalog <em>URI</em> is<b> /dataset/act </b>that references the schools dataset and all other datasets within this module with the dcat:dataset property.<br /> Summarising, the specific guidelines for adding metadata to Linked Data datasets are:</p>

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

<p><br/><strong>Dataset ROOT</strong><br />The &ldquo;dataset root&rdquo; URI containing the string &lsquo;dataset&rsquo; <strong><em>SHOULD</strong></em> reference a list of all Linked Data datasets in the domain.</p>

<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="80" valign="top"><b>[no 9]</b></td>
    <td width="478" valign="top">The <em>Dataset ROOT URI</em> (i.e. http://{domain}.data.gov.au/dataset) results in a list of all <em>Dataset URIs</em> in its {domain}.</td>
<td width="100" valign="top"><b><i>SHOULD</i></b></td></tr>
</table>

<p><br /><strong>General design principles</strong> <br />The following table summarises the guidelines proposed in the previous paragraphs and introduces further general design principles for publishing Linked Data datasets that are derived from existing good practices [1,2,3,4] and revised to meet some specific requirements for the Australian public sector:</p>

<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="100" valign="top"><b>[no 10]</b></td>
    <td width="467" valign="top">Provide a human-readable representation in HTML at the <em>Dataset URI</em>.</td>
    <td width="100" valign="top"><strong><em>MUST</em></strong></td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 11]</b></td>
    <td width="467" valign="top">If multiple representations exist, provide a means of discovering specific URIs for each of the available representations.</td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 12]</b></td>
    <td width="467" valign="top">The license for inspection or use of the Linked Data dataset shall be provided using a common vocabulary.</td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 13]</b></td>
    <td width="467" valign="top">The metadata for a Linked Data dataset should be provided using a common vocabulary and contain the expected longevity and maintenance plans for the <em>Dataset URI</em>.</td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 14]</b></td>
    <td width="467" valign="top">The current technical implementation of a data publication system should not be visible in or otherwise affect the URI for a Linked Data dataset.</td>
    <td width="100" valign="top"><strong><em>SHOULD NOT</em></strong></td>
  </tr>
</table>

<h2><a name="h.yhbu9svf0ixu" id="h.yhbu9svf0ixu"></a>3. Domain structure </h2>

<p>Data.gov.au currently supports 25 sub-domain names to be used for Linked Data datasets that are defined according to the top level of the Australian Governments&rsquo; Interactive Functions Thesaurus (AGIFT)<a href="#_ftn1" name="_ftnref1" title="" id="_ftnref1"> </a>. The supported sub-domain names are:</p>

<table border="0" cellspacing="0" cellpadding="0">
<tr><td>business.data.gov.au</td><td>(BUSINESS SUPPORT AND REGULATION)</td></tr><tr><td>communications.data.gov.au</td><td>(COMMUNICATIONS)</td></tr><tr><td>communityservices.data.gov.au</td><td>(COMMUNITY SERVICES)</td></tr>
<tr><td>culture.data.gov.au</td><td>(CULTURAL AFFAIRS)</td></tr>
<tr><td>defence.data.gov.au</td><td>(DEFENCE)</td></tr>
<tr><td>education.data.gov.au</td><td>(EDUCATION AND TRAINING)</td></tr>
<tr><td>employment.data.gov.au</td><td>(EMPLOYMENT)</td></tr>
<tr><td>environment.data.gov.au</td><td>(ENVIRONMENT)</td></tr>
<tr><td>finance.data.gov.au</td><td>(FINANCE MANAGEMENT)</td></tr>
<tr><td>internationalrelations.data.gov.au</td><td>(INTERNATIONAL RELATIONS)</td></tr>
<tr><td>governance.data.gov.au</td><td>(GOVERNANCE)</td></tr>
<tr><td>health.data.gov.au</td><td>(HEALTH CARE)</td></tr>
<tr><td>immigration.data.gov.au</td><td>(IMMIGRATION)</td></tr>
<tr><td>indigenous.data.gov.au</td><td>(INDIGENOUS AFFAIRS)</td></tr>
<tr><td>infrastructure.data.gov.au</td><td>(CIVIC INFRASTRUCTURE)</td></tr>
<tr><td>justice.data.gov.au</td><td>(JUSTICE ADMINISTRATION)</td></tr>
<tr><td>maritime.data.gov.au</td><td>(MARITIME SERVICES)</td></tr>
<tr><td>primaryindustry.data.gov.au</td><td>(PRIMARY INDUSTRIES)</td></tr>
<tr><td>recreation.data.gov.au</td><td>(SPORT AND RECREATION)</td></tr>
<tr><td>resources.data.gov.au</td><td>(NATURAL RESOURCES)</td></tr>
<tr><td>science.data.gov.au</td><td>(SCIENCE)</td></tr>
<tr><td>security.data.gov.au</td><td>(SECURITY)</td></tr>
<tr><td>tourism.data.gov.au</td><td>(TOURISM)</td></tr>
<tr><td>trade.data.gov.au</td><td>(TRADE)</td></tr>
<tr><td>transport.data.gov.au</td><td>(TRANSPORT)</td></tr>
</table>

<p>The publisher of a Linked Data dataset can chose the sub-domain they feel is appropriate for the entities contained within the dataset. If it is unclear  which sub-domain is appropriate for a particular Linked Data dataset the <a href="http://naa.gov.au/agift/search.htm">National Archives search tool</a> can be used to help identify the government function matching most closely with the domain of the entities  contained in the Linked Data dataset.</p>

<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="100" valign="top"><b>[no 15]</b></td>
    <td width="467" valign="top">All Linked Data datasets published under data.gov.au use a sub-domain of data.gov.au to identify all entities within the Linked Data dataset.</td>
    <td width="100" valign="top"><strong><em>MUST</em></strong></td>
  </tr>
</table>

<p>Agencies can request to be the custodian for one of the 25 sub-domains. It is expected that custodians have a robust, secure and highly available hosting environment in place. This is particularly important when the custodian  of a sub-domain is also administering redirects for modules under this  sub-domain and that are provisioned by other agencies. Where a number of  agencies supply content for a single sub-domain (e.g. environment.data.gov.au is likely to be used by multiple agencies publishing Linked Data datasets) it may be worth exploring the use of an independent proxy service, which is highly  available, and with the single purpose of redirecting traffic to the  appropriate infrastructure hosting the dataset.</p>

<p>For choosing the sub-domain name for a Linked Data dataset the following principles have been defined which are based on existing good practice and  revised to meet the requirements for datasets in the Australian public sector:<br /></p>

<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="100" valign="top"><b>[no 16]</b></td>
    <td width="467" valign="top"><strong>data.gov.au</strong> is the base domain for Linked Data datasets that are promoted for re-use.</td>
    <td width="100" valign="top"><strong><em>MUST</em></strong></td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 17]</b></td>
    <td width="467" valign="top">The government function (e.g. &lsquo;education&rsquo;,    &lsquo;environment&rsquo;, &lsquo;health&rsquo;, &lsquo;defence&rsquo;, &lsquo;location&rsquo;) according to the top level of the Australian Governments' Interactive Functions Thesaurus (AGIFT) is included in the domain name of the URI.</td>
    <td width="100" valign="top"><strong><em>MUST</em></strong></td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 18]</b></td>
    <td width="467" valign="top">The name of the department or agency currently responsible for a dataset <strong><em>SHALL NOT</em></strong> be used in persistent URIs (unless it happens to match the function in AGIFT).</td>
    <td width="100" valign="top"><strong><em>MUST NOT</em></strong></td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 19]</b></td>
    <td width="467" valign="top">The sub-domain supports a direct response (note: this may be implemented as a redirect to department/agency servers from the sub-domain).</td>
    <td width="100" valign="top"><strong><em>MUST</em></strong></td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 20]</b></td>
    <td width="467" valign="top">The sub-domain are maintained in perpetuity.</td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
</table>

<h2><a name="h.blxw9q9b2rlf" id="h.blxw9q9b2rlf"></a>4. URI patterns</h2>
<p>A URI can be used to denote a resource, which is either an Information Resource, or a <em>Non-Information Resource</em>. For example, a document, which describes a person including their name, address etc., is an <em>Information Resource</em>. The actual person (in the real-world) is a <em>Non-Information Resource</em>. Since <em>Information Resources</em> (documents, images, datasets etc.) can be served directly, the server returns a  representation of the current state of the resource and sends it back to the  client, with the HTTP response code 200 OK. <em>Non-Information Resources</em> cannot be dereferenced directly, so the server responds by pointing the client to another URI, which is for an information resource which describes the original  (non-information) resource, and sets the HTTP response code to 303 See Other.</p>
<p>The following table describes the resource types for which a URI pattern guideline is defined. Section 5 then defines how the server implementing the  pattern should resolve these URIs.</p>

<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="212" valign="top"><strong>Type of Resource</strong></td>
    <td width="155" valign="top"><strong>Type of URI</strong></td>
    <td width="367" valign="top"><strong>Definition</strong></td>
  </tr>
  <tr>
    <td width="212" valign="top">A real-world &lsquo;Thing&rsquo;<br />
        <strong><em>(Non-Information Resource)</em></strong></td>
    <td width="155" valign="top"><strong><em>Identifier URI</em></strong></td>
    <td width="367" valign="top">Identifies some physical or abstract real-world thing that may be referred to in statements.<br />
        <strong><em>Example of physical real-world &lsquo;Things&rsquo;:</em></strong> a person, a school, a road, a museum etc.<br />
        <strong><em>Example of abstract real-world &lsquo;Things&rsquo;:</em></strong> <br />
        a government sector, an ethnic group etc.</td>
  </tr>
  <tr>
    <td width="212" valign="top">A regular document<br />
        <strong><em>(Information Resource)</em></strong></td>
    <td width="155" valign="top"><strong><em>Document URI</em></strong></td>
    <td width="367" valign="top">Identifies a document that may be referred to in statements. The <em>Document URI</em> should resolve directly to a document on the Web.</td>
  </tr>
  <tr>
    <td width="212" valign="top">Definitions of characteristics of a Real-world &lsquo;Thing&rsquo;<br />
        <strong><em>(Information Resource)</em></strong></td>
    <td width="155" valign="top"><strong><em>Ontology URI</em></strong></td>
    <td width="367" valign="top">Definition of concepts and relations contained within ontologies that define characteristics of a real-world &lsquo;Thing&rsquo;.<br />
        <strong>Example of a definition of a real-world &lsquo;Thing&rsquo;:</strong> a &lsquo;Person&rsquo; class with properties such as a &lsquo;firstname&rsquo;, &lsquo;lastname&rsquo;, &lsquo;social security number&rsquo;, &lsquo;address&rsquo;, etc.<br />
        &lsquo;Ontology URIs&rsquo; can be looked up and return a definition or a set of definitions about a real-world thing, e.g. the &lsquo;Person&rsquo; class URI will return the set of properties listed above.</td>
  </tr>
</table>

<p>In the following section guidelines for the URI patterns for the  different resource types are proposed.</p>

<p>For <em>Non-Information Resources</em>, i.e. <em>Identifier URIs</em>, there are two  URI patterns that are commonly used in the Linked Data Web: <em>Hash URIs</em> and<em> Slash URIs. </em>Different patterns are proposed for each of these. The  HTTP protocol allows resources denoted by <em>Slash  URIs</em> to be accessed directly, so these are often more effective, but <em>Hash URIs</em> are easier to deploy in  practice, because only one URI is to be dealt with on the server. Several  factors will determine which publishing method is best in a given use case.</p>

<p>Figure 1 provides a decision tree defining tests to best decide between the two publishing methods.</p>
<ol>
  <li>The first test is whether the data publisher also has control of the sub-domain in  which the dataset is published. If an agency is publishing a Linked Data dataset in a sub-domain for which it is not the custodian, <em>Hash URIs <strong>SHOULD </strong></em>be used. This recommendation is made to simplify the management of redirects.</li>
  <li>Similarly, if the custodian of a sub-domain is publishing a Linked Data dataset, but does not  have full control over its publishing infrastructure (i.e. they cannot set up  redirects on their own web servers), <em>Hash  URIs</em> <strong><em>MAY </em></strong>be used.</li>
  <li>If either are possible, i.e. if the Linked Data dataset is published by the custodian of the sub-domain and the custodian has full control over its publishing  infrastructure, the size of dataset should be taken into consideration for deciding if <em>Slash URIs</em> or <em>Hash URIs</em> are used. Although there is no  definitive threshold, if the dataset only includes up to a couple of hundred entities and is not expected to grow much further in the future, a <em>Hash URI </em>pattern <strong><em>MAY </em></strong>be used for its  simplicity. For anything that is considerably bigger and/or is expected to grow  significantly in the future, the use of <em>Slash URIs</em> is <strong><em>RECOMMENDED</em></strong>.</li>
</ol>
![Decision tree for choosing publishing method](https://dl.dropboxusercontent.com/u/45222368/decision_tree.png)

<p align="center">Figure 1: Decision tree for choosing publishing method</p>

<p><strong><em>Hash URIs</em></strong> <br />
  URIs can contain a &ldquo;<em>fragment identifier&rdquo;</em>, an optional special part that is separated from the rest of  the URI by a hash symbol (&ldquo;#&rdquo;). An example of a &ldquo;Hash URI&rdquo; is: <strong>http://education.data.gov.au/resource/schools#2060</strong>.  Hash URIs generally identify a secondary resource, subordinate to the main  resource, which requires a different processing response. For example, in a web  page or linear text document, the fragment identifier typically denotes a  position within the page or document, so the browser usually scrolls to that  point in the document. In RDF the fragment identifier can be used to point to a  subordinate resource. When a <em>Hash URI</em> is dereferenced the HTTP protocol requires the fragment part to be stripped off  before passing the URI to the server. This means that the server cannot  interpret the part after the hash directly. Thus, the presence of a hash in RDF  documents can be used to denote other <em>Non-Information  Resources</em> within the same document without creating ambiguity, as this  subordinate URI will never be served directly by the browser. For example, when  the URI <strong>http://education.data.gov.au/resource/schools#2060 </strong>denoting the school with the identifier 2060 (<em>Non-Information Resource</em>) is requested in a browser, the response  will be <strong>http://education.data.gov.au/resource/schools</strong>,  which is the <em>Document URI</em> describing  this and potentially other resources.</p>
<p><strong><em>Slash URIs</em></strong> <br />
  The second solution for a URI path structure to serve several distinct  resource types is the use of so called &ldquo;Slash URIs&rdquo; for both, the <em>Document URI</em> and the <em>Identifier URI</em>, but to use a special  HTTP status code, &ldquo;303 See Other&rdquo;, to give an indication that a  requested <em>Identifier URI</em> is not a  regular Web document, i.e. <em>Non-Information  Resources</em>. This style was proposed in W3C's Technical Architecture Group in  its httpRange-14 resolution document [8]. For example, if the <em>Slash URI</em> <strong>http://education.data.gov.au/id/school/2060</strong> identifying a  particular school (<em>Non-Information  Resource</em>) is requested in a browser, the Web server is configured to answer  requests to all these URIs with a &ldquo;303  See Other&rdquo; status code  and a Location HTTP header that provides the URL of a document  (<em>Information Resource</em>) that  represents the resource, i.e. a redirect from <strong>http://education.data.gov.au/id/school/2060</strong> to <strong>http://education.data.gov.au/doc/school/2060</strong>.<br />
  <br />
  The interested reader is referred to the W3C Note on &ldquo;Cool URIs for the  Semantic Web&rdquo; [9] for a more in-depth discussion on the difference between the  two.</p>
<p>The following table proposes guidelines for the URI patterns for <em>Slash URIs</em> and <em>Hash URIs</em>.<strong></strong><br />
</p>
<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="135" valign="top" rowspan="2"><strong><em>Identifier URI</em></strong></td>
    <td width="110" valign="top"><strong>[no 21a]</strong></td>
    <td width="312" valign="top"><em>Slash URI pattern</em><br />For <em>Slash URIs</em> the <em>Identifier URI</em> <strong><em>SHOULD </em></strong>contain the token &lsquo;id&rsquo;, a reference to its concept membership {type} and a local name {name} of the &lsquo;Thing&rsquo;.<br />
      <p><strong>/id/{type}/{name} → /id/school/2060</strong><em> [Canberra Grammar]</em></p>
      </td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
  <tr>
    <td width="120" valign="top"><strong>[no 21b]</strong></td>
    <td width="312" valign="top"><em>Hash URI pattern</em><br />For <em>Hash URIs</em> the <em>Identifier URI</em> <strong><em>SHOULD</em></strong> contain the token &lsquo;resource&rsquo; followed by an appropriate identifier that <strong><em>SHOULD </em></strong>be the same as the one used for the dataset, i.e. the {datasetid} and a fragment identifier {name} to name the &lsquo;Thing&rsquo; locally.<br />
      <p><strong>/resource/{datasetid}#{name} → /resource/schools#2060</strong><em> [Canberra Grammar</em></p></td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
  <tr>
    <td width="135" valign="top" rowspan="2"><strong><em>Document URI</em></strong></td>
    <td width="120" valign="top"><strong>[no 22a]</strong></td>
    <td width="312" valign="top"><em>Slash URI pattern</em> <br />For <em>Slash URIs</em> the URI pattern for a <em>Document URI</em> <strong><em>SHOULD </em></strong>contain the token &lsquo;doc&rsquo;, a reference to its concept membership {type} and a local name {name} of the &lsquo;Thing&rsquo;.<br /><p>
        <strong>doc/{type}/{name} → doc/school/2060  </strong><em>[Document about Canberra Grammar]</em></p></td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
  <tr>
    <td width="120" valign="top"><strong>[no 22b]</strong></td>
    <td width="312" valign="top"><em>Hash URI pattern</em> <br />For <em>Hash URIs</em> the <em>Document URI</em> <strong><em>SHOULD </em></strong>contain the token &lsquo;resource&rsquo; followed by an appropriate identifier that <strong><em>SHOULD </em></strong>be the same as the one used for the dataset, i.e. the {datasetid}. The <em>Document URI <strong>MAY </strong></em>contain multiple <em>Identifier URIs</em> that can be distinguished from the document they are defined in by their fragment identifier.< br/>
      <p><strong>/resource/{datasetid}#{name} → /resource/schools#2060</strong><em> [Document that contains information about Canberra Grammar (among potentially other resources)]</em></p></td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
  <tr>
    <td width="135" valign="top" rowspan="3"><strong><em>Ontology URI</em></strong></td>
    <td width="120" valign="top"><strong>[no 23a]</strong></td>
    <td width="312" valign="top">The use of a <em>Hash URI </em>pattern <em>is <strong>RECOMMENDED </strong></em>for <em>Ontology URIs</em> for its simplicity.</td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
<tr>
    <td width="120" valign="top"><strong>[no 23b]</strong></td>
    <td width="312" valign="top">Definition of concepts and relations <strong><em>SHOULD </em></strong>be denoted by the &lsquo;def&rsquo; keyword followed by the ontology name {scheme}, followed by the concept or relationship name {concept}. If the {concept} name is omitted the whole ontology (vocabulary) should be returned.<br /><br />
        <strong>/def/{scheme}#{concept} → /def/school#phaseOfEducation</strong><em>  [The class definition of phaseOfEducation]</em></p>
      <p>If instances of classes, i.e. the actual entities (<em>non-information resources</em>) are modelled as part of the ontology (for example, code lists, finite sets of entities) in a <em>Hash URI pattern</em> the URIs used for the entities <strong><em>SHOULD </em></strong>still follow the <em>Identifier URI</em> pattern.</p></td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
<tr>
    <td width="120" valign="top"><strong>[no 23c]</strong></td>
    <td width="312" valign="top">If instances of classes, i.e. the actual entities (<em>non-information resources</em>) are modelled as part of the ontology (for example, code lists, finite sets of entities) the URIs used for the entities <strong><em>SHOULD </em></strong>still follow the <em>Identifier URI</em> pattern and not the <em>Ontology URI</em> pattern described here.</td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
</table>
<p><strong>Modularising URIs</strong> <br />
  <br />
  Sets of resources may be grouped in modules denoted by URIs that contain an arbitrary number of path segments to indicate a dataset hierarchy as described in Section 2. For each URI type, i.e. for <em>Identifier URIs</em>, <em>Document  URIs</em> and <em>Ontology URIs </em>an  (optional) [<strong>{module}/]*</strong> step can  indicate the module the particular resource belongs to. If a dataset is part of  a module all resources within this dataset <strong><em>MUST </em></strong>use the same path segment. For  example, if no federal identifiers exist for schools, a state may introduce a  dataset about schools within a module, i.e. /<strong>dataset/act/schools</strong> where <strong>act</strong> is the <strong>{module}</strong> and <strong>schools</strong> the <strong>{datasetid}</strong>. Schools identified within this module <strong><em>MUST </em></strong>then  use the <strong>act </strong>module, e.g. <strong>/act/id/school/2060</strong> for the Canberra  Grammar school (see also in the table below).</p>

<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="100" valign="top"><b>[no 24]</b></td>
    <td width="467" valign="top">If a dataset is part of a module all resources within this dataset </em></strong>MUST</em></strong> use the same path segment.</td>
    <td width="100" valign="top"><strong><em>MUST</em></strong></td>
  </tr>
</table>

<p>Classifications other than a state or the administering authority can form the basis of identifiers of modules. For example, primary and secondary  education or public and independent schools could all be distinguished by a  separate module, e.g. <strong>/dataset/act/primary/public/schools</strong> and <strong>/dataset/act/primary/independent/catholic/schools</strong>, <strong>/dataset/act/primary/independent/anglican/schools</strong> etc. where <strong>act</strong>, <strong>primary</strong>, <strong>public</strong>, <strong>independent</strong>, <strong>catholic </strong>and <strong>anglican </strong>are  all module names, whereas <strong>schools </strong>denotes  the datasets in each respective module. However, different type of schools can  also be grouped in sub-datasets of a state-wide or even of a federal school  dataset resulting, for example, in a path structure like <strong>/dataset/schools/publicSchools</strong> or <strong>/dataset/schools/independentSchools</strong> where <strong>schools </strong>is a federal dataset including all schools in Australia and <strong>publicSchools</strong> and <strong>independentSchools </strong>a sub-dataset  including all independent schools in Australia. The decision on how to  structure datasets will be use-case specific. However, individual resources <strong><em>MAY </em></strong>belong  to more than one module, and therefore may be identified by more than one URI,  each related to a different context.</p>
<p>The following table defines the guidelines for how to modularise different URI types.<br />
  <br /></p>

<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="135" valign="top" rowspan="2"><strong><em>Identifier URI</em></strong></td>
    <td width="110" valign="top"><strong>[no 25a]</strong></td>
    <td width="312" valign="top"><em>Slash URI pattern</em> <br />
        <strong>/[{module}/]*/id/{type}/{name} → /act/id/school/2060</strong><em>  [Canberra Grammar defined in the schools dataset of the act module]</em></td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
</tr>
  <tr>
    <td width="110" valign="top"><strong>[no 25b]</strong></td>
    <td width="312" valign="top"><em>Hash URI pattern</em><br />
        <strong>/[{module}/]*/resource/{datasetid}#{name} → /act/resource/schools#2060</strong><em>     [Canberra Grammar defined in the schools dataset of the act module]</em></td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>

  <tr>
    <td width="135" valign="top" rowspan="2"><strong><em>Document URI</em></strong></td>
    <td width="110" valign="top"><strong>[no 26a]</strong></td>
    <td width="312" valign="top"><em>Slash URI pattern</em> <br />
        <strong>/[{module}/]*/doc/{type}/{name} → /act/doc/school/2060</strong><em>  [Document about Canberra Grammar defined in the school dataset of the act module]</em></td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
</tr>
  <tr>
    <td width="110" valign="top"><strong>[no 26b]</strong></td>
    <td width="312" valign="top"><em>Hash URI pattern</em> <br />
        <strong>/[{module}/]*/resource/{datasetid} → /act/resource/schools</strong><em>  [Document in the act module that contains among other resources information about Canberra Grammar]</em></td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
  <tr>
    <td width="135" valign="top" rowspan="2"><strong><em>Ontology URI</em></strong></td>
    <td width="110" valign="top"><strong>[no 27]</strong></td>
    <td width="312" valign="top"><strong>/[{module}/]*/def/{scheme}#{concept} → /act/def/school#phaseOfEducation</strong> <br />
        <em>[The class definition of phaseOfEducation in the context of the act module]</em></td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
</table>
<h2><a name="h.wfjxm50byvq" id="h.wfjxm50byvq"></a>5. Publishing URIs </h2>
<p>A URI may identify a resource in a dataset without ever being resolved  or dereferenced. However, following the Linked Data principles, a URI <strong><em>MUST </em></strong>be resolvable using the HTTP protocol as defined in rule no 1, making it essentially a URL. As URIs in this document are resolved in a sub-domain of data.gov.au, the URI pattern chosen for a dataset has to be registered with data.gov.au in order to be resolvable as a URL.</p>
<p><strong>Registering URIs with data.gov.au</strong> <br />
  The URI for a dataset, in particular the chosen sub-domain, module and datasetid, have to be  registered with data.gov.au. Currently, this process requires one to send an email to <a href="mailto:data.gov@finance.gov.au">data.gov@finance.gov.au</a>, but a Web-enabled management tool  is considered for the future.</p>
<p>Depending on  the publishing method, different URI path structures have to be registered.</p>
<p><strong>Hash URIs</strong> <br />
  For Hash URIs only the <em>Dataset URI</em> has to be  registered:<br />
  <strong>{domain}</strong>.data.gov.au/dataset<strong>[/{module}]*</strong>/<strong>{datasetid}</strong></p>
<p>The physical  location of the document results from this Dataset URI, i.e.:<br />
  <strong>{domain}</strong>.data.gov.au/<strong>[/{module}]*</strong>/resource/<strong>{datasetid}</strong></p>
<p><strong>Slash URIs</strong> <br />
  Since datasets  published in a <em>Slash URI<strong> </strong></em>pattern will typically not physically reside on data.gov.au servers, the physical location of the dataset on an agency server has to be registered with data.gov.au. For <em>Slash URIs</em> two scenarios have to be distinguished, (1) a custodian  of the data.gov.au sub-domain in question is publishing a new Linked Data dataset,  or (2) an agency that is NOT the custodian of a data.gov.au sub-domain is  requesting to publish a new Linked Data dataset under this sub-domain that is  managed by someone else.</p>
<p><strong>Custodian of the data.gov.au sub-domain:</strong> <br />
  The custodian  of a data.gov.au sub-domain only has to register new modules, i.e. the  following URIs have to be registered:</p>
<p><strong>{domain}</strong>.data.gov.au/dataset<strong>[/{module}]*</strong>/<br />
  <strong>{domain}</strong>.data.gov.au/<strong>[/{module}/]*</strong>/id/<br />
  <strong>{domain}</strong>.data.gov.au/<strong>[/{module}/]*</strong>/doc/<br />
  <strong>{domain}</strong>.data.gov.au/<strong>[/{module}/]*</strong>/def/</p>
<p>For each of  these URIs the storage location, i.e. the IP address or the hostname, of the data that will be served by these URIs has to be registered with data.gov.au.</p>
<p>Datasets that are published under existing modules or in the top-level URI path, i.e. directly under <strong>{domain}</strong>.data.gov.au/id/, <strong>{domain}</strong>.data.gov.au/doc/ or <strong>{domain}</strong>.data.gov.au/def/ do not need  to be registered.</p>
<p><strong>Agencies that are NOT the custodian of the respective data.gov.au sub-domain:</strong> <br />
  Agencies that are not the custodian of the sub-domain can only request a new module within  the sub-domain in question, i.e. they cannot publish datasets under the  top-level URI path <strong>{domain}</strong>.data.gov.au/id/, <strong>{domain}</strong>.data.gov.au/doc/ or <strong>{domain}</strong>.data.gov.au/def/. The Dataset  URI has to be registered as above:</p>
<p><strong>{domain}</strong>.data.gov.au/dataset<strong>[/{module}]*</strong>/<strong>{datasetid}</strong><br />
  <strong>{domain}</strong>.data.gov.au/<strong>[/{module}/]*</strong>/id/<br />
  <strong>{domain}</strong>.data.gov.au/<strong>[/{module}/]*</strong>/doc/<br />
  <strong>{domain}</strong>.data.gov.au/<strong>[/{module}/]*</strong>/def/</p>
<p>For each of  these URIs the storage location, i.e. the IP address or the hostname, of the  data that will be served by these URIs has to be registered with data.gov.au.</p>
<p>If the module  name has already been assigned, alternative URI paths will be proposed to the  requester.</p>
<p><strong>Resolving URIs</strong> <br />
  <em>Content negotiation</em> is a mechanism defined for HTTP  that makes it possible to serve different versions of a resource representation  at the same URI. Different client applications have different preferences on  the data format and language which can be indicated in the HTTP header of the  request. For example, a browser usually requests HTML, localized with a natural language such as English or Chinese, while Semantic Web software usually  requests RDF. The server then selects the best match, perhaps from its file system, or by generating the desired content on demand, and sends it back to the client.<br />
  For dereferencing HTTP URIs there are standard patterns [8] that distinguish between the different resource types. The following paragraphs introduce guidelines for the resolving of the different URI types in the  data.gov.au domain.<br />
  <br />
  <br />
  <strong>Resolving Identifier URIs</strong> <br />
  To conform to the Linked data principles [1], a URI for a real-world  &lsquo;Thing&rsquo; must resolve to a document that contains information about that thing. This principle poses different requirements on the architecture, depending on if a <em>Hash URI Pattern</em> or <em>Slash URI Pattern</em> is used to identify the resource.</p>

<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="135" valign="top" rowspan="2"><strong><em>Resolving Identifier URIs</em></strong></td>
    <td width="110" valign="top"><strong>[no 28a]</strong></td>
    <td width="312" valign="top"><em>Slash URI pattern</em> <br />For <em>Slash URIs</em> a &ldquo;303 See Other&rdquo; status code <strong><em>SHOULD</em></strong> be issued for requests for<strong> /id/{type}/{id} </strong>with a response redirecting to <strong> /doc/{type}/{id} </strong>. This indicates to the user that the requested resource is a <em>Non-Information  Resource</em>, while redirecting the user to the document for the &lsquo;Thing&rsquo;, i.e. the <em>Information Resource</em>. Content-negotiation can be used to decide on the specific representation that is returned to the user for the document.</td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
</tr>
  <tr>
    <td width="110" valign="top"><strong>[no 28b]</strong></td>
    <td width="312" valign="top"><em>Hash URI pattern</em> <br />For <em>Hash Identifier URIs</em> the storage location for <strong>/resource/{datasetid}#{id}</strong> <strong><em>SHOULD</em></strong> be <strong>/resource/{datasetid}</strong>. As the fragment part in the Hash URI <strong>/resource/{datasetid}#{id}</strong> is stripped off by the HTTP protocol, this is the default storage location and there is no need to setup a redirect.</td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong>
</tr>
</table>
<p>Rule No 28b makes the <em>Hash Identifier URI </em>pattern very easy to implement while largely maintaining Linked Data principles. In this setting, the <strong><em>document storage location</em></strong> is also the <em>Document URI</em>, whereas any <em>Identifier URI</em> within this document uses the storage location plus a fragment identifier for identifying its <em>Non-Information  Resource</em>. For example, if the Identifier URI is <strong>http://education.data.gov.au/resource/schools#2060</strong>, the <strong>#2060</strong> is stripped off and the document is returned, using the <em>Document URI</em> <strong>http://education.data.gov.au/resource/schools</strong>.<br /></p>
<p><strong>Resolving Document  URIs</strong> <br />
  A <em>Document URI</em> will resolve to  the most appropriate representation as defined by the content-type(s) in the  &lsquo;Accept&rsquo; header of an HTTP request. The guidelines are similar for <em>Hash URIs</em> and <em>Slash URIs</em>.<br /></p>

<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="100" valign="top"><b>[no 29]</b></td>
    <td width="467" valign="top">If the RDF and HTML representations of the resource do not differ in  terms of their information content, the use of the file extension is <strong><em>RECOMMENDED </em></strong>to distinguish the different representations, e.g. .html, .rdf, .owl.</td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 30]</b></td>
    <td width="467" valign="top">If file extensions are used to distinguish between different representations, the type <strong><em>MAY NOT</em></strong> be explicitly stated in any other part of the URI, e.g.<strong> /doc/school/2060.rdf</strong> rather than<strong> /doc/rdf/school/2060.rdf</strong>.</td>
    <td width="100" valign="top"><strong><em>SHOULD NOT</em></strong></td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 31]</b></td>
    <td width="467" valign="top">If the RDF and HTML representations of the resource differ  substantially, i.e. they are not two versions of the same document but different documents altogether, a &ldquo;303  See Other&rdquo; redirect in combination with a content-negotiation <strong><em>SHOULD </em></strong>be set up that points to two separate <em>Document URIs</em>. In this case the use of a token indicating the file type in the <em>Document URI</em> is <em><strong>RECOMMENDED</strong></em>, e.g. <strong> /doc/school/2060 </strong> redirects to <strong> /doc/rdf/school/2060.rdf </strong>for the RDF representation and to<strong> /doc/html/school/2060.html </strong>for the HTML representation.</td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 32]</b></td>
    <td width="467" valign="top">To denote different versions of documents, a &lsquo;date&rsquo; token <strong><em>SHOULD </em></strong>be used for the <em>Document URIs</em> to indicate that the  information is valid on, or from, a particular date. For example, <strong>/doc/html/2012/school/2060</strong> can be used  as a <em>Document URI</em> for the school dataset that is current as of 2012.<br /></td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
</table>

<p><strong>Resolving <em>Ontology URIs</em></strong> <br />
  <em>Ontology URIs</em> are a special kind of <em>Document URI</em> where the document type is always RDF or OWL. Thus, for ontologies that only contain schema-level definitions (i.e. classes/properties) there is no need for content negotiation or redirects. For example, for classes and properties in a <em>Hash URI </em>ontology with the pattern <strong>/def/{scheme}#{concept}</strong>, the hash is automatically stripped off resulting in <strong>/def/{scheme}</strong>, the <em>Document URI</em>.<br /><br />

If instances are included in the same file as the classes and properties, the URI scheme of these instances should follow the <em>Identifier URI</em> pattern as described in Section 4, resulting in the following guideline.</p>

<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="100" valign="top"><b>[no 33]</b></td>
    <td width="467" valign="top">For ontologies using a <em>Hash URI </em>scheme that include both, schema-level (i.e. classes/properties) and instance-level information, the file should be stored in two locations,<strong> /def/{scheme} </strong>and <strong>/resource/{type}</strong> in order to allow  proper resolving of <em>Document URIs</em> and <em>Identifier URIs</em> defined in the ontology.</td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
</table>

<h2><a name="h.h7mypgxdds0" id="h.h7mypgxdds0"></a>6. URI naming conventions </h2>
<p> <br />
  In the recently published RDF1.1 W3C recommendation [12] URIs were  replaced in favour of their internationalized version, the so called  Internationalized Resource identifier (IRI) that allows to contain characters  from the Universal Character Set (Unicode/ISO 10646), including Chinese or  Japanese kanji, Korean, Cyrillic characters, etc. However, considering that  government documents in Australia are mostly published in the English language  the use of URIs for naming resources in Linked Data datasets is <strong><em>RECOMMENDED</em></strong> as defined by rule no 1.</p>
<p><strong>Character Sets used in URI</strong> <br />

<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="100" valign="top"><b>[no 34]</b></td>
    <td width="467" valign="top">For <em>Linked Data dataset URIs</em>, ASCII characters <strong><em>SHOULD </em></strong>be used, i.e. the numbers from 0-9, the uppercase and lowercase English letters from A to Z, and some special characters.</td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 35]</b></td>
    <td width="467" valign="top">Accented letters, diacritical and special language characters <strong><em>SHOULD NOT</em></strong>be used in URIs.</td>
    <td width="100" valign="top"><strong><em>SHOULD NOT</em></strong></td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 36]</b></td>
    <td width="467" valign="top">Spaces in URIs are <strong><em>NOT RECOMMENDED</em></strong>.</td>
    <td width="100" valign="top"><strong><em>NOT RECOMMENDED</em></strong></td>
  </tr>
  <tr>
    <td width="100" valign="top"><b>[no 37]</b></td>
    <td width="467" valign="top">URIs are case-sensitive apart from the domain name. However, using upper/lower case as a differentiating factor in URIs is <strong><em>NOT RECOMMENDED</em></strong>.</td>
    <td width="100" valign="top"><strong><em>NOT RECOMMENDED</em></strong></td>
  </tr>
</table>
  <p><strong>Naming resources</strong></p>
<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="100" valign="top"><b>[no 38]</b></td>
    <td width="467" valign="top">English <strong><em>SHOULD </em></strong>be exclusively used for naming resources, unless the  real-world thing is commonly known in English by its native name (e.g. aboriginal name).</td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
</table>

<table border="1" cellspacing="0" cellpadding="0">
  <tr>
    <td width="135" valign="top" rowspan="2"><strong><em>Dataset URI</em></strong></td>
    <td width="110" valign="top"><b>[no 39a]</b></td>
    <td width="312" valign="top">Lower case <strong><em>MUST</em></strong> be used for the entire URI path up to the {datasetid} part. No particular recommendations are made for the {datasetid} part, which can use any casing as deemed appropriate for the domain.</td>
    <td width="100" valign="top"><strong><em>MUST</em></strong></td>
  </tr>
  <tr>
    <td width="110" valign="top"><b>[no 39b]</b></td>
    <td width="312" valign="top">Datasets denote a collection of real-world &lsquo;Things&rsquo; and thus <strong><em>SHOULD </em></strong>use the plural for the {datasetid}, e.g. <strong>/dataset/schools</strong>.</td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
  <tr>
    <td width="135" valign="top" rowspan="6"><strong><em>Identifier URI</em></strong></td>
    <td width="110" valign="top"><b>[no 40a]</b></td>
    <td width="312" valign="top">Existing identifiers <strong><em>MUST </em></strong>always be reused    when applicable (even if they are not compliant with the rules on the use of special characters, whitespaces, ... as stated above).</td>
    <td width="100" valign="top"><strong><em>MUST</em></strong></td>
  </tr>
  <tr>
    <td width="110" valign="top"><b>[no 40b]</b></td>
    <td width="312" valign="top">Lower case <strong><em>MUST</em></strong> be used for the entire URI path up to the {name} part. No particular recommendations are made for the {name} part, which can use any casing as deemed appropriate for the domain.</td>
    <td width="100" valign="top"><strong><em>MUST</em></strong></td>
  </tr>
  <tr>
    <td width="110" valign="top"><b>[no 40c]</b></td>
    <td width="312" valign="top">A singular name <strong><em>SHOULD </em></strong>always be used for naming one particular physical or abstract real-world thing, except if the word to be used for the thing is only available as plural (e.g. series, species).</td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
  <tr>
    <td width="110" valign="top"><b>[no 40d]</b></td>
    <td width="312" valign="top">The plural <strong><em>SHOULD </em></strong>always be used for naming a set/list of real-world &lsquo;Things&rsquo;, e.g. <strong>/id/school/independentSchools</strong> to identify a list of all independent schools in a dataset.</td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
  <tr>
    <td width="110" valign="top"><b>[no 40e]</b></td>
    <td width="312" valign="top">Acronyms <strong><em>SHOULD </em></strong>all be in upper cases or    all in lower cases.</td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>
  <tr>
    <td width="110" valign="top"><b>[no 40f]</b></td>
    <td width="312" valign="top">A de-identified scheme <strong><em>SHOULD </em></strong>be used for    persons, i.e. do not include the name of the person in the URI.</td>
    <td width="100" valign="top"><strong><em>SHOULD</em></strong></td>
  </tr>

  <tr>
    <td width="135" valign="top"><strong><em>Ontology URI</em></strong></td>
    <td width="522" valign="top" colspan="3">For class names and property names in <em>Ontology URIs</em> no formatting guidelines are made. Common practise in ontology engineering is to use either lower or upper camel case, e.g. <strong>/def/phaseOfEducation</strong> or <strong>/def/PhaseOfEducation, </strong>or dashes/underscores as word separators, e.g. <strong>/def/phase_of_education</strong></td>
  </tr>
</table>
<h1><a name="h.depmzbrccojw" id="h.depmzbrccojw"></a>7. HOW-TO publish a Linked Data dataset on data.gov.au</h1>
<p>In this section a walk-through example is presented on how to publish a Linked Data dataset on data.gov.au. The instructions presented are based on the example school dataset that was used throughout the document. For the example, let us assume a state government agency governing the educational portfolio in the Australian Capital Territory is to publish the &ldquo;Locations of all ACT schools&rdquo; in a Linked Data fashion. Currently, a CSV version of this dataset is available at <a href="http://www.data.gov.au/dataset/location-of-act-schools">http://www.data.gov.au/dataset/location-of-act-schools</a> published by the Department of Education and Training (ACT).</p>
<h2><a name="h.kdopiiao7s23" id="h.kdopiiao7s23"></a>Choose Sub-Domain</h2>
<p>First, an appropriate sub-domain for the dataset has to be chosen. For the &ldquo;Location of ACT schools&rdquo; the <strong>&ldquo;education&rdquo; </strong>sub-domain or <strong>&ldquo;governance&rdquo; </strong>sub-domain seem appropriate, depending on the level of detail in the dataset and its relation to other datasets. Let us assume, the <strong>&ldquo;education&rdquo; </strong>sub-domain is chosen for the example ACT school dataset.</p>
<h2><a name="h.de8w7gz2pkor" id="h.de8w7gz2pkor"></a>Choose a path structure (module)</h2>
<p>Next, it has to be decided if the dataset is appropriate to be included in the top-level of the respective sub-domain, e.g. <strong>education.data.gov.au/dataset/</strong> or if it is better placed within a module, i.e. an additional path structure that is added to the URI to denote the datasets domain of discourse. The sub-levels of the AGIFT classification of functions in the Australian  Government can be consulted to make a decision on the appropriate module. If the dataset is a state dataset, the appropriate state identifier should be used in the module name, i.e. <strong>education.data.gov.au/dataset/act/</strong> in the ACT school example.</p>
<h2><a name="h.2jjsxvokqhq1" id="h.2jjsxvokqhq1"></a>Decide on publishing method</h2>
<p>Next, the publishing agent has to decide on the publishing method to use. The decision tree proposed in Figure 1 in Section 4 can be consulted to help in deciding whether to use <em>Hash URIs</em> or <em>Slash URIs</em>. In the case of the ACT school dataset, <em>Hash URIs <strong>MAY </strong></em>be used regardless whether the published is the custodian of the education.data.gov.au sub-domain, as the dataset includes only 100 entities and is not expected to grow significantly in the future. For the remainder of this guide, let us assume <em>Hash URIs</em> are used.</p>
<h2><a name="h.wrrkhndzriqm" id="h.wrrkhndzriqm"></a>Register URI path with data.gov.au</h2>
<p>Once the sub-domain and module have been chosen, a name (datasetid) for the dataset has to be chosen and the URI path has to be registered with data.gov.au. As outlined above, an email has to be sent to <a href="mailto:data.gov@finance.gov.au">data.gov@finance.gov.au</a> to requests a URI, in our example:</p>
<p><strong>http://education.data.gov.au/dataset/act/schools</strong></p>
<p>If the URI is already assigned, an alternative URI will be proposed to the requester. Let us assume the URI is successfully registered for the remainder of this example.</p>
<h2><a name="h.hkdkg9p0mutu" id="h.hkdkg9p0mutu"></a>Develop the dataset</h2>
<p>Once the URI path is registered, the Linked Data dataset can be developed. As a Hash URI pattern was chosen, entities within this dataset will be identified with URIs such as: <strong>http://education.data.gov.au/act/resource/schools#2060</strong>, denoting Canberra Grammar school.</p>
<h2><a name="h.kwb19j7bistv" id="h.kwb19j7bistv"></a>Publish the dataset on data.gov.au</h2>
<p>When finished the Linked Data dataset is uploaded to the data.gov.au servers through the CKAN system. The system will automatically create the metadata that will be accessible at the Dataset URI, i.e. at <strong>http://education.data.gov.au/dataset/act/schools</strong>. The metadata will also include a reference to the storage location, which will be <strong>http://education.data.gov.au/act/resource/schools.rdf</strong>.</p>
<h2><a name="h.1vlcemw9iv0h" id="h.1vlcemw9iv0h"></a>References </h2>
<p>[1] Linked Data – Design Issues,<a href="http://www.w3.org/DesignIssues/LinkedData.html">http://www.w3.org/DesignIssues/LinkedData.html</a> <br />
  [2] Designing URI Sets for the UK Public Sector,<a href="http://www.cabinetoffice.gov.uk/resource-library/designing-uri-sets-uk-public-sector">http://www.cabinetoffice.gov.uk/resource-library/designing-uri-sets-uk-public-sector</a> <br />
  [3] 223 Best Practices URI Construction,<a href="http://www.w3.org/2011/gld/wiki/223_Best_Practices_URI_Construction">http://www.w3.org/2011/gld/wiki/223_Best_Practices_URI_Construction</a> <br />
  [4] Defra, UK Linked Data,<a href="http://location.defra.gov.uk/resources/linked-data/">http://location.defra.gov.uk/resources/linked-data/</a> <br />
  [5] Data Catalog Vocabulary (DCAT), W3C Working Draft,<a href="http://www.w3.org/TR/2013/WD-vocab-dcat-20130312/">http://www.w3.org/TR/2013/WD-vocab-dcat-20130312/</a> <br />
  [6] DCMI Metadata Terms,<a href="http://purl.org/dc/terms/">http://purl.org/dc/terms/</a> <br />
  [7]<a href="http://tools.ietf.org/html/rfc6570">RFC 6570</a> - URI Template, Proposed Standard, Internet  Engineering Task Force (IETF), March 2012<a href="http://tools.ietf.org/html/rfc6570">http://tools.ietf.org/html/rfc6570</a> <br />
  [8] [httpRange-14] Resolved.<a href="http://lists.w3.org/Archives/Public/www-tag/2005Jun/0039.html">http://lists.w3.org/Archives/Public/www-tag/2005Jun/0039.html</a> <br />
  [9] Cool URIs for the Semantic Web.<a href="http://www.w3.org/TR/cooluris/">http://www.w3.org/TR/cooluris/</a> <br />
  [10] RFC2616 Hypertext Transfer Protocol -- HTTP/1.1, Internet  Engineering Task Force (IETF), June 1999<a href="http://www.ietf.org/rfc/rfc2616">http://www.ietf.org/rfc/rfc2616</a> <br />
  [11] S. Bradner.<a href="http://www.ietf.org/rfc/rfc2119.txt">Key words for use in RFCs to Indicate Requirement  Levels.</a> March 1997. Internet RFC 2119. URL:<a href="http://www.ietf.org/rfc/rfc2119.txt">http://www.ietf.org/rfc/rfc2119.txt</a><br />
  [12] RDF 1.1 Concepts and Abstract Syntax, W3C Proposed Recommendation, 09 January  2014, <a href="http://www.w3.org/TR/rdf11-concepts/">http://www.w3.org/TR/rdf11-concepts/</a></p>
<div id="ftn1">
  <p><a href="#_ftnref1" name="_ftn1" title="" id="_ftn1"> </a> See  http://agift.naa.gov.au/</p>
</div>
</body>
</html>
