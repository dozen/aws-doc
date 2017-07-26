[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs describe-destinations:


*********************
describe-destinations
*********************



===========
Description
===========



Lists all your destinations. The results are ASCII-sorted by destination name.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/logs-2014-03-28/DescribeDestinations>`_


``describe-destinations`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``destinations``


========
Synopsis
========

::

    describe-destinations
  [--destination-name-prefix <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--destination-name-prefix`` (string)


  The prefix to match. If you don't specify a value, no prefix filter is applied.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

destinations -> (list)

  

  The destinations.

  

  (structure)

    

    Represents a cross-account destination that receives subscription log events.

    

    destinationName -> (string)

      

      The name of the destination.

      

      

    targetArn -> (string)

      

      The Amazon Resource Name (ARN) of the physical target where the log events will be delivered (for example, a Kinesis stream).

      

      

    roleArn -> (string)

      

      A role for impersonation, used when delivering log events to the target.

      

      

    accessPolicy -> (string)

      

      An IAM policy document that governs which AWS accounts can create subscription filters against this destination.

      

      

    arn -> (string)

      

      The ARN of this destination.

      

      

    creationTime -> (long)

      

      The creation time of the destination, expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

      

    

  

nextToken -> (string)

  

  The token for the next set of items to return. The token expires after 24 hours.

  

  

