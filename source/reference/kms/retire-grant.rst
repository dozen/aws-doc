[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms retire-grant:


************
retire-grant
************



===========
Description
===========



Retires a grant. You can retire a grant when you're done using it to clean up. You should revoke a grant when you intend to actively deny operations that depend on it. The following are permitted to call this API: 

 
* The account that created the grant
 
* The ``RetiringPrincipal`` , if present
 
* The ``GranteePrincipal`` , if ``retire-grant`` is a grantee operation
 

The grant to retire must be identified by its grant token or by a combination of the key ARN and the grant ID. A grant token is a unique variable-length base64-encoded string. A grant ID is a 64 character unique identifier of a grant. Both are returned by the ``create-grant`` function. 



========
Synopsis
========

::

    retire-grant
  [--grant-token <value>]
  [--key-id <value>]
  [--grant-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--grant-token`` (string)


  Token that identifies the grant to be retired.

  

``--key-id`` (string)


  A unique identifier for the customer master key associated with the grant. This value can be a globally unique identifier or a fully specified ARN of the key. 

   
  * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012
   
  * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012
   

   

  

``--grant-id`` (string)


  Unique identifier of the grant to be retired. The grant ID is returned by the ``create-grant`` function. 

   
  * Grant ID Example - 0123456789012345678901234567890123456789012345678901234567890123
   

   

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None