[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks unassign-instance:


*****************
unassign-instance
*****************



===========
Description
===========



Unassigns a registered instance from all of it's layers. The instance remains in the stack as an unassigned instance and can be assigned to another layer, as needed. You cannot use this action with instances that were created with AWS OpsWorks.

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    unassign-instance
  --instance-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-id`` (string)


  The instance ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To unassign a registered instance from its layers**

The following ``unassign-instance`` command unassigns an instance from its attached layers. ::

  aws opsworks --region us-east-1 unassign-instance --instance-id 4d6d1710-ded9-42a1-b08e-b043ad7af1e2

**Note**: AWS OpsWorks CLI commands should set the region to us-east-1 regardless of the stack's location.

**Output**: None.

**More Information**

For more information, see `Unassigning a Registered Instance`_ in the *AWS OpsWorks User Guide*.

.. _`Unassigning a Registered Instance`: http://docs.aws.amazon.com/opsworks/latest/userguide/registered-instances-unassign.html



======
Output
======

None

.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
