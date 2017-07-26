[ :ref:`aws <cli:aws>` . :ref:`pinpoint <cli:aws pinpoint>` ]

.. _cli:aws pinpoint update-email-channel:


********************
update-email-channel
********************



===========
Description
===========

Update an email channel

========
Synopsis
========

::

    update-email-channel
  --application-id <value>
  --email-channel-request <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-id`` (string)


``--email-channel-request`` (structure)
Email Channel Request



Shorthand Syntax::

    Enabled=boolean,FromAddress=string,Identity=string,RoleArn=string




JSON Syntax::

  {
    "Enabled": true|false,
    "FromAddress": "string",
    "Identity": "string",
    "RoleArn": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

EmailChannelResponse -> (structure)

  Email Channel Response.

  ApplicationId -> (string)

    Application id

    

  CreationDate -> (string)

    The date that the settings were last updated in ISO 8601 format.

    

  Enabled -> (boolean)

    If the channel is enabled for sending messages.

    

  FromAddress -> (string)

    The email address used to send emails from.

    

  Id -> (string)

    Channel ID. Not used, only for backwards compatibility.

    

  Identity -> (string)

    The ARN of an identity verified with SES.

    

  IsArchived -> (boolean)

    Is this channel archived

    

  LastModifiedBy -> (string)

    Who last updated this entry

    

  LastModifiedDate -> (string)

    Last date this was updated

    

  Platform -> (string)

    Platform type. Will be "EMAIL"

    

  RoleArn -> (string)

    The ARN of an IAM Role used to submit events to Mobile Analytics' event ingestion service

    

  Version -> (integer)

    Version of channel

    

  

