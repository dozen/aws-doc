[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs describe-log-groups:


*******************
describe-log-groups
*******************



===========
Description
===========



Returns all the log groups that are associated with the AWS account making the request. The list returned in the response is ASCII-sorted by log group name. 

 

By default, this operation returns up to 50 log groups. If there are more log groups to list, the response would contain a ``nextToken`` value in the response body. You can also limit the number of log groups returned in the response by specifying the ``limit`` parameter in the request. 



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
  [--generate-cli-skeleton]




=======
Options
=======

``--log-group-name-prefix`` (string)


  Will only return log groups that match the provided logGroupNamePrefix. If you don't specify a value, no prefix filter is applied.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``next-token`` will be provided in the output that you can use to resume pagination. This ``next-token`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  A list of log groups.

  

  (structure)

    

    logGroupName -> (string)

      

      

    creationTime -> (long)

      

      A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

      

    retentionInDays -> (integer)

      

      Specifies the number of days you want to retain log events in the specified log group. Possible values are: 1, 3, 5, 7, 14, 30, 60, 90, 120, 150, 180, 365, 400, 545, 731, 1827, 3653.

      

      

    metricFilterCount -> (integer)

      

      The number of metric filters associated with the log group.

      

      

    arn -> (string)

      

      

    storedBytes -> (long)

      

      

    

  

nextToken -> (string)

  

  A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous request. The token expires after 24 hours.

  

  

