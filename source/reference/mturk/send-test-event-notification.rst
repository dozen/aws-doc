[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk send-test-event-notification:


****************************
send-test-event-notification
****************************



===========
Description
===========



The ``send-test-event-notification`` operation causes Amazon Mechanical Turk to send a notification message as if a HIT event occurred, according to the provided notification specification. This allows you to test notifications without setting up notifications for a real HIT type and trying to trigger them using the website. When you call this operation, the service attempts to send the test notification immediately. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/SendTestEventNotification>`_


========
Synopsis
========

::

    send-test-event-notification
  --notification <value>
  --test-event-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--notification`` (structure)


  The notification specification to test. This value is identical to the value you would provide to the update-notification-settings operation when you establish the notification specification for a HIT type. 

  



Shorthand Syntax::

    Destination=string,Transport=string,Version=string,EventTypes=string,string




JSON Syntax::

  {
    "Destination": "string",
    "Transport": "Email"|"SQS",
    "Version": "string",
    "EventTypes": ["AssignmentAccepted"|"AssignmentAbandoned"|"AssignmentReturned"|"AssignmentSubmitted"|"AssignmentRejected"|"AssignmentApproved"|"HITCreated"|"HITExpired"|"HITReviewable"|"HITExtended"|"HITDisposed"|"Ping", ...]
  }



``--test-event-type`` (string)


  The event to simulate to test the notification specification. This event is included in the test message even if the notification specification does not include the event type. The notification specification does not filter out the test event. 

  

  Possible values:

  
  *   ``AssignmentAccepted``

  
  *   ``AssignmentAbandoned``

  
  *   ``AssignmentReturned``

  
  *   ``AssignmentSubmitted``

  
  *   ``AssignmentRejected``

  
  *   ``AssignmentApproved``

  
  *   ``HITCreated``

  
  *   ``HITExpired``

  
  *   ``HITReviewable``

  
  *   ``HITExtended``

  
  *   ``HITDisposed``

  
  *   ``Ping``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

