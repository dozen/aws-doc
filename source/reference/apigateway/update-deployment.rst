[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway update-deployment:


*****************
update-deployment
*****************



===========
Description
===========



Changes information about a  Deployment resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/UpdateDeployment>`_


========
Synopsis
========

::

    update-deployment
  --rest-api-id <value>
  --deployment-id <value>
  [--patch-operations <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  The string identifier of the associated  RestApi .

  

``--deployment-id`` (string)


  The replacement identifier for the  Deployment resource to change information about.

  

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

**To change the description of a deployment**

Command::

  aws apigateway update-deployment --rest-api-id 1234123412 --deployment-id ztt4m2 --patch-operations op='replace',path='/description',value='newDescription'

Output::

  {
      "description": "newDescription", 
      "id": "ztt4m2", 
      "createdDate": 1455218022
  }



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

  

  A summary of the  RestApi at the date and time that the deployment resource was created.

  

  key -> (string)

    

    

  value -> (map)

    

    key -> (string)

      

      

    value -> (structure)

      

      Represents a summary of a  Method resource, given a particular date and time.

      

      authorizationType -> (string)

        

        The method's authorization type. Valid values are ``NONE`` for open access, ``AWS_IAM`` for using AWS IAM permissions, ``CUSTOM`` for using a custom authorizer, or ``COGNITO_USER_POOLS`` for using a Cognito user pool.

        

        

      apiKeyRequired -> (boolean)

        

        Specifies whether the method requires a valid  ApiKey .

        

        

      

    

  

