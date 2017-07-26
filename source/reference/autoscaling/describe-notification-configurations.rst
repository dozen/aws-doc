[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-notification-configurations:


************************************
describe-notification-configurations
************************************



===========
Description
===========



Describes the notification actions associated with the specified Auto Scaling group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DescribeNotificationConfigurations>`_


``describe-notification-configurations`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``NotificationConfigurations``


========
Synopsis
========

::

    describe-notification-configurations
  [--auto-scaling-group-names <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auto-scaling-group-names`` (list)


  The name of the group.

  



Syntax::

  "string" "string" ...



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

**To describe the Auto Scaling notification configurations**

This example describes the notification configurations for the specified Auto Scaling group::

    aws autoscaling describe-notification-configurations --auto-scaling-group-name my-auto-scaling-group

The following is example output::

    {
        "NotificationConfigurations": [
            {
                "AutoScalingGroupName": "my-auto-scaling-group",
                "NotificationType": "autoscaling:TEST_NOTIFICATION",
                "TopicARN": "arn:aws:sns:us-west-2:123456789012:my-sns-topic-2"
            },
            {
                "AutoScalingGroupName": "my-auto-scaling-group",
                "NotificationType": "autoscaling:TEST_NOTIFICATION",
                "TopicARN": "arn:aws:sns:us-west-2:123456789012:my-sns-topic"
            }
        ]
    }

To return a specific number of notification configurations, use the ``max-items`` parameter::

    aws autoscaling describe-notification-configurations --auto-scaling-group-name my-auto-scaling-group --max-items 1

The following is example output::

    {
        "NextToken": "Z3M3LMPEXAMPLE",
        "NotificationConfigurations": [
            {
                "AutoScalingGroupName": "my-auto-scaling-group",
                "NotificationType": "autoscaling:TEST_NOTIFICATION",
                "TopicARN": "arn:aws:sns:us-west-2:123456789012:my-sns-topic-2"
            }
        ]
    }

Use the ``NextToken`` field with the ``starting-token`` parameter in a subsequent call to get additional notification configurations::

    aws autoscaling describe-notification-configurations --auto-scaling-group-name my-auto-scaling-group --starting-token Z3M3LMPEXAMPLE

For more information, see `Getting Notifications When Your Auto Scaling Group Changes`_ in the *Auto Scaling Developer Guide*.

.. _`Getting Notifications When Your Auto Scaling Group Changes`: http://docs.aws.amazon.com/AutoScaling/latest/DeveloperGuide/ASGettingNotifications.html


======
Output
======

NotificationConfigurations -> (list)

  

  The notification configurations.

  

  (structure)

    

    Describes a notification.

    

    AutoScalingGroupName -> (string)

      

      The name of the group.

      

      

    TopicARN -> (string)

      

      The Amazon Resource Name (ARN) of the Amazon Simple Notification Service (SNS) topic.

      

      

    NotificationType -> (string)

      

      One of the following event notification types:

       

       
      * ``autoscaling:EC2_INSTANCE_LAUNCH``   
       
      * ``autoscaling:EC2_INSTANCE_LAUNCH_ERROR``   
       
      * ``autoscaling:EC2_INSTANCE_TERMINATE``   
       
      * ``autoscaling:EC2_INSTANCE_TERMINATE_ERROR``   
       
      * ``autoscaling:TEST_NOTIFICATION``   
       

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

