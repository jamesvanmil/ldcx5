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
