[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms create-grant:


************
create-grant
************



===========
Description
===========



Adds a grant to a key to specify who can use the key and under what conditions. Grants are alternate permission mechanisms to key policies.

 

For more information about grants, see `Grants`_ in the *AWS Key Management Service Developer Guide* .



========
Synopsis
========

::

    create-grant
  --key-id <value>
  --grantee-principal <value>
  [--retiring-principal <value>]
  [--operations <value>]
  [--constraints <value>]
  [--grant-tokens <value>]
  [--name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--key-id`` (string)


  The unique identifier for the customer master key (CMK) that the grant applies to.

   

  To specify this value, use the globally unique key ID or the Amazon Resource Name (ARN) of the key. Examples: 

   
  * Globally unique key ID: 12345678-1234-1234-1234-123456789012
   
  * Key ARN: arn:aws:kms:us-west-2:123456789012:key/12345678-1234-1234-1234-123456789012
   

   

  

``--grantee-principal`` (string)


  The principal that is given permission to perform the operations that the grant permits.

   

  To specify the principal, use the `Amazon Resource Name (ARN)`_ of an AWS principal. Valid AWS principals include AWS accounts (root), IAM users, federated users, and assumed role users. For examples of the ARN syntax to use for specifying a principal, see `AWS Identity and Access Management (IAM)`_ in the Example ARNs section of the *AWS General Reference* .

  

``--retiring-principal`` (string)


  The principal that is given permission to retire the grant by using  RetireGrant operation.

   

  To specify the principal, use the `Amazon Resource Name (ARN)`_ of an AWS principal. Valid AWS principals include AWS accounts (root), IAM users, federated users, and assumed role users. For examples of the ARN syntax to use for specifying a principal, see `AWS Identity and Access Management (IAM)`_ in the Example ARNs section of the *AWS General Reference* .

  

``--operations`` (list)


  A list of operations that the grant permits. The list can contain any combination of one or more of the following values: 

   
  * Decrypt
   
  * Encrypt
   
  * GenerateDataKey
   
  * GenerateDataKeyWithoutPlaintext
   
  * ReEncryptFrom
   
  * ReEncryptTo
   
  * CreateGrant
   
  * RetireGrant
   

   

  



Syntax::

  "string" "string" ...

  Where valid values are:
    Decrypt
    Encrypt
    GenerateDataKey
    GenerateDataKeyWithoutPlaintext
    ReEncryptFrom
    ReEncryptTo
    CreateGrant
    RetireGrant
    DescribeKey





``--constraints`` (structure)


  The conditions under which the operations permitted by the grant are allowed.

   

  You can use this value to allow the operations permitted by the grant only when a specified encryption context is present. For more information, see `Encryption Context`_ in the *AWS Key Management Service Developer Guide* .

  



Shorthand Syntax::

    EncryptionContextSubset={KeyName1=string,KeyName2=string},EncryptionContextEquals={KeyName1=string,KeyName2=string}




JSON Syntax::

  {
    "EncryptionContextSubset": {"string": "string"
      ...},
    "EncryptionContextEquals": {"string": "string"
      ...}
  }



``--grant-tokens`` (list)


  A list of grant tokens.

   

  For more information, go to `Grant Tokens`_ in the *AWS Key Management Service Developer Guide* .

  



Syntax::

  "string" "string" ...



``--name`` (string)


  A friendly name for identifying the grant. Use this value to prevent unintended creation of duplicate grants when retrying this request.

   

  When this value is absent, all ``CreateGrant`` requests result in a new grant with a unique ``GrantId`` even if all the supplied parameters are identical. This can result in unintended duplicates when you retry the ``CreateGrant`` request.

   

  When this value is present, you can retry a ``CreateGrant`` request with identical parameters; if the grant already exists, the original ``GrantId`` is returned without creating a new grant. Note that the returned grant token is unique with every ``CreateGrant`` request, even when a duplicate ``GrantId`` is returned. All grant tokens obtained in this way can be used interchangeably.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

GrantToken -> (string)

  

  The grant token.

   

  For more information about using grant tokens, see `Grant Tokens`_ in the *AWS Key Management Service Developer Guide* . 

  

  

GrantId -> (string)

  

  The unique identifier for the grant.

   

  You can use the ``GrantId`` in a subsequent  RetireGrant or  RevokeGrant operation.

  

  



.. _Grant Tokens: http://docs.aws.amazon.com/kms/latest/developerguide/concepts.html#grant_token
.. _Encryption Context: http://docs.aws.amazon.com/kms/latest/developerguide/encrypt-context.html
.. _Grants: http://docs.aws.amazon.com/kms/latest/developerguide/grants.html
.. _AWS Identity and Access Management (IAM): http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html#arn-syntax-iam
.. _Amazon Resource Name (ARN): http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html
