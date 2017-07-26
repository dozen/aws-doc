[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-export:


**********
get-export
**********



===========
Description
===========



========
Synopsis
========

::

    get-export
  --rest-api-id <value>
  --stage-name <value>
  --export-type <value>
  [--parameters <value>]
  [--accepts <value>]
  outfile <value>




=======
Options
=======

``--rest-api-id`` (string)


``--stage-name`` (string)


``--export-type`` (string)


``--parameters`` (map)




Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--accepts`` (string)


``outfile`` (string)
Filename where the content will be saved



======
Output
======

contentType -> (string)

  

  

contentDisposition -> (string)

  

  

body -> (blob)

  

  

