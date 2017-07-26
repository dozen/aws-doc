[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk update-notification-settings:


****************************
update-notification-settings
****************************



===========
Description
===========



The ``update-notification-settings`` operation creates, updates, disables or re-enables notifications for a HIT type. If you call the update-notification-settings operation for a HIT type that already has a notification specification, the operation replaces the old specification with a new one. You can call the update-notification-settings operation to enable or disable notifications for the HIT type, without having to modify the notification specification itself by providing updates to the Active status without specifying a new notification specification. To change the Active status of a HIT type's notifications, the HIT type must already have a notification specification, or one must be provided in the same call to ``update-notification-settings`` . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/UpdateNotificationSettings>`_


========
Synopsis
========

::

    update-notification-settings
  --hit-type-id <value>
  [--notification <value>]
  [--active | --no-active]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--hit-type-id`` (string)


  The ID of the HIT type whose notification specification is being updated. 

  

``--notification`` (structure)


  The notification specification for the HIT type. 

  



Shorthand Syntax::

    Destination=string,Transport=string,Version=string,EventTypes=string,string




JSON Syntax::

  {
    "Destination": "string",
    "Transport": "Email"|"SQS",
    "Version": "string",
    "EventTypes": ["AssignmentAccepted"|"AssignmentAbandoned"|"AssignmentReturned"|"AssignmentSubmitted"|"AssignmentRejected"|"AssignmentApproved"|"HITCreated"|"HITExpired"|"HITReviewable"|"HITExtended"|"HITDisposed"|"Ping", ...]
  }



``--active`` | ``--no-active`` (boolean)


  Specifies whether notifications are sent for HITs of this HIT type, according to the notification specification. You must specify either the Notification parameter or the Active parameter for the call to update-notification-settings to succeed. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

