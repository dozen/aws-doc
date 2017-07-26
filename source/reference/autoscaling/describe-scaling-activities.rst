[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-scaling-activities:


***************************
describe-scaling-activities
***************************



===========
Description
===========



Describes one or more scaling activities for the specified Auto Scaling group. If you omit the ``activity-ids`` , the call returns all activities from the past six weeks. Activities are sorted by the start time. Activities still in progress appear first on the list.



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
  [--generate-cli-skeleton]




=======
Options
=======

``--activity-ids`` (list)


  The activity IDs of the desired scaling activities. If this list is omitted, all activities are described. If you specify an Auto Scaling group, the results are limited to that group. The list of requested activities cannot contain more than 50 items. If unknown activities are requested, they are ignored with no error.

  



Syntax::

  "string" "string" ...



``--auto-scaling-group-name`` (string)


  The name of the group.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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
                  "Cause": "At 2013-08-19T20:53:25Z a user request created an AutoScalingGroup changing the desired capacity from 0 to 1.  At 2013-08-19T20:53:29Z an instance was started in response to a difference between desired and actual capa city, increasing the capacity from 0 to 1.",
                  "StatusCode": "Successful"
              }
         ]
      }

To describe a specific scaling activity, use the ``activity-ids`` parameter::

	aws autoscaling describe-scaling-activities --activity-ids b55c7b67-c8aa-4d10-b240-730ff91d8895

To return a specific number of activities, use the ``max-items`` parameter::

	aws autoscaling describe-scaling-activities --max-items 1

If the output includes a ``NextToken`` field, there are more activities. To get the additional activities, use the value of this field with the ``starting-token`` parameter in a subsequent call as follows::

    aws autoscaling describe-scaling-activities --starting-token None___1


======
Output
======

Activities -> (list)

  

  The scaling activities.

  

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

  

  

