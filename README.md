
Submarine Cable Map
===================

[![Submarine Cable Map](http://26.media.tumblr.com/tumblr_lru2g8MJaV1qcsswzo1_500.png)](http://www.submarinecablemap.com)

[TeleGeography's](http://www.telegeography.com) submarine cable map is based on our authoritative [Global Bandwidth](http://www.telegeography.com/research-services/global-bandwidth-research-service/) research and depicts international active and planned submarine cable systems and their landing stations. The map presents data about each cable, including landing points, owners, length, ready-for-service (RFS) date, and website. Try it today! Visit [http://www.submarinecablemap.com](http://www.submarinecablemap.com).


Installation
------------

    $ git clone git://github.com/telegeography/www.submarinecablemap.com.git

Point your webserver's document root to the public directory and that's it.


Updates
-------

To make sure you get any updates, just watch this repository and perform a pull when you see any new commits:

    $ cd www.submarinecablemap.com
    $ git pull


How did you make the Submarine Cable Map?
-------------------------------

[TeleGeography](http://www.telegeography.com) draws the cable routes and plots the landing points with [Adobe Illustrator](http://www.adobe.com/products/illustrator.html). Using [Avenza's MAPublisher](http://www.avenza.com/mapublisher) plug-in, which works with Illustrator, two sets of data are exported as KML files: the cable routes (as MultiLineStrings) and landing points (as Points). These KML files are then parsed to create CSV files that are uploaded to Google Fusion Tables.

We use [Google's Maps API v3.](http://code.google.com/apis/maps/documentation/javascript/) to transform the [Google Fusion Tables](http://www.google.com/fusiontables) into two separate map layers of cable routes and landing points. The interactivity on the map is driven by javascript and was written in-house at TeleGeography.

This interactive map Javascript was created using the [Node.js](http://nodejs.org/) utility [CoffeeScript](http://coffeescript.org/) written by Jeremy Ashkenas, the [Ember](http://emberjs.com/) web application framework, the [HTML5 Boilerplate](http://html5boilerplate.com/) front-end template, the [node-build-script](https://github.com/h5bp/node-build-script) and [node-ember-precompile](https://github.com/gabrielgrant/node-ember-precompile) tools.  The CoffeScript for the map was written in-house at TeleGeography.

Notable Commandline examples:

	# Install ember-precomile from github to get versions correct.
	npm install --from-git git://github.com/gabrielgrant/node-ember-precompile.git
	# precompile handlebars templates
	ember-precompile handlebars/*.handlebars -f src/javascripts/handlebars.tmpl.js
	
	# Used watchr to compile coffeescript/handlebars.
	watchr bin/script.watchr
	
	# Watch, server and build using h5bp, very helpful
	h5bp watch
	h5bp server
	h5bp build:minify


How can I download the KML or a CSV of the dataset?
--------------------------------------------------

Below are links to both of the datasets used for the [Submarine Cable Map](http://www.submarinecablemap.com).

__Submarine Cables:__

[https://www.google.com/fusiontables/DataSource?docid=1pY5tMAMkf36aH-N2VvXPxnmjPblcQnONodZ32fk#map:id=3](https://www.google.com/fusiontables/DataSource?docid=1pY5tMAMkf36aH-N2VvXPxnmjPblcQnONodZ32fk#map:id=3)

__To download as KML try the following steps:__

1. Click 'File' then 'Download'.
2. Then select the KML radion button and click 'Download'

__Landing points:__

[https://www.google.com/fusiontables/DataSource?docid=1y38C_S73_osEB-L60DiRS7JJFARw03SnYzVJtdg#map:id=3](https://www.google.com/fusiontables/DataSource?docid=1y38C_S73_osEB-L60DiRS7JJFARw03SnYzVJtdg#map:id=3)


__To download as KML try the following steps:__

1. Click 'File' then 'Download'.
2. Then select the KML radion button and click 'Download'

__Note:__ For landing points, modify the 'Select location' dropdown menu to 'coordinates' from 'id', then click 'Download KML' to get the landing point data.


Questions? Corrections?
------------------------

[cablemap@telegeography.com](mailto:cablemap@telegeography.com)
