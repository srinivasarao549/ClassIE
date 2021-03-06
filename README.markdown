ClassIE 0.3.0
=============

Following a H5BP's commit discussion (https://github.com/paulirish/html5-boilerplate/commit/e5e057e53815ed55f4ecfaef3057bf2940c7c0b2), I've decided to write an unobstrusive tiny library to automatically detect Internet Explorer version and bring us a sure way to use polyfills and IE CSS fixes.

Overall remarks
---------------

- Please don't use the non minified version as it's the development version: the build step still adds some more code
- IE5.5 is supported as IE6 version since they're quite the same
- Others than IE will not parse ClassIE
- IE10 and ulterior don't support conditional comments anymore (http://blogs.msdn.com/b/ie/archive/2011/07/06/html5-parsing-in-ie10.aspx), then they will be all recognized as IE10 by ClassIE

JS
--

The `IE` variable is available to know under which version of Internet Explorer your script is loaded.

    if(IE<=8){
        // some polyfills
    }

For browsers other than IE, `IE` variable will return `-1`.

CSS
---

Internet Explorer version is also accessible with CSS classes since ClassIE adds the current IE browser version to the `html` markup like: `<html class="ie8">`.

Then, using ClassIE with your stylesheets is pretty simple:

    .ie6 #contents,
    .ie7 #contents{
        // some specific properties
    }

License
-------

This library is published under the MIT license.

Special thanks
--------------

Thanks to James Padolsey for his wonderful CC IE detection idea: https://gist.github.com/527683
