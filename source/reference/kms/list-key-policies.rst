[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms list-key-policies:


*****************
list-key-policies
*****************



===========
Description
===========



Retrieves a list of policies attached to a key.



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
  [--generate-cli-skeleton]




=======
Options
=======

``--key-id`` (string)


  A unique identifier for the customer master key. This value can be a globally unique identifier, a fully specified ARN to either an alias or a key, or an alias name prefixed by "alias/". 

   
  * Key ARN Example - arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012
   
  * Alias ARN Example - arn:aws:kms:us-east-1:123456789012:alias/MyAliasName
   
  * Globally Unique Key ID Example - 12345678-1234-1234-1234-123456789012
   
  * Alias Name Example - alias/MyAliasName
   

   

  

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

PolicyNames -> (list)

  

  A list of policy names. Currently, there is only one policy and it is named "Default".

  

  (string)

    

    

  

NextMarker -> (string)

  

  When ``Truncated`` is true, this value is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  

Truncated -> (boolean)

  

  A flag that indicates whether there are more items in the list. If your results were truncated, you can use the ``Marker`` parameter to make a subsequent pagination request to retrieve more items in the list.

  

  

