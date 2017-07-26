[ :ref:`aws <cli:aws>` ]

.. _cli:aws application-autoscaling:


***********************
application-autoscaling
***********************



===========
Description
===========



With Application Auto Scaling, you can automatically scale your AWS resources. The experience similar to that of `Auto Scaling <https://aws.amazon.com/autoscaling/>`_ . You can use Application Auto Scaling to accomplish the following tasks:

 

 
* Define scaling policies to automatically scale your AWS resources 
 
* Scale your resources in response to CloudWatch alarms 
 
* View the history of your scaling events 
 

 

Application Auto Scaling can scale the following AWS resources:

 

 
* Amazon ECS services. For more information, see `Service Auto Scaling <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-auto-scaling.html>`_ in the *Amazon EC2 Container Service Developer Guide* . 
 
* Amazon EC2 Spot fleets. For more information, see `Automatic Scaling for Spot Fleet <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/fleet-auto-scaling.html>`_ in the *Amazon EC2 User Guide* . 
 
* Amazon EMR clusters. For more information, see `Using Automatic Scaling in Amazon EMR <http://docs.aws.amazon.com/ElasticMapReduce/latest/ManagementGuide/emr-automatic-scaling.html>`_ in the *Amazon EMR Management Guide* . 
 
* AppStream 2.0 fleets. For more information, see `Fleet Auto Scaling for Amazon AppStream 2.0 <http://docs.aws.amazon.com/appstream2/latest/developerguide/autoscaling.html>`_ in the *Amazon AppStream 2.0 Developer Guide* . 
 
* Provisioned read and write capacity for Amazon DynamoDB tables and global secondary indexes. For more information, see `Auto Scaling for DynamoDB <http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/TargetTracking.html>`_ in the *Amazon DynamoDB Developer Guide* . 
 

 

For a list of supported regions, see `AWS Regions and Endpoints\: Application Auto Scaling <http://docs.aws.amazon.com/general/latest/gr/rande.html#as-app_region>`_ in the *AWS General Reference* .



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  delete-scaling-policy
  deregister-scalable-target
  describe-scalable-targets
  describe-scaling-activities
  describe-scaling-policies
  put-scaling-policy
  register-scalable-target
