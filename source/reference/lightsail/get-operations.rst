[ :ref:`aws <cli:aws>` . :ref:`lightsail <cli:aws lightsail>` ]

.. _cli:aws lightsail get-operations:


**************
get-operations
**************



===========
Description
===========



Returns information about all operations.

 

Results are returned from oldest to newest, up to a maximum of 200. Results can be paged by making each subsequent call to ``get-operations`` use the maximum (last) ``statusChangedAt`` value from the previous request.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/lightsail-2016-11-28/GetOperations>`_


``get-operations`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``operations``


========
Synopsis
========

::

    get-operations
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON page-token provided. The JSON page-token follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

operations -> (list)

  

  An array of key-value pairs containing information about the results of your get operations request.

  

  (structure)

    

    Describes the API operation.

    

    id -> (string)

      

      The ID of the operation.

      

      

    resourceName -> (string)

      

      The resource name.

      

      

    resourceType -> (string)

      

      The resource type. 

      

      

    createdAt -> (timestamp)

      

      The timestamp when the operation was initialized (e.g., ``1479816991.349`` ).

      

      

    location -> (structure)

      

      The region and Availability Zone.

      

      availabilityZone -> (string)

        

        The Availability Zone. Follows the format ``us-east-1a`` (case-sensitive).

        

        

      regionName -> (string)

        

        The AWS Region name.

        

        

      

    isTerminal -> (boolean)

      

      A Boolean value indicating whether the operation is terminal.

      

      

    operationDetails -> (string)

      

      Details about the operation (e.g., ``Debian-1GB-Virginia-1`` ).

      

      

    operationType -> (string)

      

      The type of operation. 

      

      

    status -> (string)

      

      The status of the operation. 

      

      

    statusChangedAt -> (timestamp)

      

      The timestamp when the status was changed (e.g., ``1479816991.349`` ).

      

      

    errorCode -> (string)

      

      The error code.

      

      

    errorDetails -> (string)

      

      The error details.

      

      

    

  

nextPageToken -> (string)

  

  A token used for advancing to the next page of results from your get operations request.

  

  

