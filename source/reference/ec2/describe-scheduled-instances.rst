[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-scheduled-instances:


****************************
describe-scheduled-instances
****************************



===========
Description
===========



Describes one or more of your Scheduled Instances.



========
Synopsis
========

::

    describe-scheduled-instances
  [--dry-run | --no-dry-run]
  [--scheduled-instance-ids <value>]
  [--slot-start-time-range <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--scheduled-instance-ids`` (list)


  One or more Scheduled Instance IDs.

  



Syntax::

  "string" "string" ...



``--slot-start-time-range`` (structure)


  The time period for the first schedule to start.

  



Shorthand Syntax::

    EarliestTime=timestamp,LatestTime=timestamp




JSON Syntax::

  {
    "EarliestTime": timestamp,
    "LatestTime": timestamp
  }



``--next-token`` (string)


  The token for the next set of results.

  

``--max-results`` (integer)


  The maximum number of results to return in a single call. To retrieve the remaining results, make another call with the returned ``NextToken`` value.

  

``--filters`` (list)


  One or more filters.

   

   
  * ``availability-zone`` - The Availability Zone (for example, ``us-west-2a`` ). 
   
  * ``instance-type`` - The instance type (for example, ``c4.large`` ). 
   
  * ``network-platform`` - The network platform (``EC2-Classic`` or ``EC2-VPC`` ). 
   
  * ``platform`` - The platform (``Linux/UNIX`` or ``Windows`` ). 
   

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe your Scheduled Instances**

This example describes the specified Scheduled Instance.

Command::

  aws ec2 describe-scheduled-instances --scheduled-instance-ids sci-1234-1234-1234-1234-123456789012

Output::

  {
    "ScheduledInstanceSet": [
        {
            "AvailabilityZone": "us-west-2b",
            "ScheduledInstanceId": "sci-1234-1234-1234-1234-123456789012",
            "HourlyPrice": "0.095",
            "CreateDate": "2016-01-25T21:43:38.612Z",
            "Recurrence": {
                "OccurrenceDaySet": [
                    1
                ],
                "Interval": 1,
                "Frequency": "Weekly",
                "OccurrenceRelativeToEnd": false,
                "OccurrenceUnit": ""
            },
            "Platform": "Linux/UNIX",
            "TermEndDate": "2017-01-31T09:00:00Z",
            "InstanceCount": 1,
            "SlotDurationInHours": 32,
            "TermStartDate": "2016-01-31T09:00:00Z",
            "NetworkPlatform": "EC2-VPC",
            "TotalScheduledInstanceHours": 1696,
            "NextSlotStartTime": "2016-01-31T09:00:00Z",
            "InstanceType": "c4.large"
        }
    ]
  }

This example describes all your Scheduled Instances.

Command::

  aws ec2 describe-scheduled-instances


======
Output
======

NextToken -> (string)

  

  The token required to retrieve the next set of results. This value is ``null`` when there are no more results to return.

  

  

ScheduledInstanceSet -> (list)

  

  Information about the Scheduled Instances.

  

  (structure)

    

    Describes a Scheduled Instance.

    

    ScheduledInstanceId -> (string)

      

      The Scheduled Instance ID.

      

      

    InstanceType -> (string)

      

      The instance type.

      

      

    Platform -> (string)

      

      The platform (``Linux/UNIX`` or ``Windows`` ).

      

      

    NetworkPlatform -> (string)

      

      The network platform (``EC2-Classic`` or ``EC2-VPC`` ).

      

      

    AvailabilityZone -> (string)

      

      The Availability Zone.

      

      

    SlotDurationInHours -> (integer)

      

      The number of hours in the schedule.

      

      

    Recurrence -> (structure)

      

      The schedule recurrence.

      

      Frequency -> (string)

        

        The frequency (``Daily`` , ``Weekly`` , or ``Monthly`` ).

        

        

      Interval -> (integer)

        

        The interval quantity. The interval unit depends on the value of ``frequency`` . For example, every 2 weeks or every 2 months.

        

        

      OccurrenceDaySet -> (list)

        

        The days. For a monthly schedule, this is one or more days of the month (1-31). For a weekly schedule, this is one or more days of the week (1-7, where 1 is Sunday).

        

        (integer)

          

          

        

      OccurrenceRelativeToEnd -> (boolean)

        

        Indicates whether the occurrence is relative to the end of the specified week or month.

        

        

      OccurrenceUnit -> (string)

        

        The unit for ``occurrenceDaySet`` (``DayOfWeek`` or ``DayOfMonth`` ).

        

        

      

    PreviousSlotEndTime -> (timestamp)

      

      The time that the previous schedule ended or will end.

      

      

    NextSlotStartTime -> (timestamp)

      

      The time for the next schedule to start.

      

      

    HourlyPrice -> (string)

      

      The hourly price for a single instance.

      

      

    TotalScheduledInstanceHours -> (integer)

      

      The total number of hours for a single instance for the entire term.

      

      

    InstanceCount -> (integer)

      

      The number of instances.

      

      

    TermStartDate -> (timestamp)

      

      The start date for the Scheduled Instance.

      

      

    TermEndDate -> (timestamp)

      

      The end date for the Scheduled Instance.

      

      

    CreateDate -> (timestamp)

      

      The date when the Scheduled Instance was purchased.

      

      

    

  

