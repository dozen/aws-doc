[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-scheduled-instance-availability:


****************************************
describe-scheduled-instance-availability
****************************************



===========
Description
===========



Finds available schedules that meet the specified criteria.

 

You can search for an available schedule no more than 3 months in advance. You must meet the minimum required duration of 1,200 hours per year. For example, the minimum daily schedule is 4 hours, the minimum weekly schedule is 24 hours, and the minimum monthly schedule is 100 hours.

 

After you find a schedule that meets your needs, call  purchase-scheduled-instances to purchase Scheduled Instances with that schedule.



========
Synopsis
========

::

    describe-scheduled-instance-availability
  [--dry-run | --no-dry-run]
  --recurrence <value>
  --first-slot-start-time-range <value>
  [--min-slot-duration-in-hours <value>]
  [--max-slot-duration-in-hours <value>]
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

  

``--recurrence`` (structure)


  The schedule recurrence.

  



Shorthand Syntax::

    Frequency=string,Interval=integer,OccurrenceDays=integer,integer,OccurrenceRelativeToEnd=boolean,OccurrenceUnit=string




JSON Syntax::

  {
    "Frequency": "string",
    "Interval": integer,
    "OccurrenceDays": [integer, ...],
    "OccurrenceRelativeToEnd": true|false,
    "OccurrenceUnit": "string"
  }



``--first-slot-start-time-range`` (structure)


  The time period for the first schedule to start.

  



Shorthand Syntax::

    EarliestTime=timestamp,LatestTime=timestamp




JSON Syntax::

  {
    "EarliestTime": timestamp,
    "LatestTime": timestamp
  }



``--min-slot-duration-in-hours`` (integer)


  The minimum available duration, in hours. The minimum required duration is 1,200 hours per year. For example, the minimum daily schedule is 4 hours, the minimum weekly schedule is 24 hours, and the minimum monthly schedule is 100 hours.

  

``--max-slot-duration-in-hours`` (integer)


  The maximum available duration, in hours. This value must be greater than ``MinSlotDurationInHours`` and less than 1,720.

  

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

**To describe an available schedule**

This example describes a schedule that occurs every week on Sunday, starting on the specified date.

Command::

  aws ec2 describe-scheduled-instance-availability --recurrence Frequency=Weekly,Interval=1,OccurrenceDays=[1] --first-slot-start-time-range EarliestTime=2016-01-31T00:00:00Z,LatestTime=2016-01-31T04:00:00Z

Output::

  {
    "ScheduledInstanceAvailabilitySet": [
      {
          "AvailabilityZone": "us-west-2b",
          "TotalScheduledInstanceHours": 1219,
          "PurchaseToken": "eyJ2IjoiMSIsInMiOjEsImMiOi...",
          "MinTermDurationInDays": 366,
          "AvailableInstanceCount": 20,
          "Recurrence": {
              "OccurrenceDaySet": [
                  1
              ],
              "Interval": 1,
              "Frequency": "Weekly",
              "OccurrenceRelativeToEnd": false
          },
          "Platform": "Linux/UNIX",
          "FirstSlotStartTime": "2016-01-31T00:00:00Z",
          "MaxTermDurationInDays": 366,
          "SlotDurationInHours": 23,
          "NetworkPlatform": "EC2-VPC",
          "InstanceType": "c4.large",
          "HourlyPrice": "0.095"
      },
      ...
    ]
  }

To narrow the results, you can add filters that specify the operating system, network, and instance type.

Command:

  --filters Name=platform,Values=Linux/UNIX Name=network-platform,Values=EC2-VPC Name=instance-type,Values=c4.large


======
Output
======

NextToken -> (string)

  

  The token required to retrieve the next set of results. This value is ``null`` when there are no more results to return.

  

  

ScheduledInstanceAvailabilitySet -> (list)

  

  Information about the available Scheduled Instances.

  

  (structure)

    

    Describes a schedule that is available for your Scheduled Instances.

    

    InstanceType -> (string)

      

      The instance type. You can specify one of the C3, C4, M4, or R3 instance types.

      

      

    Platform -> (string)

      

      The platform (``Linux/UNIX`` or ``Windows`` ).

      

      

    NetworkPlatform -> (string)

      

      The network platform (``EC2-Classic`` or ``EC2-VPC`` ).

      

      

    AvailabilityZone -> (string)

      

      The Availability Zone.

      

      

    PurchaseToken -> (string)

      

      The purchase token. This token expires in two hours.

      

      

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

        

        

      

    FirstSlotStartTime -> (timestamp)

      

      The time period for the first schedule to start.

      

      

    HourlyPrice -> (string)

      

      The hourly price for a single instance.

      

      

    TotalScheduledInstanceHours -> (integer)

      

      The total number of hours for a single instance for the entire term.

      

      

    AvailableInstanceCount -> (integer)

      

      The number of available instances.

      

      

    MinTermDurationInDays -> (integer)

      

      The minimum term. The only possible value is 365 days.

      

      

    MaxTermDurationInDays -> (integer)

      

      The maximum term. The only possible value is 365 days.

      

      

    

  

