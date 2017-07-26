[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds restore-from-snapshot:


*********************
restore-from-snapshot
*********************



===========
Description
===========



Restores a directory using an existing directory snapshot.

 

When you restore a directory from a snapshot, any changes made to the directory after the snapshot date are overwritten.

 

This action returns as soon as the restore operation is initiated. You can monitor the progress of the restore operation by calling the  describe-directories operation with the directory identifier. When the **DirectoryDescription.Stage** value changes to ``Active`` , the restore operation is complete.



========
Synopsis
========

::

    restore-from-snapshot
  --snapshot-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--snapshot-id`` (string)


  The identifier of the snapshot to restore from.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

