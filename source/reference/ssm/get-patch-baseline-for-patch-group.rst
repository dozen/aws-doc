[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm get-patch-baseline-for-patch-group:


**********************************
get-patch-baseline-for-patch-group
**********************************



===========
Description
===========



Retrieves the patch baseline that should be used for the specified patch group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/GetPatchBaselineForPatchGroup>`_


========
Synopsis
========

::

    get-patch-baseline-for-patch-group
  --patch-group <value>
  [--operating-system <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--patch-group`` (string)


  The name of the patch group whose patch baseline should be retrieved.

  

``--operating-system`` (string)


  Returns he operating system rule specified for patch groups using the patch baseline.

  

  Possible values:

  
  *   ``WINDOWS``

  
  *   ``AMAZON_LINUX``

  
  *   ``UBUNTU``

  
  *   ``REDHAT_ENTERPRISE_LINUX``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To display the patch baseline for a patch group**

This example displays the patch baseline for a patch group.

Command::

  aws ssm get-patch-baseline-for-patch-group --patch-group "Production"

Output::

  {
    "PatchGroup": "Production",
    "BaselineId": "pb-045f10b4f382baeda"
  }


======
Output
======

BaselineId -> (string)

  

  The ID of the patch baseline that should be used for the patch group.

  

  

PatchGroup -> (string)

  

  The name of the patch group.

  

  

OperatingSystem -> (string)

  

  The operating system rule specified for patch groups using the patch baseline.

  

  

