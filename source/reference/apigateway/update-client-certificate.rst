[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway update-client-certificate:


*************************
update-client-certificate
*************************



===========
Description
===========



========
Synopsis
========

::

    update-client-certificate
  --client-certificate-id <value>
  [--patch-operations <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--client-certificate-id`` (string)


``--patch-operations`` (list)


  A list of operations describing the updates to apply to the specified resource. The patches are applied in the order specified in the list.

  



Shorthand Syntax::

    op=string,path=string,value=string,from=string ...




JSON Syntax::

  [
    {
      "op": "add"|"remove"|"replace"|"move"|"copy"|"test",
      "path": "string",
      "value": "string",
      "from": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

clientCertificateId -> (string)

  

  

description -> (string)

  

  

pemEncodedCertificate -> (string)

  

  

createdDate -> (timestamp)

  

  

expirationDate -> (timestamp)

  

  

