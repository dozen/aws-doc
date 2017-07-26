[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway update-base-path-mapping:


************************
update-base-path-mapping
************************



===========
Description
===========



Changes information about the  BasePathMapping resource.



========
Synopsis
========

::

    update-base-path-mapping
  --domain-name <value>
  --base-path <value>
  [--patch-operations <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)


  The domain name of the  BasePathMapping resource to change.

  

``--base-path`` (string)


  The base path of the  BasePathMapping resource to change.

  

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

basePath -> (string)

  

  The base path name that callers of the API must provide as part of the URL after the domain name.

  

  

restApiId -> (string)

  

  The name of the API.

  

  

stage -> (string)

  

  The name of the API's stage.

  

  

