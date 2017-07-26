[ :ref:`aws <cli:aws>` ]

.. _cli:aws cloudwatch:


**********
cloudwatch
**********



===========
Description
===========



Amazon CloudWatch monitors your Amazon Web Services (AWS) resources and the applications you run on AWS in real-time. You can use CloudWatch to collect and track metrics, which are the variables you want to measure for your resources and applications.

 

CloudWatch alarms send notifications or automatically make changes to the resources you are monitoring based on rules that you define. For example, you can monitor the CPU usage and disk reads and writes of your Amazon Elastic Compute Cloud (Amazon EC2) instances and then use this data to determine whether you should launch additional instances to handle increased load. You can also use this data to stop under-used instances to save money.

 

In addition to monitoring the built-in metrics that come with AWS, you can monitor your own custom metrics. With CloudWatch, you gain system-wide visibility into resource utilization, application performance, and operational health.



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  delete-alarms
  describe-alarm-history
  describe-alarms
  describe-alarms-for-metric
  disable-alarm-actions
  enable-alarm-actions
  get-metric-statistics
  list-metrics
  put-metric-alarm
  put-metric-data
  set-alarm-state
