# LiveBus

A bit of an experiment...

We're animating the movement of Honolulu's TheBus system, in the browser.

### What is this?

Here's a taste of [~7 minutes compressed to 45 seconds on Vimeo](http://vimeo.com/70266760).

This is a simple web app which combines:

* Honolulu's [TheBus](http://www.thebus.org) vehicle location data (the same used for the [Google Transit Feed Specification (GTFS) - realtime](https://developers.google.com/transit/gtfs-realtime/) service)
* The [ProtoBufJS](https://github.com/dcodeIO/ProtoBuf.js) library (installed via npm), to parse [Protocol Buffer](https://developers.google.com/protocol-buffers/) data from GTFS-realtime, translating it into JSON.
* [D3.js](http://d3js.org) to render the SVG maps and animate bus activity.
* [Underscore.js](http://underscorejs.org), because it's nearly impossible to maintain my sanity in JavaScript without it.
* The [Meteor JavaScript web application framework](http://meteor.com) to tie it all together.

This experiement was really an excuse for me to try out the Meteor web development framework. TheBus presented itself as a good candidate as it provides realtime information on its bus locations. Once bus positions are added/updated in MongoDB, Meteor syncs that data with any connected browsers. 

D3 handles moving the dots on the map, since it ties data to SVG elements and animations to changes to that data.

In this way, I write very little code. It's fairly declarative in nature. Et, voilà ! Realtime bus map.

## How do I use this?

I don't know.

It kind of depends. This implementation is fairly specific to TheBus. But, that said, if your city uses GTFS-realtime, you could swap your system's data URL and `.proto` into [`server.js`](https://github.com/PasDeChocolat/LiveBus/blob/master/server/server.js).

Of course, you'll also have to use a different map. I've written a bit about how to create these maps in D3 before. [My write-up](http://pasdechocolat.com/2013/05/03/mapping-hawaii/) is just an extension of the formal [D3 write-up by Mike Bostock](http://bost.ocks.org/mike/map/), but mine's tailored to Hawai‘i.

## Notes

* This is not using TheBus' older HEA API. It favors the GTFS-realtime feed, as this is the direction we seem to be going in for future services.

## Installation/Running

* Install [node.js](http://nodejs.org/)
* Install [Meteor](http://meteor.com)
** curl https://install.meteor.com | sh
* Run app
** cd LiveBus
** meteor

## License

<a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by-sa/3.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/3.0/">Creative Commons Attribution-ShareAlike 3.0 Unported License</a>.

Copyright © 2013 Pas de Chocolat, LLC
