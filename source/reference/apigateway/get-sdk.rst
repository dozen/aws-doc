[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-sdk:


*******
get-sdk
*******



===========
Description
===========



========
Synopsis
========

::

    get-sdk
  --rest-api-id <value>
  --stage-name <value>
  --sdk-type <value>
  [--parameters <value>]
  outfile <value>




=======
Options
=======

``--rest-api-id`` (string)


``--stage-name`` (string)


``--sdk-type`` (string)


``--parameters`` (map)




Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``outfile`` (string)
Filename where the content will be saved



======
Output
======

contentType -> (string)

  

  

contentDisposition -> (string)

  

  

body -> (blob)

  

  

