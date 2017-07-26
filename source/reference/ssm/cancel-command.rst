[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm cancel-command:


**************
cancel-command
**************



===========
Description
===========



Attempts to cancel the command specified by the Command ID. There is no guarantee that the command will be terminated and the underlying process stopped.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/CancelCommand>`_


========
Synopsis
========

::

    cancel-command
  --command-id <value>
  [--instance-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To attempt to cancel a command**

This example attempts to cancel a command. There is no output if the operation succeeds.

Command::

  aws ssm cancel-command --command-id "662add3d-5831-4a10-b64a-f2ff3a577858"


======
Output
======

