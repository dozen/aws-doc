[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains list-operations:


***************
list-operations
***************



===========
Description
===========



This operation returns the operation IDs of operations that are not yet complete.



``list-operations`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Operations``


========
Synopsis
========

::

    list-operations
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Operations -> (list)

  

  Lists summaries of the operations.

   

  Type: Complex type containing a list of operation summaries

   

  Children: ``OperationId`` , ``Status`` , ``SubmittedDate`` , ``Type`` 

  

  (structure)

    

    OperationSummary includes the following elements.

    

    OperationId -> (string)

      

      Identifier returned to track the requested action.

       

      Type: String

      

      

    Status -> (string)

      

      The current status of the requested operation in the system.

       

      Type: String

      

      

    Type -> (string)

      

      Type of the action requested.

       

      Type: String

       

      Valid values: ``REGISTER_DOMAIN`` | ``DELETE_DOMAIN`` | ``TRANSFER_IN_DOMAIN`` | ``UPDATE_DOMAIN_CONTACT`` | ``UPDATE_NAMESERVER`` | ``CHANGE_PRIVACY_PROTECTION`` | ``DOMAIN_LOCK`` 

      

      

    SubmittedDate -> (timestamp)

      

      The date when the request was submitted.

      

      

    

  

NextPageMarker -> (string)

  

  If there are more operations than you specified for ``MaxItems`` in the request, submit another request and include the value of ``NextPageMarker`` in the value of ``Marker`` .

   

  Type: String

   

  Parent: ``Operations`` 

  

  

