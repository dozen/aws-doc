[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm delete-patch-baseline:


*********************
delete-patch-baseline
*********************



===========
Description
===========



Deletes a patch baseline.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DeletePatchBaseline>`_


========
Synopsis
========

::

    delete-patch-baseline
  --baseline-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--baseline-id`` (string)


  The ID of the patch baseline to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a patch baseline**

This example deletes a patch baseline.

Command::

  aws ssm delete-patch-baseline --baseline-id "pb-045f10b4f382baeda"

Output::

  {
    "BaselineId": "pb-045f10b4f382baeda"
  }


======
Output
======

BaselineId -> (string)

  

  The ID of the deleted patch baseline.

  

  

