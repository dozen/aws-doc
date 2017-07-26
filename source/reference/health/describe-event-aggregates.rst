[ :ref:`aws <cli:aws>` . :ref:`health <cli:aws health>` ]

.. _cli:aws health describe-event-aggregates:


*************************
describe-event-aggregates
*************************



===========
Description
===========



Returns the number of events of each event type (issue, scheduled change, and account notification). If no filter is specified, the counts of all events in each category are returned.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/health-2016-08-04/DescribeEventAggregates>`_


``describe-event-aggregates`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``eventAggregates``


========
Synopsis
========

::

    describe-event-aggregates
  [--filter <value>]
  --aggregate-field <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filter`` (structure)


  Values to narrow the results returned.

  



Shorthand Syntax::

    eventArns=string,string,eventTypeCodes=string,string,services=string,string,regions=string,string,availabilityZones=string,string,startTimes=[{from=timestamp,to=timestamp},{from=timestamp,to=timestamp}],endTimes=[{from=timestamp,to=timestamp},{from=timestamp,to=timestamp}],lastUpdatedTimes=[{from=timestamp,to=timestamp},{from=timestamp,to=timestamp}],entityArns=string,string,entityValues=string,string,eventTypeCategories=string,string,tags=[{KeyName1=string,KeyName2=string},{KeyName1=string,KeyName2=string}],eventStatusCodes=string,string




JSON Syntax::

  {
    "eventArns": ["string", ...],
    "eventTypeCodes": ["string", ...],
    "services": ["string", ...],
    "regions": ["string", ...],
    "availabilityZones": ["string", ...],
    "startTimes": [
      {
        "from": timestamp,
        "to": timestamp
      }
      ...
    ],
    "endTimes": [
      {
        "from": timestamp,
        "to": timestamp
      }
      ...
    ],
    "lastUpdatedTimes": [
      {
        "from": timestamp,
        "to": timestamp
      }
      ...
    ],
    "entityArns": ["string", ...],
    "entityValues": ["string", ...],
    "eventTypeCategories": ["issue"|"accountNotification"|"scheduledChange", ...],
    "tags": [
      {"string": "string"
        ...}
      ...
    ],
    "eventStatusCodes": ["open"|"closed"|"upcoming", ...]
  }



``--aggregate-field`` (string)


  The only currently supported value is ``eventTypeCategory`` .

  

  Possible values:

  
  *   ``eventTypeCategory``

  

  

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

eventAggregates -> (list)

  

  The number of events in each category that meet the optional filter criteria.

  

  (structure)

    

    The number of events of each issue type. Returned by the  describe-event-aggregates operation.

    

    aggregateValue -> (string)

      

      The issue type for the associated count.

      

      

    count -> (integer)

      

      The number of events of the associated issue type.

      

      

    

  

nextToken -> (string)

  

  If the results of a search are large, only a portion of the results are returned, and a ``next-token`` pagination token is returned in the response. To retrieve the next batch of results, reissue the search request and include the returned token. When all results have been returned, the response does not contain a pagination token value.

  

  

