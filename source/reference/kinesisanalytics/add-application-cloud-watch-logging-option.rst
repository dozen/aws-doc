[ :ref:`aws <cli:aws>` . :ref:`kinesisanalytics <cli:aws kinesisanalytics>` ]

.. _cli:aws kinesisanalytics add-application-cloud-watch-logging-option:


******************************************
add-application-cloud-watch-logging-option
******************************************



===========
Description
===========



Adds a CloudWatch log stream to monitor application configuration errors. For more information about using CloudWatch log streams with Amazon Kinesis Analytics applications, see `Monitoring Configuration Errors <http://docs.aws.amazon.com/kinesisanalytics/latest/dev/cloudwatch-monitor-configuration.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesisanalytics-2015-08-14/AddApplicationCloudWatchLoggingOption>`_


========
Synopsis
========

::

    add-application-cloud-watch-logging-option
  --application-name <value>
  --current-application-version-id <value>
  --cloud-watch-logging-option <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  The Amazon Kinesis Analytics application name.

  

``--current-application-version-id`` (long)


  The version ID of the Amazon Kinesis Analytics application.

  

``--cloud-watch-logging-option`` (structure)


  Provide the CloudWatch log stream ARN and the IAM role ARN. Note: To write application messages to CloudWatch, the IAM role used must have the ``PutLogEvents`` policy action enabled. 

  



Shorthand Syntax::

    LogStreamARN=string,RoleARN=string




JSON Syntax::

  {
    "LogStreamARN": "string",
    "RoleARN": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

