.. _dojo/moduleUrl:

==============
dojo.moduleUrl
==============

:since: v0.9

.. contents ::
   :depth: 2

dojo.moduleUrl is used to return a dojo._Url object relative to a module.

Usage
=====

Dojo 1.7 (AMD)
--------------

.. js ::

   require(["dojo/_base/kernel", "dojo/_base/xhr", "dojo/dom"], function(dojo, xhr, dom){
      // points to $dojoroot/dijit/form/tests/TestFile.html
      var url = dojo.moduleUrl("dijit.form", "tests/TestFile.html");
      xhr.get({
         url: url,
          load: function(html){
              dom.byId("foo").innerHTML = html;
         }
      });
   });


Dojo < 1.7
----------

.. js ::

   // points to $dojoroot/dijit/form/tests/TestFile.html
   var url = dojo.moduleUrl("dijit.form", "tests/TestFile.html");
   dojo.xhrGet({
       url: url,
       load: function(html){
            dojo.byId("foo").innerHTML = html;
       }
   });

See also
========

* :ref:`dojo.registerModulePath <dojo/registerModulePath>`
* :ref:`dojo.cache <dojo/cache>`
