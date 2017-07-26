[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway create-api-key:


**************
create-api-key
**************



===========
Description
===========



Create an  ApiKey resource. 

 `AWS CLI <http://docs.aws.amazon.com/cli/latest/reference/apigateway/create-api-key.html>`_ 

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/CreateApiKey>`_


========
Synopsis
========

::

    create-api-key
  [--name <value>]
  [--description <value>]
  [--enabled | --no-enabled]
  [--generate-distinct-id | --no-generate-distinct-id]
  [--value <value>]
  [--stage-keys <value>]
  [--customer-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the  ApiKey .

  

``--description`` (string)


  The description of the  ApiKey .

  

``--enabled`` | ``--no-enabled`` (boolean)


  Specifies whether the  ApiKey can be used by callers.

  

``--generate-distinct-id`` | ``--no-generate-distinct-id`` (boolean)


  Specifies whether (``true`` ) or not (``false`` ) the key identifier is distinct from the created API key value.

  

``--value`` (string)


  Specifies a value of the API key.

  

``--stage-keys`` (list)


  DEPRECATED FOR USAGE PLANS - Specifies stages associated with the API key.

  



Shorthand Syntax::

    restApiId=string,stageName=string ...




JSON Syntax::

  [
    {
      "restApiId": "string",
      "stageName": "string"
    }
    ...
  ]



``--customer-id`` (string)


  An AWS Marketplace customer identifier , when integrating with the AWS SaaS Marketplace.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create an API key that is enabled for an existing API and Stage**

Command::

  aws apigateway create-api-key --name 'Dev API Key' --description 'Used for development' --enabled --stage-keys restApiId='a1b2c3d4e5',stageName='dev'


======
Output
======

id -> (string)

  

  The identifier of the API Key.

  

  

value -> (string)

  

  The value of the API Key.

  

  

name -> (string)

  

  The name of the API Key.

  

  

customerId -> (string)

  

  An AWS Marketplace customer identifier , when integrating with the AWS SaaS Marketplace.

  

  

description -> (string)

  

  The description of the API Key.

  

  

enabled -> (boolean)

  

  Specifies whether the API Key can be used by callers.

  

  

createdDate -> (timestamp)

  

  The timestamp when the API Key was created.

  

  

lastUpdatedDate -> (timestamp)

  

  The timestamp when the API Key was last updated.

  

  

stageKeys -> (list)

  

  A list of  Stage resources that are associated with the  ApiKey resource.

  

  (string)

    

    

  

