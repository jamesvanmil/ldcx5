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
	$ git init ##etc... omitting futher notes about git; commit as needed

You should not include the Gemfile.lock in the git repo; make sure it's in the .gitignore

	$ bundle install

Wire up rspec stuff:

	$ rspec --init 

Run rspec to test that it works

	$ rspec

Need to name hydra_myplugin files:

	$ mv hydra.myplugin.gemspec hydra-myplugin.gemspec

Maniupulate the app/\*/hyrda_myplugins dirs in to app/\*/hydra/myplugins (this is important for the namespacing)

