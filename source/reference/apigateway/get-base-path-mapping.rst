[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-base-path-mapping:


*********************
get-base-path-mapping
*********************



===========
Description
===========



Describe a  BasePathMapping resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/GetBasePathMapping>`_


========
Synopsis
========

::

    get-base-path-mapping
  --domain-name <value>
  --base-path <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  The domain name of the  BasePathMapping resource to be described.

  

``--base-path`` (string)


  The base path name that callers of the API must provide as part of the URL after the domain name. This value must be unique for all of the mappings across a single API. Leave this blank if you do not want callers to specify any base path name after the domain name.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get the base path mapping for a custom domain name**

Command::

  aws apigateway get-base-path-mapping --domain-name subdomain.domain.tld --base-path v1

Output::

  {
      "basePath": "v1", 
      "restApiId": "1234w4321e", 
      "stage": "api"
  }


======
Output
======

basePath -> (string)

  

  The base path name that callers of the API must provide as part of the URL after the domain name.

  

  

restApiId -> (string)

  

  The string identifier of the associated  RestApi .

  

  

stage -> (string)

  

  The name of the associated stage.

  

  

