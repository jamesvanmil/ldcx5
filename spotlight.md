#Installing Spotlight

	git clone git@github.com:sul-dlss/spotlight.git
	bundle install
	bundle exec rake jetty:download
	" jetty:unzip
	" spotlight:configure_jetty
	" engine_cart:generate
	" jetty:start
