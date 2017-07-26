[ :ref:`aws <cli:aws>` . :ref:`cognito-identity <cli:aws cognito-identity>` ]

.. _cli:aws cognito-identity list-identity-pools:


*******************
list-identity-pools
*******************



===========
Description
===========



Lists all of the Cognito identity pools registered for your account.

 

You must use AWS Developer credentials to call this API.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-identity-2014-06-30/ListIdentityPools>`_


========
Synopsis
========

::

    list-identity-pools
  --max-results <value>
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--max-results`` (integer)


  The maximum number of identities to return.

  

``--next-token`` (string)


  A pagination token.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

IdentityPools -> (list)

  

  The identity pools returned by the list-identity-pools action.

  

  (structure)

    

    A description of the identity pool.

    

    IdentityPoolId -> (string)

      

      An identity pool ID in the format REGION:GUID.

      

      

    IdentityPoolName -> (string)

      

      A string that you provide.

      

      

    

  

NextToken -> (string)

  

  A pagination token.

  

  

