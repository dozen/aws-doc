[ :ref:`aws <cli:aws>` . :ref:`pinpoint <cli:aws pinpoint>` ]

.. _cli:aws pinpoint get-gcm-channel:


***************
get-gcm-channel
***************



===========
Description
===========

Returns information about the GCM channel for an app.

========
Synopsis
========

::

    get-gcm-channel
  --application-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-id`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

GCMChannelResponse -> (structure)

  Google Cloud Messaging channel definition

  ApplicationId -> (string)

    The ID of the application to which the channel applies.

    

  CreationDate -> (string)

    When was this segment created

    

  Credential -> (string)

    The GCM API key from Google.

    

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

    The platform type. Will be GCM

    

  Version -> (integer)

    Version of channel

    

  

