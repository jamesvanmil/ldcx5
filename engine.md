#How to build an engine - Core practices

[Rails guide](http://guides.rubyonrails.org/engines.html)

Curate and Sufia use mountable engines.
Resque is an explemlar of a mountable engine.

Would like to see Hydra::Engine.new (to handle conventions of Hydra engines)

Jeremy has a hydramaton plugin_generator.rb - good place to extract what we want.

It's a convention for rails plugins to have a namesapce, but this behavior isn't available by default:

	Hydra::MyPlugin

More fully functional plugins may be Engines; smaller pieces (such as Works) could be Railties

Plugin demo:

	$ rails plugin -h  ## to get options

There are templates (-m PATH_TO_TEMPLATE)
Skip ActiveRecords (-O)
We'll move the dummy path (Hydra convention)
Namespace isolation will be complicated

	$ rails plugin new hydra_myplugin -T --dummy-path=spec/internal --mountable 
	... output ...

For Hydra, will have to replace MIT license with Apache, replace rdoc with md, add rspec to gemspec:

	s.add_development_dependency "rspec-rails"
	$ bundle install
