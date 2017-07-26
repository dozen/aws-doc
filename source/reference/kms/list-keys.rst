[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms list-keys:


*********
list-keys
*********



===========
Description
===========



Lists the customer master keys.



``list-keys`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Keys``


========
Synopsis
========

::

    list-keys
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

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

Keys -> (list)

  

  A list of keys.

  

  (structure)

    

    Contains information about each entry in the key list.

    

    KeyId -> (string)

      

      Unique identifier of the key.

      

      

    KeyArn -> (string)

      

      ARN of the key.

      

      

    

  

NextMarker -> (string)

  

  When ``Truncated`` is true, this value is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  

Truncated -> (boolean)

  

  A flag that indicates whether there are more items in the list. If your results were truncated, you can use the ``Marker`` parameter to make a subsequent pagination request to retrieve more items in the list.

  

  

