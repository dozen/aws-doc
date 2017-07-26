[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector list-event-subscriptions:


************************
list-event-subscriptions
************************



===========
Description
===========



Lists all the event subscriptions for the assessment template that is specified by the ARN of the assessment template. For more information, see  subscribe-to-event and  unsubscribe-from-event .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/ListEventSubscriptions>`_


========
Synopsis
========

::

    list-event-subscriptions
  [--resource-arn <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-arn`` (string)


  The ARN of the assessment template for which you want to list the existing event subscriptions.

  

``--next-token`` (string)


  You can use this parameter when paginating results. Set the value of this parameter to null on your first call to the **list-event-subscriptions** action. Subsequent calls to the action fill **nextToken** in the request with the value of **NextToken** from the previous response to continue listing data.

  

``--max-results`` (integer)


  You can use this parameter to indicate the maximum number of items you want in the response. The default value is 10. The maximum value is 500.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list event subscriptions**

The following ``list-event-subscriptions`` command lists all the event subscriptions for the assessment template with the ARN of ``arn:aws:inspector:us-west-2:123456789012:target/0-nvgVhaxX/template/0-7sbz2Kz0``::

  aws inspector list-event-subscriptions --resource-arn arn:aws:inspector:us-west-2:123456789012:target/0-nvgVhaxX/template/0-7sbz2Kz0

Output::

  {
	"subscriptions": [
	  {
		"eventSubscriptions": [
		  {
			"event": "ASSESSMENT_RUN_COMPLETED",
			"subscribedAt": 1459455440.867
		  }
		],
		"resourceArn": "arn:aws:inspector:us-west-2:123456789012:target/0-nvgVhaxX/template/0-7sbz2Kz0",
		"topicArn": "arn:aws:sns:us-west-2:123456789012:exampletopic"
	  }
	]
  }

For more information, see `Amazon Inspector Assessment Templates and Assessment Runs`_ in the *Amazon Inspector* guide.

.. _`Amazon Inspector Assessment Templates and Assessment Runs`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_assessments.html



======
Output
======

subscriptions -> (list)

  

  Details of the returned event subscriptions.

  

  (structure)

    

    This data type is used as a response element in the  list-event-subscriptions action.

    

    resourceArn -> (string)

      

      The ARN of the assessment template that is used during the event for which the SNS notification is sent.

      

      

    topicArn -> (string)

      

      The ARN of the Amazon Simple Notification Service (SNS) topic to which the SNS notifications are sent.

      

      

    eventSubscriptions -> (list)

      

      The list of existing event subscriptions.

      

      (structure)

        

        This data type is used in the  Subscription data type.

        

        event -> (string)

          

          The event for which Amazon Simple Notification Service (SNS) notifications are sent.

          

          

        subscribedAt -> (timestamp)

          

          The time at which  subscribe-to-event is called.

          

          

        

      

    

  

nextToken -> (string)

  

  When a response is generated, if there is more data to be listed, this parameter is present in the response and contains the value to use for the **nextToken** parameter in a subsequent pagination request. If there is no more data to be listed, this parameter is set to null.

  

  

