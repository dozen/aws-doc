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



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/RestoreFromSnapshot>`_


========
Synopsis
========

::

    restore-from-snapshot
  --snapshot-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--snapshot-id`` (string)


  The identifier of the snapshot to restore from.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

