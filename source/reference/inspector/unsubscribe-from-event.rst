[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector unsubscribe-from-event:


**********************
unsubscribe-from-event
**********************



===========
Description
===========



Disables the process of sending Amazon Simple Notification Service (SNS) notifications about a specified event to a specified SNS topic.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/UnsubscribeFromEvent>`_


========
Synopsis
========

::

    unsubscribe-from-event
  --resource-arn <value>
  --event <value>
  --topic-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arn`` (string)


  The ARN of the assessment template that is used during the event for which you want to stop receiving SNS notifications.

  

``--event`` (string)


  The event for which you want to stop receiving SNS notifications.

  

  Possible values:

  
  *   ``ASSESSMENT_RUN_STARTED``

  
  *   ``ASSESSMENT_RUN_COMPLETED``

  
  *   ``ASSESSMENT_RUN_STATE_CHANGED``

  
  *   ``FINDING_REPORTED``

  
  *   ``OTHER``

  

  

``--topic-arn`` (string)


  The ARN of the SNS topic to which SNS notifications are sent.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To unsubscribe from an event**

The following ``unsubscribe-from-event`` command disables the process of sending Amazon SNS notifications about the ``ASSESSMENT_RUN_COMPLETED`` event to the topic with the ARN of ``arn:aws:sns:us-west-2:123456789012:exampletopic``::

  aws inspector unsubscribe-from-event --event ASSESSMENT_RUN_COMPLETED --resource-arn arn:aws:inspector:us-west-2:123456789012:target/0-nvgVhaxX/template/0-7sbz2Kz0 --topic arn:aws:sns:us-west-2:123456789012:exampletopic

For more information, see `Amazon Inspector Assessment Templates and Assessment Runs`_ in the *Amazon Inspector* guide.

.. _`Amazon Inspector Assessment Templates and Assessment Runs`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_assessments.html



======
Output
======

None