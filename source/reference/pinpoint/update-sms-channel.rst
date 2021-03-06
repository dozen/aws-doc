[ :ref:`aws <cli:aws>` . :ref:`pinpoint <cli:aws pinpoint>` ]

.. _cli:aws pinpoint update-sms-channel:


******************
update-sms-channel
******************



===========
Description
===========

Update an SMS channel

========
Synopsis
========

::

    update-sms-channel
  --application-id <value>
  --sms-channel-request <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-id`` (string)


``--sms-channel-request`` (structure)
SMS Channel Request



Shorthand Syntax::

    Enabled=boolean,SenderId=string




JSON Syntax::

  {
    "Enabled": true|false,
    "SenderId": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

SMSChannelResponse -> (structure)

  SMS Channel Response.

  ApplicationId -> (string)

    Application id

    

  CreationDate -> (string)

    The date that the settings were last updated in ISO 8601 format.

    

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

    Platform type. Will be "SMS"

    

  SenderId -> (string)

    Sender identifier of your messages.

    

  ShortCode -> (string)

    The short code registered with the phone provider.

    

  Version -> (integer)

    Version of channel

    

  

