[ :ref:`aws <cli:aws>` ]

.. _cli:aws logs:


****
logs
****



===========
Description
===========



You can use Amazon CloudWatch Logs to monitor, store, and access your log files from EC2 instances, Amazon CloudTrail, or other sources. You can then retrieve the associated log data from CloudWatch Logs using the Amazon CloudWatch console, the CloudWatch Logs commands in the AWS CLI, the CloudWatch Logs API, or the CloudWatch Logs SDK.

 

You can use CloudWatch Logs to:

 

 
* **Monitor Logs from Amazon EC2 Instances in Real-time** : You can use CloudWatch Logs to monitor applications and systems using log data. For example, CloudWatch Logs can track the number of errors that occur in your application logs and send you a notification whenever the rate of errors exceeds a threshold you specify. CloudWatch Logs uses your log data for monitoring; so, no code changes are required. For example, you can monitor application logs for specific literal terms (such as "NullReferenceException") or count the number of occurrences of a literal term at a particular position in log data (such as "404" status codes in an Apache access log). When the term you are searching for is found, CloudWatch Logs reports the data to a Amazon CloudWatch metric that you specify. 
 
* **Monitor Amazon CloudTrail Logged Events** : You can create alarms in Amazon CloudWatch and receive notifications of particular API activity as captured by CloudTrail and use the notification to perform troubleshooting. 
 
* **Archive Log Data** : You can use CloudWatch Logs to store your log data in highly durable storage. You can change the log retention setting so that any log events older than this setting are automatically deleted. The CloudWatch Logs agent makes it easy to quickly send both rotated and non-rotated log data off of a host and into the log service. You can then access the raw log data when you need it. 
 



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  cancel-export-task
  create-export-task
  create-log-group
  create-log-stream
  delete-destination
  delete-log-group
  delete-log-stream
  delete-metric-filter
  delete-retention-policy
  delete-subscription-filter
  describe-destinations
  describe-export-tasks
  describe-log-groups
  describe-log-streams
  describe-metric-filters
  describe-subscription-filters
  filter-log-events
  get-log-events
  list-tags-log-group
  put-destination
  put-destination-policy
  put-log-events
  put-metric-filter
  put-retention-policy
  put-subscription-filter
  tag-log-group
  test-metric-filter
  untag-log-group
