[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-patch-group-state:


**************************
describe-patch-group-state
**************************



===========
Description
===========



Returns high-level aggregated patch compliance state for a patch group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DescribePatchGroupState>`_


========
Synopsis
========

::

    describe-patch-group-state
  --patch-group <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--patch-group`` (string)


  The name of the patch group whose patch snapshot should be retrieved.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get the state of a patch group**

This example gets the high-level patch compliance summary for a patch group.

Command::

  aws ssm describe-patch-group-state --patch-group "Production"

Output::

  {
    "InstancesWithNotApplicablePatches": 0,
    "InstancesWithMissingPatches": 0,
    "InstancesWithFailedPatches": 1,
    "InstancesWithInstalledOtherPatches": 4,
    "Instances": 4,
    "InstancesWithInstalledPatches": 3
  }


======
Output
======

Instances -> (integer)

  

  The number of instances in the patch group.

  

  

InstancesWithInstalledPatches -> (integer)

  

  The number of instances with installed patches.

  

  

InstancesWithInstalledOtherPatches -> (integer)

  

  The number of instances with patches installed that aren't defined in the patch baseline.

  

  

InstancesWithMissingPatches -> (integer)

  

  The number of instances with missing patches from the patch baseline.

  

  

InstancesWithFailedPatches -> (integer)

  

  The number of instances with patches from the patch baseline that failed to install.

  

  

InstancesWithNotApplicablePatches -> (integer)

  

  The number of instances with patches that aren't applicable.

  

  

