[ :ref:`aws <cli:aws>` . :ref:`cognito-sync <cli:aws cognito-sync>` ]

.. _cli:aws cognito-sync set-identity-pool-configuration:


*******************************
set-identity-pool-configuration
*******************************



===========
Description
===========



Sets the necessary configuration for push sync.

 

This API can only be called with developer credentials. You cannot call this API with the temporary user credentials provided by Cognito Identity.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-sync-2014-06-30/SetIdentityPoolConfiguration>`_


========
Synopsis
========

::

    set-identity-pool-configuration
  --identity-pool-id <value>
  [--push-sync <value>]
  [--cognito-streams <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identity-pool-id`` (string)


  A name-spaced GUID (for example, us-east-1:23EC4050-6AEA-7089-A2DD-08002EXAMPLE) created by Amazon Cognito. This is the ID of the pool to modify.

  

``--push-sync`` (structure)


  Options to apply to this identity pool for push synchronization.

  



Shorthand Syntax::

    ApplicationArns=string,string,RoleArn=string




JSON Syntax::

  {
    "ApplicationArns": ["string", ...],
    "RoleArn": "string"
  }



``--cognito-streams`` (structure)
Options to apply to this identity pool for Amazon Cognito streams.



Shorthand Syntax::

    StreamName=string,RoleArn=string,StreamingStatus=string




JSON Syntax::

  {
    "StreamName": "string",
    "RoleArn": "string",
    "StreamingStatus": "ENABLED"|"DISABLED"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

IdentityPoolId -> (string)

  

  A name-spaced GUID (for example, us-east-1:23EC4050-6AEA-7089-A2DD-08002EXAMPLE) created by Amazon Cognito.

  

  

PushSync -> (structure)

  

  Options to apply to this identity pool for push synchronization.

  

  ApplicationArns -> (list)

    

    List of SNS platform application ARNs that could be used by clients.

    

    (string)

      

      

    

  RoleArn -> (string)

    

    A role configured to allow Cognito to call SNS on behalf of the developer.

    

    

  

CognitoStreams -> (structure)

  Options to apply to this identity pool for Amazon Cognito streams.

  StreamName -> (string)

    The name of the Cognito stream to receive updates. This stream must be in the developers account and in the same region as the identity pool.

    

  RoleArn -> (string)

    The ARN of the role Amazon Cognito can assume in order to publish to the stream. This role must grant access to Amazon Cognito (cognito-sync) to invoke PutRecord on your Cognito stream.

    

  StreamingStatus -> (string)

    Status of the Cognito streams. Valid values are: 

    ENABLED - Streaming of updates to identity pool is enabled.

     

    DISABLED - Streaming of updates to identity pool is disabled. Bulk publish will also fail if StreamingStatus is DISABLED.

    

    

  

