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



========
Synopsis
========

::

    delete-identities
  --identity-ids-to-delete <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--identity-ids-to-delete`` (list)


  A list of 1-60 identities that you want to delete.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

      

      

    

  

