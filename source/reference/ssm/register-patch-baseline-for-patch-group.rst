[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm register-patch-baseline-for-patch-group:


***************************************
register-patch-baseline-for-patch-group
***************************************



===========
Description
===========



Registers a patch baseline for a patch group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/RegisterPatchBaselineForPatchGroup>`_


========
Synopsis
========

::

    register-patch-baseline-for-patch-group
  --baseline-id <value>
  --patch-group <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--baseline-id`` (string)


  The ID of the patch baseline to register the patch group with.

  

``--patch-group`` (string)


  The name of the patch group that should be registered with the patch baseline.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To register a patch baseline for a patch group**

This example registers a patch baseline for a patch group.

Command::

  aws ssm register-patch-baseline-for-patch-group --baseline-id "pb-045f10b4f382baeda" --patch-group "Production"

Output::

  {
    "PatchGroup": "Production",
    "BaselineId": "pb-045f10b4f382baeda"
  }


======
Output
======

BaselineId -> (string)

  

  The ID of the patch baseline the patch group was registered with.

  

  

PatchGroup -> (string)

  

  The name of the patch group registered with the patch baseline.

  

  

