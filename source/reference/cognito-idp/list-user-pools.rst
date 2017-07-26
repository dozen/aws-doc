[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp list-user-pools:


***************
list-user-pools
***************



===========
Description
===========



Lists the user pools associated with an AWS account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/ListUserPools>`_


========
Synopsis
========

::

    list-user-pools
  [--next-token <value>]
  --max-results <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-token`` (string)


  An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

  

``--max-results`` (integer)


  The maximum number of results you want the request to return when listing the user pools.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

UserPools -> (list)

  

  The user pools from the response to list users.

  

  (structure)

    

    A user pool description.

    

    Id -> (string)

      

      The ID in a user pool description.

      

      

    Name -> (string)

      

      The name in a user pool description.

      

      

    LambdaConfig -> (structure)

      

      The AWS Lambda configuration information in a user pool description.

      

      PreSignUp -> (string)

        

        A pre-registration AWS Lambda trigger.

        

        

      CustomMessage -> (string)

        

        A custom Message AWS Lambda trigger.

        

        

      PostConfirmation -> (string)

        

        A post-confirmation AWS Lambda trigger.

        

        

      PreAuthentication -> (string)

        

        A pre-authentication AWS Lambda trigger.

        

        

      PostAuthentication -> (string)

        

        A post-authentication AWS Lambda trigger.

        

        

      DefineAuthChallenge -> (string)

        

        Defines the authentication challenge.

        

        

      CreateAuthChallenge -> (string)

        

        Creates an authentication challenge.

        

        

      VerifyAuthChallengeResponse -> (string)

        

        Verifies the authentication challenge response.

        

        

      

    Status -> (string)

      

      The user pool status in a user pool description.

      

      

    LastModifiedDate -> (timestamp)

      

      The date the user pool description was last modified.

      

      

    CreationDate -> (timestamp)

      

      The date the user pool description was created.

      

      

    

  

NextToken -> (string)

  

  An identifier that was returned from the previous call to this operation, which can be used to return the next set of items in the list.

  

  

