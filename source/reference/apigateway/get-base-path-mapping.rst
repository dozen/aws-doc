[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-base-path-mapping:


*********************
get-base-path-mapping
*********************



===========
Description
===========



Describe a  BasePathMapping resource.



========
Synopsis
========

::

    get-base-path-mapping
  --domain-name <value>
  --base-path <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)


  The domain name of the  BasePathMapping resource to be described.

  

``--base-path`` (string)


  The base path name that callers of the API must provide as part of the URL after the domain name. This value must be unique for all of the mappings across a single API. Leave this blank if you do not want callers to specify any base path name after the domain name.

  

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

  

  

