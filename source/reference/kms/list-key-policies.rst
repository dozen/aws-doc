[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms list-key-policies:


*****************
list-key-policies
*****************



===========
Description
===========



Retrieves a list of policies attached to a key.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kms-2014-11-01/ListKeyPolicies>`_


``list-key-policies`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``PolicyNames``


========
Synopsis
========

::

    list-key-policies
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


  A unique identifier for the customer master key (CMK). You can use the unique key ID or the Amazon Resource Name (ARN) of the CMK. Examples:

   

   
  * Unique key ID: ``1234abcd-12ab-34cd-56ef-1234567890ab``   
   
  * Key ARN: ``arn:aws:kms:us-east-2:111122223333:key/1234abcd-12ab-34cd-56ef-1234567890ab``   
   

  

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

PolicyNames -> (list)

  

  A list of policy names. Currently, there is only one policy and it is named "Default".

  

  (string)

    

    

  

NextMarker -> (string)

  

  When ``Truncated`` is true, this element is present and contains the value to use for the ``Marker`` parameter in a subsequent request.

  

  

Truncated -> (boolean)

  

  A flag that indicates whether there are more items in the list. When this value is true, the list in this response is truncated. To retrieve more items, pass the value of the ``NextMarker`` element in this response to the ``Marker`` parameter in a subsequent request.

  

  

