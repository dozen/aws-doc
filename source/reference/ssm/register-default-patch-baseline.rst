[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm register-default-patch-baseline:


*******************************
register-default-patch-baseline
*******************************



===========
Description
===========



Defines the default patch baseline.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/RegisterDefaultPatchBaseline>`_


========
Synopsis
========

::

    register-default-patch-baseline
  --baseline-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--baseline-id`` (string)


  The ID of the patch baseline that should be the default patch baseline.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To set the default patch baseline**

This example registers a patch baseline as the default patch baseline.

Command::

  aws ssm register-default-patch-baseline --baseline-id "pb-08b654cf9b9681f04"

Output::

  {
	"BaselineId":"pb-08b654cf9b9681f04"
  }


======
Output
======

BaselineId -> (string)

  

  The ID of the default patch baseline.

  

  

