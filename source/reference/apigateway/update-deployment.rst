[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway update-deployment:


*****************
update-deployment
*****************



===========
Description
===========



Changes information about a  Deployment resource.



========
Synopsis
========

::

    update-deployment
  --rest-api-id <value>
  --deployment-id <value>
  [--patch-operations <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rest-api-id`` (string)


  The replacement identifier of the  RestApi resource for the  Deployment resource to change information about.

  

``--deployment-id`` (string)


  The replacment identifier for the  Deployment resource to change information about.

  

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

id -> (string)

  

  The identifier for the deployment resource.

  

  

description -> (string)

  

  The description for the deployment resource.

  

  

createdDate -> (timestamp)

  

  The date and time that the deployment resource was created.

  

  

apiSummary -> (map)

  

  Gets a summary of the  RestApi at the date and time that the deployment resource was created.

  

  key -> (string)

    

    

  value -> (map)

    

    key -> (string)

      

      

    value -> (structure)

      

      Represents a summary of a  Method resource, given a particular date and time.

      

      authorizationType -> (string)

        

        Specifies the type of authorization used for the method.

        

        

      apiKeyRequired -> (boolean)

        

        Specifies whether the method requires a valid  ApiKey .

        

        

      

    

  

