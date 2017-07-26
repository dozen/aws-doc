[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm cancel-command:


**************
cancel-command
**************



===========
Description
===========



Attempts to cancel the command specified by the Command ID. There is no guarantee that the command will be terminated and the underlying process stopped.



========
Synopsis
========

::

    cancel-command
  --command-id <value>
  [--instance-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--command-id`` (string)
The ID of the command you want to cancel.

``--instance-ids`` (list)


  (Optional) A list of instance IDs on which you want to cancel the command. If not provided, the command is canceled on every instance on which it was requested.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

