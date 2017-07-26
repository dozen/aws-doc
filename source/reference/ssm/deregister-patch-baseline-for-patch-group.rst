[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm deregister-patch-baseline-for-patch-group:


*****************************************
deregister-patch-baseline-for-patch-group
*****************************************



===========
Description
===========



Removes a patch group from a patch baseline.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DeregisterPatchBaselineForPatchGroup>`_


========
Synopsis
========

::

    deregister-patch-baseline-for-patch-group
  --baseline-id <value>
  --patch-group <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--baseline-id`` (string)


  The ID of the patch baseline to deregister the patch group from.

  

``--patch-group`` (string)


  The name of the patch group that should be deregistered from the patch baseline.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To deregister a patch group from a patch baseline**

This example deregisters a patch group from a patch baseline.

Command::

  aws ssm deregister-patch-baseline-for-patch-group --patch-group "Production" --baseline-id "arn:aws:ssm:us-west-1:812345678901:patchbaseline/pb-0ca44a362f8afc725"
  
Output::

  {
	"PatchGroup":"Production",
	"BaselineId":"arn:aws:ssm:us-west-1:812345678901:patchbaseline/pb-0ca44a362f8afc725"
  }


======
Output
======

BaselineId -> (string)

  

  The ID of the patch baseline the patch group was deregistered from.

  

  

PatchGroup -> (string)

  

  The name of the patch group deregistered from the patch baseline.

  

  

