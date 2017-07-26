[ :ref:`aws <cli:aws>` ]

.. _cli:aws events:


******
events
******



===========
Description
===========



Amazon CloudWatch Events helps you to respond to state changes in your AWS resources. When your resources change state they automatically send events into an event stream. You can create rules that match selected events in the stream and route them to targets to take action. You can also use rules to take action on a pre-determined schedule. For example, you can configure rules to: 

 

 
* Automatically invoke an AWS Lambda function to update DNS entries when an event notifies you that Amazon EC2 instance enters the running state.
 
* Direct specific API records from CloudTrail to an Amazon Kinesis stream for detailed analysis of potential security or availability risks.
 
* Periodically invoke a built-in target to create a snapshot of an Amazon EBS volume.
 

 

For more information about Amazon CloudWatch Events features, see the `Amazon CloudWatch Developer Guide`_ . 



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  delete-rule
  describe-rule
  disable-rule
  enable-rule
  list-rule-names-by-target
  list-rules
  list-targets-by-rule
  put-events
  put-rule
  put-targets
  remove-targets
  test-event-pattern


.. _Amazon CloudWatch Developer Guide: http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide
