[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms list-grants:


***********
list-grants
***********



===========
Description
===========



List the grants for a specified key.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kms-2014-11-01/ListGrants>`_


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
  [--generate-cli-skeleton <value>]




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

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

      

      A list of key-value pairs that must be present in the encryption context of certain subsequent operations that the grant allows.

      

      EncryptionContextSubset -> (map)

        

        A list of key-value pairs, all of which must be present in the encryption context of certain subsequent operations that the grant allows. When certain subsequent operations allowed by the grant include encryption context that matches this list or is a superset of this list, the grant allows the operation. Otherwise, the grant does not allow the operation.

        

        key -> (string)

          

          

        value -> (string)

          

          

        

      EncryptionContextEquals -> (map)

        

        A list of key-value pairs that must be present in the encryption context of certain subsequent operations that the grant allows. When certain subsequent operations allowed by the grant include encryption context that matches this list, the grant allows the operation. Otherwise, the grant does not allow the operation.

        

        key -> (string)

          

          

        value -> (string)

          

          

        

      

    

  

NextMarker -> (string)

  

  When ``Truncated`` is true, this element is present and contains the value to use for the ``Marker`` parameter in a subsequent request.

  

  

Truncated -> (boolean)

  

  A flag that indicates whether there are more items in the list. When this value is true, the list in this response is truncated. To retrieve more items, pass the value of the ``NextMarker`` element in this response to the ``Marker`` parameter in a subsequent request.

  

  

