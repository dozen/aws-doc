[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds create-snapshot:


***************
create-snapshot
***************



===========
Description
===========



Creates a snapshot of a Simple AD directory.

 

.. note::

   

  You cannot take snapshots of AD Connector directories.

   



========
Synopsis
========

::

    create-snapshot
  --directory-id <value>
  [--name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--directory-id`` (string)


  The identifier of the directory to take a snapshot of.

  

``--name`` (string)


  The descriptive name to apply to the snapshot.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

SnapshotId -> (string)

  

  The identifier of the snapshot that was created.

  

  

