[ :ref:`aws <cli:aws>` . :ref:`appstream <cli:aws appstream>` ]

.. _cli:aws appstream create-streaming-url:


********************
create-streaming-url
********************



===========
Description
===========



Creates a URL to start an AppStream 2.0 streaming session for a user. By default, the URL is valid only for 1 minute from the time that it is generated.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/appstream-2016-12-01/CreateStreamingURL>`_


========
Synopsis
========

::

    create-streaming-url
  --stack-name <value>
  --fleet-name <value>
  --user-id <value>
  [--application-id <value>]
  [--validity <value>]
  [--session-context <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-name`` (string)


  The stack for which the URL is generated.

  

``--fleet-name`` (string)


  The fleet for which the URL is generated.

  

``--user-id`` (string)


  A unique user ID for whom the URL is generated.

  

``--application-id`` (string)


  The ID of the application that must be launched after the session starts.

  

``--validity`` (long)


  The duration up to which the URL returned by this action is valid. The input can be any numeric value in seconds between 1 and 604800 seconds.

  

``--session-context`` (string)


  The sessionContext of the streaming URL.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

StreamingURL -> (string)

  

  The URL to start the AppStream 2.0 streaming session.

  

  

Expires -> (timestamp)

  

  Elapsed seconds after the Unix epoch, when this URL expires.

  

  

