[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds delete-snapshot:


***************
delete-snapshot
***************



===========
Description
===========



Deletes a directory snapshot.



========
Synopsis
========

::

    delete-snapshot
  --snapshot-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--snapshot-id`` (string)


  The identifier of the directory snapshot to be deleted.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

SnapshotId -> (string)

  

  The identifier of the directory snapshot that was deleted.

  

  

