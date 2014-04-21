## Lightning talks

### IIIF - INstitutional Image Interoperability Framework

Stuart Snyderman - [http://iiif.io](http://iiif.io). Set of APIs for sharing images. Metadata API and image API. Close to two dozen instutions contributing. 

Simeon Warner - updaing impage API to 2.0. Working on presentation (metadata) API. Question about tooling for annotating images.

### DPLA metadata aggregration

25 different aggregators. Talk about aggregation stack - issues emerging from assumptions. No understanding of data form application. Interested in working with others about doing aggregation and reconciling with vocabularies. RDF is appealing. 

Jon Stroop - Princeton has a similar problem on a smaller scale. Resource Sync is an interesting solutions? Something to tag on?

Tom Cramer - Interested in Hydra or Fedora 4 as an API to expose resources.

### RDF and Hydra 7 

Tom Johnson - Active Fedora 7 came with overhaul of RDF - rewrote for that resources are modeled as a subgraph of a larger graph - Ruby wrapper around RDF to allow writing and persisting. Work around RDF in Fedora 4. Session is an opportunity to get everyone up to speed. Also working on a linked vocabs tool with SKOS, RDFS, or OWL for modeling and enforcement of vocabularies.

### Are we doing a good job sharing?

Frisen - Examples of successful share components? Examples and post-mortem on failed sharing.

### EAD on Blacklight (BeadL)

Tom Cramer - would like solution for displaying EADs in Blacklight.

### Hadoop for repos

Use cases unclear - some ideas. 

### DevOps

Relationships with systems parters - making things less mysterious for partners. 

### WebComponents

Zumwalt - Angular, Ember, and Backbone for UI. Google pushing WebComponents - will be part of HTML 6. Sharing and reuse of interactive components. Looking at reimplementing Blacklight views as WebComponents.

### Hydra and ArchiveSpace

Giarlo - Many of us use Hydra and are planning to adopt ArchiveSpace. What makes sense in terms of interoperability? Have been working to gather integration use cases as user stories. Looking to advance user stories and do some planning. Meyer 182 Monday, 2pm.

### Hydra-works

Giarlo (on bahlf of Carolyn Cole) - Intellectual works in Hydra - looking at work from Hydramata and applying across hydra

### Hydra Roles for Users and Groups

David Chandek-Start - many use cases don't fit hydra roles. Create a lot of groups with Grouper - requring long names and long Solr queries, which was breaking things. Hydra permissions don't deal with right to create. Not really a Hydra way to do this. Might be a place for roles in the Hydra API.

### Adding proxy deposit to sufia

Jim Coble - Needs to allow staff member to upload on behalf of others. Have been copying code from Scholarsphere. Common enough to integrate into Sufia?

### Spotlight

Stanford demoed Spotlight with the goal of finding early adopters.

### Mirador

IIIF client to give direct access to objects via OpenSeadragon library. Metadata now incorporates annotations - goal to serve rich resources with annotations in a shared environment. Working with other instutions to develop plug-ins.


### GeoMonitor

Service monitoring for geodata server availibility.

### Bulk ingest

Mark Bussey - questions about catching errors during ingest as early as possible - trying to avoid cleaning, showing status, leveraging backgroud processing. Batch status reports. A lot of issues that don't have to do with crosswalking. What's the right way to present errors?

### Linked Data for Libraries

Cornell moving library catalog to Blacklight - moving library catalog data into Solr through an RDf blob. How to share data between institutions? (Harvard, Stanford) E.g., usage data, open access resources, etc. Manging RDF data with Hydra.

### DPLA stack

Mark Matenzio - [https://github.com/dpla/ingestion](https://github.com/dpla/ingestion)
