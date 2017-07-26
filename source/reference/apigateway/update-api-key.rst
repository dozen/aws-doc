[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway update-api-key:


**************
update-api-key
**************



===========
Description
===========



Changes information about an  ApiKey resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/UpdateApiKey>`_


========
Synopsis
========

::

    update-api-key
  --api-key <value>
  [--patch-operations <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--api-key`` (string)


  The identifier of the  ApiKey resource to be updated.

  

``--patch-operations`` (list)


  A list of update operations to be applied to the specified resource and in the order specified in this list.

  



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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To change the name for an API Key**

Command::

  aws apigateway update-api-key --api-key sNvjQDMReA1eEQPNAW8r37XsU2rDD7fc7m2SiMnu --patch-operations op='replace',path='/description',value='newName'

Output::

  {
      "description": "currentDescription", 
      "enabled": true, 
      "stageKeys": [
          "41t2j324r5/dev"
      ], 
      "lastUpdatedDate": 1470086052, 
      "createdDate": 1445460347, 
      "id": "sNvjQDMReA1vEQPNzW8r3dXsU2rrD7fcjm2SiMnu", 
      "name": "newName"
  }

**To disable the API Key**

Command::

  aws apigateway update-api-key --api-key sNvjQDMReA1eEQPNAW8r37XsU2rDD7fc7m2SiMnu --patch-operations op='replace',path='/enabled',value='false'

Output::

  {
      "description": "currentDescription", 
      "enabled": false, 
      "stageKeys": [
          "41t2j324r5/dev"
      ], 
      "lastUpdatedDate": 1470086052, 
      "createdDate": 1445460347, 
      "id": "sNvjQDMReA1vEQPNzW8r3dXsU2rrD7fcjm2SiMnu", 
      "name": "newName"
  }


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

    

    

  

