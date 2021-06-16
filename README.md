TouchBusinessCard - Ruby
===================================
Shoify App for Touch Business Card, built with Ruby
  
Project Period
----------------------
- Start: 2019.10.4
- End: 2019.12.9

## Environment
- Framework: Ruby/Rails
- Cloud Server: Heroku
- DB: Postgres v9.6
- Packages: Yarn, Node, Ruby/Rails, Webpack
- Programming Language: Ruby, jQuery, CSS, HTML

## Project History
- Built App site connected to Shopify
- Integration: Lob Payment

## SETUP
- Build Repo
````
	yarn update 
````

- Rails Build
````
	rails server
	ruby ./bin/webpack-dev-server
````

- web: PORT=3000 bundle exec rails s
- webpacker: ruby ./bin/webpack --watch --progress --colors
- worker: bundle exec rails jobs:work
- Ngrok on Local
ngrok http -region=eu -hostname=[ngrok_site_link] 3000

## CODE REVIEW

- payment part
- Lob api part
- shopify connection part for customes info get
- DB structure

## CODE FIX

gem uninstall pg
gem install pg -v 0.19.0 -- --with-pg-config="C:\Program Files\PostgreSQL\9.6"

- rmagic
	- installed imagemagick 6.9
	- gem install rmagick -v 0.18.4 -- --with-opt-dir="C:\Program Files\ImageMagick-6.9.11-Q16-HDRI"

- 2.4/pg_ext.so error
	- Upgrade pg version from Gemfile
	- origin version: 0.18.4
	- pg (0.21.0)
	- pg (0.21.0-x64-mingw32)

- Ruby Eventmachine 2.4/rubyeventmachine
	- origin version: 1.2.5

- File: eventmachine.rb
	- Add code to top: require 'em/pure_ruby'

- Please add gem 'tzinfo-data' to your Gemfile
	- File: gemfile
	- Add code: gem 'tzinfo-data'

- /lib/ruby/gems/2.4.0/gems/eventmachine-1.2.5-x64-mingw32/lib/em/pure_ruby.rb:1049:in 'bind': An address incompatible with the requested protocol was used. - bind(2) for [::1]:3000 (Errno::EAFNOSUPPORT)
````
file: gemfile
Add code: gem 'puma'
gem "tzinfo-data"
gem "puma"
````
