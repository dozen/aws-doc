[ :ref:`aws <cli:aws>` . :ref:`health <cli:aws health>` ]

.. _cli:aws health describe-event-details:


**********************
describe-event-details
**********************



===========
Description
===========



Returns detailed information about one or more specified events. Information includes standard event data (region, service, etc., as returned by  describe-events ), a detailed event description, and possible additional metadata that depends upon the nature of the event. Affected entities are not included; to retrieve those, use the  describe-affected-entities operation.

 

If a specified event cannot be retrieved, an error message is returned for that event.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/health-2016-08-04/DescribeEventDetails>`_


========
Synopsis
========

::

    describe-event-details
  --event-arns <value>
  [--locale <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--event-arns`` (list)


  A list of event ARNs (unique identifiers). For example: ``"arn:aws:health:us-east-1::event/AWS_EC2_MAINTENANCE_5331", "arn:aws:health:us-west-1::event/AWS_EBS_LOST_VOLUME_xyz"``  

  



Syntax::

  "string" "string" ...



``--locale`` (string)


  The locale (language) to return information in. English (en) is the default and the only supported value at this time.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

successfulSet -> (list)

  

  Information about the events that could be retrieved.

  

  (structure)

    

    Detailed information about an event. A combination of an  Event object, an  EventDescription object, and additional metadata about the event. Returned by the  describe-event-details operation.

    

    event -> (structure)

      

      Summary information about the event.

      

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

        

        

      

    eventDescription -> (structure)

      

      The most recent description of the event.

      

      latestDescription -> (string)

        

        The most recent description of the event.

        

        

      

    eventMetadata -> (map)

      

      Additional metadata about the event.

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    

  

failedSet -> (list)

  

  Error messages for any events that could not be retrieved.

  

  (structure)

    

    Error information returned when a  describe-event-details operation cannot find a specified event.

    

    eventArn -> (string)

      

      The unique identifier for the event. Format: ``arn:aws:health:*event-region* ::event/*EVENT_TYPE_PLUS_ID* `` . Example: ``arn:aws:health:us-east-1::event/AWS_EC2_MAINTENANCE_5331``  

      

      

    errorName -> (string)

      

      The name of the error.

      

      

    errorMessage -> (string)

      

      A message that describes the error.

      

      

    

  

