[ :ref:`aws <cli:aws>` . :ref:`cognito-identity <cli:aws cognito-identity>` ]

.. _cli:aws cognito-identity list-identities:


***************
list-identities
***************



===========
Description
===========



Lists the identities in a pool.

 

You must use AWS Developer credentials to call this API.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-identity-2014-06-30/ListIdentities>`_


========
Synopsis
========

::

    list-identities
  --identity-pool-id <value>
  --max-results <value>
  [--next-token <value>]
  [--hide-disabled | --no-hide-disabled]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identity-pool-id`` (string)


  An identity pool ID in the format REGION:GUID.

  

``--max-results`` (integer)


  The maximum number of identities to return.

  

``--next-token`` (string)


  A pagination token.

  

``--hide-disabled`` | ``--no-hide-disabled`` (boolean)


  An optional boolean parameter that allows you to hide disabled identities. If omitted, the list-identities API will include disabled identities in the response.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

IdentityPoolId -> (string)

  

  An identity pool ID in the format REGION:GUID.

  

  

Identities -> (list)

  

  An object containing a set of identities and associated mappings.

  

  (structure)

    

    A description of the identity.

    

    IdentityId -> (string)

      

      A unique identifier in the format REGION:GUID.

      

      

    Logins -> (list)

      

      A set of optional name-value pairs that map provider names to provider tokens.

      

      (string)

        

        

      

    CreationDate -> (timestamp)

      

      Date on which the identity was created.

      

      

    LastModifiedDate -> (timestamp)

      

      Date on which the identity was last modified.

      

      

    

  

NextToken -> (string)

  

  A pagination token.

  

  

