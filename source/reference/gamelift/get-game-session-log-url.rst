[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift get-game-session-log-url:


************************
get-game-session-log-url
************************



===========
Description
===========



Retrieves the location of stored game session logs for a specified game session. When a game session is terminated, Amazon GameLift automatically stores the logs in Amazon S3. Use this URL to download the logs.

 

.. note::

  

  See the `AWS Service Limits`_ page for maximum log file sizes. Log files that exceed this limit are not saved.

  



========
Synopsis
========

::

    get-game-session-log-url
  --game-session-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--game-session-id`` (string)


  Unique identifier for a game session. Specify the game session you want to get logs for.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

PreSignedUrl -> (string)

  

  Location of the requested game session logs, available for download.

  

  



.. _AWS Service Limits: http://docs.aws.amazon.com/general/latest/gr/aws_service_limits.html#limits_gamelift
