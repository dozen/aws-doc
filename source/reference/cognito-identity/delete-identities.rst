[ :ref:`aws <cli:aws>` . :ref:`cognito-identity <cli:aws cognito-identity>` ]

.. _cli:aws cognito-identity delete-identities:


*****************
delete-identities
*****************



===========
Description
===========



Deletes identities from an identity pool. You can specify a list of 1-60 identities that you want to delete.

 

You must use AWS Developer credentials to call this API.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-identity-2014-06-30/DeleteIdentities>`_


========
Synopsis
========

::

    delete-identities
  --identity-ids-to-delete <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--identity-ids-to-delete`` (list)


  A list of 1-60 identities that you want to delete.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

UnprocessedIdentityIds -> (list)

  

  An array of UnprocessedIdentityId objects, each of which contains an ErrorCode and IdentityId.

  

  (structure)

    

    An array of UnprocessedIdentityId objects, each of which contains an ErrorCode and IdentityId.

    

    IdentityId -> (string)

      

      A unique identifier in the format REGION:GUID.

      

      

    ErrorCode -> (string)

      

      The error code indicating the type of error that occurred.

      

      

    

  

