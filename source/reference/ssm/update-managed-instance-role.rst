[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm update-managed-instance-role:


****************************
update-managed-instance-role
****************************



===========
Description
===========



Assigns or changes an Amazon Identity and Access Management (IAM) role to the managed instance.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/UpdateManagedInstanceRole>`_


========
Synopsis
========

::

    update-managed-instance-role
  --instance-id <value>
  --iam-role <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-id`` (string)


  The ID of the managed instance where you want to update the role.

  

``--iam-role`` (string)


  The IAM role you want to assign or change.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To update the role of a managed instance**

This example updates the role of a managed instance. There is no output if the command succeeds.

Command::

  aws ssm update-managed-instance-role --instance-id "mi-08ab247cdf1046573" --iam-role "AutomationRole"


======
Output
======

