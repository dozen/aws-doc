[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs describe-log-groups:


*******************
describe-log-groups
*******************



===========
Description
===========



Lists the specified log groups. You can list all your log groups or filter the results by prefix. The results are ASCII-sorted by log group name.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/logs-2014-03-28/DescribeLogGroups>`_


``describe-log-groups`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``logGroups``


========
Synopsis
========

::

    describe-log-groups
  [--log-group-name-prefix <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--log-group-name-prefix`` (string)


  The prefix to match.

  

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



========
Examples
========

The following command describes a log group named ``my-logs``::

  aws logs describe-log-groups --log-group-name-prefix my-logs

Output::

  {
      "logGroups": [
          {
              "storedBytes": 0,
              "metricFilterCount": 0,
              "creationTime": 1433189500783,
              "logGroupName": "my-logs",
              "retentionInDays": 5,
              "arn": "arn:aws:logs:us-west-2:0123456789012:log-group:my-logs:*"
          }
      ]
  }


======
Output
======

logGroups -> (list)

  

  The log groups.

  

  (structure)

    

    Represents a log group.

    

    logGroupName -> (string)

      

      The name of the log group.

      

      

    creationTime -> (long)

      

      The creation time of the log group, expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

      

    retentionInDays -> (integer)

      

      The number of days to retain the log events in the specified log group. Possible values are: 1, 3, 5, 7, 14, 30, 60, 90, 120, 150, 180, 365, 400, 545, 731, 1827, and 3653.

      

      

    metricFilterCount -> (integer)

      

      The number of metric filters.

      

      

    arn -> (string)

      

      The Amazon Resource Name (ARN) of the log group.

      

      

    storedBytes -> (long)

      

      The number of bytes stored.

      

      

    

  

nextToken -> (string)

  

  The token for the next set of items to return. The token expires after 24 hours.

  

  

