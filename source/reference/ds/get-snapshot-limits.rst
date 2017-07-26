[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds get-snapshot-limits:


*******************
get-snapshot-limits
*******************



===========
Description
===========



Obtains the manual snapshot limits for a directory.



========
Synopsis
========

::

    get-snapshot-limits
  --directory-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--directory-id`` (string)


  Contains the identifier of the directory to obtain the limits for.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

    

    

  

