[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm create-hapg:


***********
create-hapg
***********



===========
Description
===========



Creates a high-availability partition group. A high-availability partition group is a group of partitions that spans multiple physical HSMs.



========
Synopsis
========

::

    create-hapg
  --label <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--label`` (string)


  The label of the new high-availability partition group.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

HapgArn -> (string)

  

  The ARN of the high-availability partition group.

  

  

