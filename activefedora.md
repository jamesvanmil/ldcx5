# ActiveFedora at LDCX^5
## Backgronud

	class MyObject < ActiveFedora::Rdf::Resource
		property :title, predicate: RDF::DC.title
		property :creator, predicate: RDF::DC.creator, class_name: "Person"
	end

	o = MyObject.new
	o.rdf_subject ## returns bnode
	o.set_subject! RDF::URI.new("http://example.org/1")
	o.title = "Welcome"
	o.dump.(:ntriples)
	
	class Person < ActiveFedora::Rdf::Resource
		configure type: RDF::FOAF.Person
		property :name, predicateL RDF::FOAF.name
	end

	person = Person.new
	person.name = "Big D"

	o.creator = person
	o.dump(:ntriples)

	o << RDF::Statement.new(o.rdf_subject, RDF::DC.creator, "Bob")
	o.creator ##returns "Bob"

	
	ActiveFedora::Rdf::Repositories.add_repository :default, RDF::Repository.new
	
	MyObject.configure repository: :default  	## Will cause new objects to persist to a repostory, such as 4Store
																						## Objects will persist upstream until they hit a parent

	s = ActiveFedora:Rdf::REsource.new('http://dbpedia.org/resource/Stanford/')
	s.dump :ntriples 	## is empty
	s.fetch						## will get data
	s.dump :ntriples  ## data!!!
	
	s.rdf_label  ##"meta-accessor"

## Discussion
ObjectResource class connects this all to Fedora. When managing Fedora data, you're making that datastream the triplestore for the graph; opportunity to think about what data you want to reuse, vs persisting to each datastream

With ActiveFedora 6, without comples nodes, things will be the same. 

See Tom's dpla_map code on Github: [https://github.com/no-reply/dpla_map](https://github.com/no-reply/dpla_map)

ActiveFedora 7 "identifiable" class makes ActiveFedora Base object behave like a graph node

Normalized approach (OSU, UCSD) impacts performance because of repeated calls to the repository. Declan: you don't do RDF for performance, you use it for stability; use Solr for performance.

Indexing is an interesting problem - not solved in ActiveFedora. OSU overrides Solr to reindex the URI and the label - to use the label in facets and to build out objects as needed

Take a look at [this](https://github.com/OregonDigital/oregondigital/blob/master/lib/oregon_digital/controlled_vocabularies/geographic.rb)

## ActiveTriples
Hydra Framework to manage broad swath of RDF data; connection with Solr. Interested in tooling for the management of RDF data.

Opportunity for coordinating an Indexing Strategy for RDF (later this week) - how far should to_solr go? Framing in JSON LD - See [this](https://github.com/mtrudel/pragmatic_context)
