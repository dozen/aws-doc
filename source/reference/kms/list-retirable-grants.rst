[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms list-retirable-grants:


*********************
list-retirable-grants
*********************



===========
Description
===========



Returns a list of all grants for which the grant's ``RetiringPrincipal`` matches the one specified.

 

A typical use is to list all grants that you are able to retire. To retire a grant, use  retire-grant .



========
Synopsis
========

::

    list-retirable-grants
  [--limit <value>]
  [--marker <value>]
  --retiring-principal <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--limit`` (integer)


  When paginating results, specify the maximum number of items to return in the response. If additional items exist beyond the number you specify, the ``Truncated`` element in the response is set to true.

  

  This value is optional. If you include a value, it must be between 1 and 100, inclusive. If you do not include a value, it defaults to 50.

  

``--marker`` (string)


  Use this parameter only when paginating results and only in a subsequent request after you've received a response with truncated results. Set it to the value of ``NextMarker`` from the response you just received.

  

``--retiring-principal`` (string)


  The retiring principal for which to list grants.

   

  To specify the retiring principal, use the `Amazon Resource Name (ARN)`_ of an AWS principal. Valid AWS principals include AWS accounts (root), IAM users, federated users, and assumed role users. For examples of the ARN syntax for specifying a principal, go to `AWS Identity and Access Management (IAM)`_ in the Example ARNs section of the *Amazon Web Services General Reference* .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Grants -> (list)

  

  A list of grants.

  

  (structure)

    

    Contains information about an entry in a list of grants.

    

    KeyId -> (string)

      

      The unique identifier for the customer master key (CMK) to which the grant applies.

      

      

    GrantId -> (string)

      

      The unique identifier for the grant.

      

      

    Name -> (string)

      

      The friendly name that identifies the grant. If a name was provided in the  create-grant request, that name is returned. Otherwise this value is null.

      

      

    CreationDate -> (timestamp)

      

      The date and time when the grant was created.

      

      

    GranteePrincipal -> (string)

      

      The principal that receives the grant's permissions.

      

      

    RetiringPrincipal -> (string)

      

      The principal that can retire the grant.

      

      

    IssuingAccount -> (string)

      

      The AWS account under which the grant was issued.

      

      

    Operations -> (list)

      

      The list of operations permitted by the grant.

      

      (string)

        

        

      

    Constraints -> (structure)

      

      The conditions under which the grant's operations are allowed.

      

      EncryptionContextSubset -> (map)

        

        Contains a list of key-value pairs, a subset of which must be present in the encryption context of a subsequent operation permitted by the grant. When a subsequent operation permitted by the grant includes an encryption context that matches this list or is a subset of this list, the grant allows the operation. Otherwise, the operation is not allowed.

        

        key -> (string)

          

          

        value -> (string)

          

          

        

      EncryptionContextEquals -> (map)

        

        Contains a list of key-value pairs that must be present in the encryption context of a subsequent operation permitted by the grant. When a subsequent operation permitted by the grant includes an encryption context that matches this list, the grant allows the operation. Otherwise, the operation is not allowed.

        

        key -> (string)

          

          

        value -> (string)

          

          

        

      

    

  

NextMarker -> (string)

  

  When ``Truncated`` is true, this value is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  

Truncated -> (boolean)

  

  A flag that indicates whether there are more items in the list. If your results were truncated, you can use the ``Marker`` parameter to make a subsequent pagination request to retrieve more items in the list.

  

  



.. _AWS Identity and Access Management (IAM): http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html#arn-syntax-iam
.. _Amazon Resource Name (ARN): http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html
