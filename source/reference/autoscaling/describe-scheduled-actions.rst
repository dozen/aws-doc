[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-scheduled-actions:


**************************
describe-scheduled-actions
**************************



===========
Description
===========



Describes the actions scheduled for your Auto Scaling group that haven't run. To describe the actions that have already run, use  describe-scaling-activities .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DescribeScheduledActions>`_


``describe-scheduled-actions`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ScheduledUpdateGroupActions``


========
Synopsis
========

::

    describe-scheduled-actions
  [--auto-scaling-group-name <value>]
  [--scheduled-action-names <value>]
  [--start-time <value>]
  [--end-time <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auto-scaling-group-name`` (string)


  The name of the group.

  

``--scheduled-action-names`` (list)


  Describes one or more scheduled actions. If you omit this parameter, all scheduled actions are described. If you specify an unknown scheduled action, it is ignored with no error.

   

  You can describe up to a maximum of 50 instances with a single call. If there are more items to return, the call returns a token. To get the next set of items, repeat the call with the returned token.

  



Syntax::

  "string" "string" ...



``--start-time`` (timestamp)


  The earliest scheduled start time to return. If scheduled action names are provided, this parameter is ignored.

  

``--end-time`` (timestamp)


  The latest scheduled start time to return. If scheduled action names are provided, this parameter is ignored.

  

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



========
Examples
========

**To describe scheduled actions**

This example describes all your scheduled actions::

    aws autoscaling describe-scheduled-actions

The following is example output::

    {
        "ScheduledUpdateGroupActions": [
            {
                "MinSize": 2,
                "DesiredCapacity": 4,
                "AutoScalingGroupName": "my-auto-scaling-group",
                "MaxSize": 6,
                "Recurrence": "30 0 1 12 0",
                "ScheduledActionARN": "arn:aws:autoscaling:us-west-2:123456789012:scheduledUpdateGroupAction:8e86b655-b2e6-4410-8f29-b4f094d6871c:autoScalingGroupName/my-auto-scaling-group:scheduledActionName/my-scheduled-action",
                "ScheduledActionName": "my-scheduled-action",
                "StartTime": "2019-12-01T00:30:00Z",
                "Time": "2019-12-01T00:30:00Z"
            }
        ]
    }

To describe the scheduled actions for a specific Auto Scaling group, use the ``auto-scaling-group-name`` parameter::

    aws autoscaling describe-scheduled-actions --auto-scaling-group-name my-auto-scaling-group

To describe a specific scheduled action, use the ``scheduled-action-names`` parameter::

    aws autoscaling describe-scheduled-actions --scheduled-action-names my-scheduled-action

To describe the scheduled actions that start at a specific time, use the ``start-time`` parameter::

    aws autoscaling describe-scheduled-actions --start-time "2019-12-01T00:30:00Z"

To describe the scheduled actions that end at a specific time, use the ``end-time`` parameter::

    aws autoscaling describe-scheduled-actions --end-time "2022-12-01T00:30:00Z"

To return a specific number of scheduled actions, use the ``max-items`` parameter::

    aws autoscaling describe-scheduled-actions --auto-scaling-group-name my-auto-scaling-group --max-items 1

The following is example output::

    {
        "NextToken": "Z3M3LMPEXAMPLE",
        "ScheduledUpdateGroupActions": [
            {
                "MinSize": 2,
                "DesiredCapacity": 4,
                "AutoScalingGroupName": "my-auto-scaling-group",
                "MaxSize": 6,
                "Recurrence": "30 0 1 12 0",
                "ScheduledActionARN": "arn:aws:autoscaling:us-west-2:123456789012:scheduledUpdateGroupAction:8e86b655-b2e6-4410-8f29-b4f094d6871c:autoScalingGroupName/my-auto-scaling-group:scheduledActionName/my-scheduled-action",
                "ScheduledActionName": "my-scheduled-action",
                "StartTime": "2019-12-01T00:30:00Z",
                "Time": "2019-12-01T00:30:00Z"
            }
        ]
    }

Use the ``NextToken`` field with the ``starting-token`` parameter in a subsequent call to get the additional scheduled actions::

    aws autoscaling describe-scheduled-actions --auto-scaling-group-name my-auto-scaling-group --starting-token Z3M3LMPEXAMPLE

For more information, see `Scheduled Scaling`_ in the *Auto Scaling Developer Guide*.

.. _`Scheduled Scaling`: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/schedule_time.html


======
Output
======

ScheduledUpdateGroupActions -> (list)

  

  The scheduled actions.

  

  (structure)

    

    Describes a scheduled update to an Auto Scaling group.

    

    AutoScalingGroupName -> (string)

      

      The name of the group.

      

      

    ScheduledActionName -> (string)

      

      The name of the scheduled action.

      

      

    ScheduledActionARN -> (string)

      

      The Amazon Resource Name (ARN) of the scheduled action.

      

      

    Time -> (timestamp)

      

      This parameter is deprecated.

      

      

    StartTime -> (timestamp)

      

      The date and time that the action is scheduled to begin. This date and time can be up to one month in the future.

       

      When ``StartTime`` and ``EndTime`` are specified with ``Recurrence`` , they form the boundaries of when the recurring action will start and stop.

      

      

    EndTime -> (timestamp)

      

      The date and time that the action is scheduled to end. This date and time can be up to one month in the future.

      

      

    Recurrence -> (string)

      

      The recurring schedule for the action.

      

      

    MinSize -> (integer)

      

      The minimum size of the group.

      

      

    MaxSize -> (integer)

      

      The maximum size of the group.

      

      

    DesiredCapacity -> (integer)

      

      The number of instances you prefer to maintain in the group.

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

