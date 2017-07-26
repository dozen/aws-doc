[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs describe-subscription-filters:


*****************************
describe-subscription-filters
*****************************



===========
Description
===========



Returns all the subscription filters associated with the specified log group. The list returned in the response is ASCII-sorted by filter name. 

 

By default, this operation returns up to 50 subscription filters. If there are more subscription filters to list, the response would contain a ``nextToken`` value in the response body. You can also limit the number of subscription filters returned in the response by specifying the ``limit`` parameter in the request. 



``describe-subscription-filters`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``subscriptionFilters``


========
Synopsis
========

::

    describe-subscription-filters
  --log-group-name <value>
  [--filter-name-prefix <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--log-group-name`` (string)


  The log group name for which subscription filters are to be listed.

  

``--filter-name-prefix`` (string)


  Will only return subscription filters that match the provided filterNamePrefix. If you don't specify a value, no prefix filter is applied.

  

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



======
Output
======

subscriptionFilters -> (list)

  

  (structure)

    

    filterName -> (string)

      

      A name for a metric or subscription filter.

      

      

    logGroupName -> (string)

      

      

    filterPattern -> (string)

      

      A symbolic description of how CloudWatch Logs should interpret the data in each log event. For example, a log event may contain timestamps, IP addresses, strings, and so on. You use the filter pattern to specify what to look for in the log event message.

      

      

    destinationArn -> (string)

      

      

    roleArn -> (string)

      

      

    creationTime -> (long)

      

      A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

      

    

  

nextToken -> (string)

  

  A string token used for pagination that points to the next page of results. It must be a value obtained from the response of the previous request. The token expires after 24 hours.

  

  

