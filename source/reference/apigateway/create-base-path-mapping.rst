[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway create-base-path-mapping:


************************
create-base-path-mapping
************************



===========
Description
===========



Creates a new  BasePathMapping resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/CreateBasePathMapping>`_


========
Synopsis
========

::

    create-base-path-mapping
  --domain-name <value>
  [--base-path <value>]
  --rest-api-id <value>
  [--stage <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  The domain name of the  BasePathMapping resource to create.

  

``--base-path`` (string)


  The base path name that callers of the API must provide as part of the URL after the domain name. This value must be unique for all of the mappings across a single API. Leave this blank if you do not want callers to specify a base path name after the domain name.

  

``--rest-api-id`` (string)


  The string identifier of the associated  RestApi .

  

``--stage`` (string)


  The name of the API's stage that you want to use for this mapping. Leave this blank if you do not want callers to explicitly specify the stage name after any base path name.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create the base path mapping for a custom domain name**

Command::

  aws apigateway create-base-path-mapping --domain-name subdomain.domain.tld --rest-api-id 1234123412 --stage prod --base-path v1


======
Output
======

basePath -> (string)

  

  The base path name that callers of the API must provide as part of the URL after the domain name.

  

  

restApiId -> (string)

  

  The string identifier of the associated  RestApi .

  

  

stage -> (string)

  

  The name of the associated stage.

  

  

