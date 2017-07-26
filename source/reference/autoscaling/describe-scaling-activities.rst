[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-scaling-activities:


***************************
describe-scaling-activities
***************************



===========
Description
===========



Describes one or more scaling activities for the specified Auto Scaling group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DescribeScalingActivities>`_


``describe-scaling-activities`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Activities``


========
Synopsis
========

::

    describe-scaling-activities
  [--activity-ids <value>]
  [--auto-scaling-group-name <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--activity-ids`` (list)


  The activity IDs of the desired scaling activities. If you omit this parameter, all activities for the past six weeks are described. If you specify an Auto Scaling group, the results are limited to that group. The list of requested activities cannot contain more than 50 items. If unknown activities are requested, they are ignored with no error.

  



Syntax::

  "string" "string" ...



``--auto-scaling-group-name`` (string)


  The name of the group.

  

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

**To get a description of the scaling activities for an Auto Scaling group**

This example describes the scaling activities for the specified Auto Scaling group::

    aws autoscaling describe-scaling-activities --auto-scaling-group-name my-auto-scaling-group

The following is example output::

    {
        "Activities": [
            {
                "Description": "Launching a new EC2 instance: i-4ba0837f",
                "AutoScalingGroupName": "my-auto-scaling-group",
                "ActivityId": "f9f2d65b-f1f2-43e7-b46d-d86756459699",
                "Details": "{"Availability Zone":"us-west-2c"}",
                "StartTime": "2013-08-19T20:53:29.930Z",
                "Progress": 100,
                "EndTime": "2013-08-19T20:54:02Z",
                "Cause": "At 2013-08-19T20:53:25Z a user request created an AutoScalingGroup changing the desired capacity from 0 to 1.  At 2013-08-19T20:53:29Z an instance was started in response to a difference between desired and actual capacity, increasing the capacity from 0 to 1.",
                "StatusCode": "Successful"
            }
        ]
    }

To describe a specific scaling activity, use the ``activity-ids`` parameter::

    aws autoscaling describe-scaling-activities --activity-ids b55c7b67-c8aa-4d10-b240-730ff91d8895

To return a specific number of activities, use the ``max-items`` parameter::

    aws autoscaling describe-scaling-activities --max-items 1

If the output includes a ``NextToken`` field, there are more activities. To get the additional activities, use the value of this field with the ``starting-token`` parameter in a subsequent call as follows::

    aws autoscaling describe-scaling-activities --starting-token Z3M3LMPEXAMPLE


======
Output
======

Activities -> (list)

  

  The scaling activities. Activities are sorted by start time. Activities still in progress are described first.

  

  (structure)

    

    Describes scaling activity, which is a long-running process that represents a change to your Auto Scaling group, such as changing its size or replacing an instance.

    

    ActivityId -> (string)

      

      The ID of the activity.

      

      

    AutoScalingGroupName -> (string)

      

      The name of the Auto Scaling group.

      

      

    Description -> (string)

      

      A friendly, more verbose description of the activity.

      

      

    Cause -> (string)

      

      The reason the activity began.

      

      

    StartTime -> (timestamp)

      

      The start time of the activity.

      

      

    EndTime -> (timestamp)

      

      The end time of the activity.

      

      

    StatusCode -> (string)

      

      The current status of the activity.

      

      

    StatusMessage -> (string)

      

      A friendly, more verbose description of the activity status.

      

      

    Progress -> (integer)

      

      A value between 0 and 100 that indicates the progress of the activity.

      

      

    Details -> (string)

      

      The details about the activity.

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

