[ :ref:`aws <cli:aws>` . :ref:`pinpoint <cli:aws pinpoint>` ]

.. _cli:aws pinpoint send-messages:


*************
send-messages
*************



===========
Description
===========

Send a batch of messages

========
Synopsis
========

::

    send-messages
  --application-id <value>
  --message-request <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-id`` (string)


``--message-request`` (structure)
Send message request.



JSON Syntax::

  {
    "Addresses": {"string": {
          "BodyOverride": "string",
          "ChannelType": "GCM"|"APNS"|"APNS_SANDBOX"|"ADM"|"SMS"|"EMAIL",
          "Context": {"string": "string"
            ...},
          "RawContent": "string",
          "Substitutions": {"string": ["string", ...]
            ...},
          "TitleOverride": "string"
        }
      ...},
    "Context": {"string": "string"
      ...},
    "MessageConfiguration": {
      "APNSMessage": {
        "Action": "OPEN_APP"|"DEEP_LINK"|"URL",
        "Badge": integer,
        "Body": "string",
        "Category": "string",
        "Data": {"string": "string"
          ...},
        "MediaUrl": "string",
        "RawContent": "string",
        "SilentPush": true|false,
        "Sound": "string",
        "Substitutions": {"string": ["string", ...]
          ...},
        "ThreadId": "string",
        "Title": "string",
        "Url": "string"
      },
      "DefaultMessage": {
        "Body": "string",
        "Substitutions": {"string": ["string", ...]
          ...}
      },
      "DefaultPushNotificationMessage": {
        "Action": "OPEN_APP"|"DEEP_LINK"|"URL",
        "Body": "string",
        "Data": {"string": "string"
          ...},
        "SilentPush": true|false,
        "Substitutions": {"string": ["string", ...]
          ...},
        "Title": "string",
        "Url": "string"
      },
      "GCMMessage": {
        "Action": "OPEN_APP"|"DEEP_LINK"|"URL",
        "Body": "string",
        "CollapseKey": "string",
        "Data": {"string": "string"
          ...},
        "IconReference": "string",
        "ImageIconUrl": "string",
        "ImageUrl": "string",
        "RawContent": "string",
        "RestrictedPackageName": "string",
        "SilentPush": true|false,
        "SmallImageIconUrl": "string",
        "Sound": "string",
        "Substitutions": {"string": ["string", ...]
          ...},
        "Title": "string",
        "Url": "string"
      },
      "SMSMessage": {
        "Body": "string",
        "MessageType": "TRANSACTIONAL"|"PROMOTIONAL",
        "SenderId": "string",
        "Substitutions": {"string": ["string", ...]
          ...}
      }
    }
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

MessageResponse -> (structure)

  Send message response.

  ApplicationId -> (string)

    Application id of the message.

    

  RequestId -> (string)

    Original request Id for which this message was delivered.

    

  Result -> (map)

    A map containing a multi part response for each address, with the address as the key(Email address, phone number or push token) and the result as the value.

    key -> (string)

      

      

    value -> (structure)

      The result from sending a message to an address.

      DeliveryStatus -> (string)

        Delivery status of message.

        

      StatusCode -> (integer)

        Downstream service status code.

        

      StatusMessage -> (string)

        Status message for message delivery.

        

      UpdatedToken -> (string)

        If token was updated as part of delivery. (This is GCM Specific)

        

      

    

  

