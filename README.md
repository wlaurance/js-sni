js-sni
======

Load this script over https. If the load succeeds, it redirects browser to the https version of the url.

###Why

This is an algorithm for serving clients who support [SNI](http://en.wikipedia.org/wiki/Server_Name_Indication).

It isn't foolproof (what is?), but the algorithm is like this

* Only ever put http urls out in the public indexed internets.
* Add the script tag for `js-sni-min.js` into your html with **the https** endpoint
* You **have** to have it load from the **https** server of your site. If you don't, then this script is useless.
* Essentially, if the browser supports SNI, the script will load and run the redirect function. If SNI is not supported, then the browser remains on the http endpoint.

If a user, with a non supported browser, hits an https URI on your site, then there is nothing you can do.
The browser will more than likely show certerficate warnings.

Because the SNI stuff is done during the TCP/TLS handshake process, http cannot do anything.
