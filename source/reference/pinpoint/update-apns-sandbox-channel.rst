[ :ref:`aws <cli:aws>` . :ref:`pinpoint <cli:aws pinpoint>` ]

.. _cli:aws pinpoint update-apns-sandbox-channel:


***************************
update-apns-sandbox-channel
***************************



===========
Description
===========

Update an APNS sandbox channel

========
Synopsis
========

::

    update-apns-sandbox-channel
  --apns-sandbox-channel-request <value>
  --application-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--apns-sandbox-channel-request`` (structure)
Apple Development Push Notification Service channel definition.



Shorthand Syntax::

    Certificate=string,Enabled=boolean,PrivateKey=string




JSON Syntax::

  {
    "Certificate": "string",
    "Enabled": true|false,
    "PrivateKey": "string"
  }



``--application-id`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

APNSSandboxChannelResponse -> (structure)

  Apple Development Push Notification Service channel definition.

  ApplicationId -> (string)

    Application id

    

  CreationDate -> (string)

    When was this segment created

    

  Enabled -> (boolean)

    If the channel is enabled for sending messages.

    

  Id -> (string)

    Channel ID. Not used, only for backwards compatibility.

    

  IsArchived -> (boolean)

    Is this channel archived

    

  LastModifiedBy -> (string)

    Who last updated this entry

    

  LastModifiedDate -> (string)

    Last date this was updated

    

  Platform -> (string)

    The platform type. Will be APNS.

    

  Version -> (integer)

    Version of channel

    

  

