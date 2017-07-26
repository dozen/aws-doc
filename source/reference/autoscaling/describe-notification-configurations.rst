[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-notification-configurations:


************************************
describe-notification-configurations
************************************



===========
Description
===========



Describes the notification actions associated with the specified Auto Scaling group.



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
  [--generate-cli-skeleton]




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

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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
    "NextToken": "None___1",
    "NotificationConfigurations": [
      {
        "AutoScalingGroupName": "my-auto-scaling-group",
        "NotificationType": "autoscaling:TEST_NOTIFICATION",
        "TopicARN": "arn:aws:sns:us-west-2:123456789012:my-sns-topic-2"
      }
    ]
  }

Use the ``NextToken`` field with the ``starting-token`` parameter in a subsequent call to get additional notification configurations::

    aws autoscaling describe-notification-configurations --auto-scaling-group-name my-auto-scaling-group --starting-token None___1

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

  

  

