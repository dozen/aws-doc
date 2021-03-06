[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 purchase-scheduled-instances:


****************************
purchase-scheduled-instances
****************************



===========
Description
===========



Purchases one or more Scheduled Instances with the specified schedule.

 

Scheduled Instances enable you to purchase Amazon EC2 compute capacity by the hour for a one-year term. Before you can purchase a Scheduled Instance, you must call  describe-scheduled-instance-availability to check for available schedules and obtain a purchase token. After you purchase a Scheduled Instance, you must call  run-scheduled-instances during each scheduled time period.

 

After you purchase a Scheduled Instance, you can't cancel, modify, or resell your purchase.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/PurchaseScheduledInstances>`_


========
Synopsis
========

::

    purchase-scheduled-instances
  [--client-token <value>]
  [--dry-run | --no-dry-run]
  --purchase-requests <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--client-token`` (string)


  Unique, case-sensitive identifier that ensures the idempotency of the request. For more information, see `Ensuring Idempotency <http://docs.aws.amazon.com/AWSEC2/latest/APIReference/Run_Instance_Idempotency.html>`_ .

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--purchase-requests`` (list)


  One or more purchase requests.

  



Shorthand Syntax::

    InstanceCount=integer,PurchaseToken=string ...




JSON Syntax::

  [
    {
      "InstanceCount": integer,
      "PurchaseToken": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To purchase a Scheduled Instance**

This example purchases a Scheduled Instance.

Command::

  aws ec2 purchase-scheduled-instances --purchase-requests file://purchase-request.json

Purchase-request.json::

  [
      {
          "PurchaseToken": "eyJ2IjoiMSIsInMiOjEsImMiOi...",
          "InstanceCount": 1
      }
  ]

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


======
Output
======

ScheduledInstanceSet -> (list)

  

  Information about the Scheduled Instances.

  

  (structure)

    

    Describes a Scheduled Instance.

    

    AvailabilityZone -> (string)

      

      The Availability Zone.

      

      

    CreateDate -> (timestamp)

      

      The date when the Scheduled Instance was purchased.

      

      

    HourlyPrice -> (string)

      

      The hourly price for a single instance.

      

      

    InstanceCount -> (integer)

      

      The number of instances.

      

      

    InstanceType -> (string)

      

      The instance type.

      

      

    NetworkPlatform -> (string)

      

      The network platform (``EC2-Classic`` or ``EC2-VPC`` ).

      

      

    NextSlotStartTime -> (timestamp)

      

      The time for the next schedule to start.

      

      

    Platform -> (string)

      

      The platform (``Linux/UNIX`` or ``Windows`` ).

      

      

    PreviousSlotEndTime -> (timestamp)

      

      The time that the previous schedule ended or will end.

      

      

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

        

        

      

    ScheduledInstanceId -> (string)

      

      The Scheduled Instance ID.

      

      

    SlotDurationInHours -> (integer)

      

      The number of hours in the schedule.

      

      

    TermEndDate -> (timestamp)

      

      The end date for the Scheduled Instance.

      

      

    TermStartDate -> (timestamp)

      

      The start date for the Scheduled Instance.

      

      

    TotalScheduledInstanceHours -> (integer)

      

      The total number of hours for a single instance for the entire term.

      

      

    

  

