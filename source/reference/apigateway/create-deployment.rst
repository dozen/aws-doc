[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway create-deployment:


*****************
create-deployment
*****************



===========
Description
===========



Creates a  Deployment resource, which makes a specified  RestApi callable over the internet.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/CreateDeployment>`_


========
Synopsis
========

::

    create-deployment
  --rest-api-id <value>
  [--stage-name <value>]
  [--stage-description <value>]
  [--description <value>]
  [--cache-cluster-enabled | --no-cache-cluster-enabled]
  [--cache-cluster-size <value>]
  [--variables <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  The string identifier of the associated  RestApi .

  

``--stage-name`` (string)


  The name of the  Stage resource for the  Deployment resource to create.

  

``--stage-description`` (string)


  The description of the  Stage resource for the  Deployment resource to create.

  

``--description`` (string)


  The description for the  Deployment resource to create.

  

``--cache-cluster-enabled`` | ``--no-cache-cluster-enabled`` (boolean)


  Enables a cache cluster for the  Stage resource specified in the input.

  

``--cache-cluster-size`` (string)


  Specifies the cache cluster size for the  Stage resource specified in the input, if a cache cluster is enabled.

  

  Possible values:

  
  *   ``0.5``

  
  *   ``1.6``

  
  *   ``6.1``

  
  *   ``13.5``

  
  *   ``28.4``

  
  *   ``58.2``

  
  *   ``118``

  
  *   ``237``

  

  

``--variables`` (map)


  A map that defines the stage variables for the  Stage resource that is associated with the new deployment. Variable names can have alphanumeric and underscore characters, and the values must match ``[A-Za-z0-9-._~:/?#=,]+`` .

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To deploy the configured resources for an API to a new Stage**

Command::

  aws apigateway create-deployment --rest-api-id 1234123412 --stage-name dev --stage-description 'Development Stage' --description 'First deployment to the dev stage'

**To deploy the configured resources for an API to an existing stage**

Command::

  aws apigateway create-deployment --rest-api-id 1234123412 --stage-name dev --description 'Second deployment to the dev stage'

**To deploy the configured resources for an API to an existing stage with Stage Variables**

  aws apigateway create-deployment --rest-api-id 1234123412 --stage-name dev --description 'Third deployment to the dev stage' --variables key='value',otherKey='otherValue'



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

        

        

      

    

  

