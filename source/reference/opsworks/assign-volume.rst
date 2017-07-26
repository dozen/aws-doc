[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks assign-volume:


*************
assign-volume
*************



===========
Description
===========



Assigns one of the stack's registered Amazon EBS volumes to a specified instance. The volume must first be registered with the stack by calling  register-volume . After you register the volume, you must call  update-volume to specify a mount point before calling ``assign-volume`` . For more information, see `Resource Management`_ .

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    assign-volume
  --volume-id <value>
  [--instance-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--volume-id`` (string)


  The volume ID.

  

``--instance-id`` (string)


  The instance ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To assign a registered volume to an instance**

The following example assigns a registered Amazon Elastic Block Store (Amazon EBS) volume to an instance.
The volume is identified by its volume ID, which is the GUID that AWS OpsWorks assigns when
you register the volume with a stack, not the Amazon Elastic Compute Cloud (Amazon EC2) volume ID.
Before you run ``assign-volume``, you must first run ``update-volume`` to assign a mount point to the volume. ::

  aws opsworks --region us-east-1 assign-volume --instance-id 4d6d1710-ded9-42a1-b08e-b043ad7af1e2 --volume-id 26cf1d32-6876-42fa-bbf1-9cadc0bff938

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*: None.

**More Information**

For more information, see `Assigning Amazon EBS Volumes to an Instance`_ in the *AWS OpsWorks User Guide*.

.. _`Assigning Amazon EBS Volumes to an Instance`: http://docs.aws.amazon.com/opsworks/latest/userguide/resources-attach.html#resources-attach-ebs



======
Output
======

None

.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
.. _Resource Management: http://docs.aws.amazon.com/opsworks/latest/userguide/resources.html
