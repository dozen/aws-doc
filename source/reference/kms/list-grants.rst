[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms list-grants:


***********
list-grants
***********



===========
Description
===========



List the grants for a specified key.



``list-grants`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Grants``


========
Synopsis
========

::

    list-grants
  --key-id <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--key-id`` (string)


  A unique identifier for the customer master key. This value can be a globally unique identifier or the fully specified ARN to a key. 

   
  * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012
   
  * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012
   

   

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

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

  

  

