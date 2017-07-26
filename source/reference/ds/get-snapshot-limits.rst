[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds get-snapshot-limits:


*******************
get-snapshot-limits
*******************



===========
Description
===========



Obtains the manual snapshot limits for a directory.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/GetSnapshotLimits>`_


========
Synopsis
========

::

    get-snapshot-limits
  --directory-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-id`` (string)


  Contains the identifier of the directory to obtain the limits for.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

SnapshotLimits -> (structure)

  

  A  SnapshotLimits object that contains the manual snapshot limits for the specified directory.

  

  ManualSnapshotsLimit -> (integer)

    

    The maximum number of manual snapshots allowed.

    

    

  ManualSnapshotsCurrentCount -> (integer)

    

    The current number of manual snapshots of the directory.

    

    

  ManualSnapshotsLimitReached -> (boolean)

    

    Indicates if the manual snapshot limit has been reached.

    

    

  

