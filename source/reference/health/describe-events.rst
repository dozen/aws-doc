[ :ref:`aws <cli:aws>` . :ref:`health <cli:aws health>` ]

.. _cli:aws health describe-events:


***************
describe-events
***************



===========
Description
===========



Returns information about events that meet the specified filter criteria. Events are returned in a summary form and do not include the detailed description, any additional metadata that depends on the event type, or any affected resources. To retrieve that information, use the  describe-event-details and  describe-affected-entities operations.

 

If no filter criteria are specified, all events are returned. Results are sorted by ``lastModifiedTime`` , starting with the most recent.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/health-2016-08-04/DescribeEvents>`_


``describe-events`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``events``


========
Synopsis
========

::

    describe-events
  [--filter <value>]
  [--locale <value>]
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



``--locale`` (string)


  The locale (language) to return information in. English (en) is the default and the only supported value at this time.

  

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

events -> (list)

  

  The events that match the specified filter criteria.

  

  (structure)

    

    Summary information about an event, returned by the  describe-events operation. The  describe-event-details operation also returns this information, as well as the  EventDescription and additional event metadata.

    

    arn -> (string)

      

      The unique identifier for the event. Format: ``arn:aws:health:*event-region* ::event/*EVENT_TYPE_PLUS_ID* `` . Example: ``arn:aws:health:us-east-1::event/AWS_EC2_MAINTENANCE_5331``  

      

      

    service -> (string)

      

      The AWS service that is affected by the event. For example, ``EC2`` , ``RDS`` .

      

      

    eventTypeCode -> (string)

      

      The unique identifier for the event type. The format is ``AWS_*SERVICE* _*DESCRIPTION* `` ; for example, ``AWS_EC2_SYSTEM_MAINTENANCE_EVENT`` .

      

      

    eventTypeCategory -> (string)

      

      The 

      

      

    region -> (string)

      

      The AWS region name of the event.

      

      

    availabilityZone -> (string)

      

      The AWS Availability Zone of the event. For example, us-east-1a.

      

      

    startTime -> (timestamp)

      

      The date and time that the event began.

      

      

    endTime -> (timestamp)

      

      The date and time that the event ended.

      

      

    lastUpdatedTime -> (timestamp)

      

      The most recent date and time that the event was updated.

      

      

    statusCode -> (string)

      

      The most recent status of the event. Possible values are ``open`` , ``closed`` , and ``upcoming`` .

      

      

    

  

nextToken -> (string)

  

  If the results of a search are large, only a portion of the results are returned, and a ``next-token`` pagination token is returned in the response. To retrieve the next batch of results, reissue the search request and include the returned token. When all results have been returned, the response does not contain a pagination token value.

  

  

