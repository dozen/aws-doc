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



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeScheduledInstanceAvailability>`_


========
Synopsis
========

::

    describe-scheduled-instance-availability
  [--dry-run | --no-dry-run]
  [--filters <value>]
  --first-slot-start-time-range <value>
  [--max-results <value>]
  [--max-slot-duration-in-hours <value>]
  [--min-slot-duration-in-hours <value>]
  [--next-token <value>]
  --recurrence <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

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



``--first-slot-start-time-range`` (structure)


  The time period for the first schedule to start.

  



Shorthand Syntax::

    EarliestTime=timestamp,LatestTime=timestamp




JSON Syntax::

  {
    "EarliestTime": timestamp,
    "LatestTime": timestamp
  }



``--max-results`` (integer)


  The maximum number of results to return in a single call. This value can be between 5 and 300. The default value is 300. To retrieve the remaining results, make another call with the returned ``NextToken`` value.

  

``--max-slot-duration-in-hours`` (integer)


  The maximum available duration, in hours. This value must be greater than ``MinSlotDurationInHours`` and less than 1,720.

  

``--min-slot-duration-in-hours`` (integer)


  The minimum available duration, in hours. The minimum required duration is 1,200 hours per year. For example, the minimum daily schedule is 4 hours, the minimum weekly schedule is 24 hours, and the minimum monthly schedule is 100 hours.

  

``--next-token`` (string)


  The token for the next set of results.

  

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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

    

    AvailabilityZone -> (string)

      

      The Availability Zone.

      

      

    AvailableInstanceCount -> (integer)

      

      The number of available instances.

      

      

    FirstSlotStartTime -> (timestamp)

      

      The time period for the first schedule to start.

      

      

    HourlyPrice -> (string)

      

      The hourly price for a single instance.

      

      

    InstanceType -> (string)

      

      The instance type. You can specify one of the C3, C4, M4, or R3 instance types.

      

      

    MaxTermDurationInDays -> (integer)

      

      The maximum term. The only possible value is 365 days.

      

      

    MinTermDurationInDays -> (integer)

      

      The minimum term. The only possible value is 365 days.

      

      

    NetworkPlatform -> (string)

      

      The network platform (``EC2-Classic`` or ``EC2-VPC`` ).

      

      

    Platform -> (string)

      

      The platform (``Linux/UNIX`` or ``Windows`` ).

      

      

    PurchaseToken -> (string)

      

      The purchase token. This token expires in two hours.

      

      

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

        

        

      

    SlotDurationInHours -> (integer)

      

      The number of hours in the schedule.

      

      

    TotalScheduledInstanceHours -> (integer)

      

      The total number of hours for a single instance for the entire term.

      

      

    

  

