[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks unassign-volume:


***************
unassign-volume
***************



===========
Description
===========



Unassigns an assigned Amazon EBS volume. The volume remains registered with the stack. For more information, see `Resource Management`_ .

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    unassign-volume
  --volume-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--volume-id`` (string)


  The volume ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To unassign a volume from its instance**

The following example unassigns a registered Amazon Elastic Block Store (Amazon EBS) volume from its instance.
The volume is identified by its volume ID, which is the GUID that AWS OpsWorks assigns when
you register the volume with a stack, not the Amazon Elastic Compute Cloud (Amazon EC2) volume ID. ::

  aws opsworks --region us-east-1 unassign-volume --volume-id 8430177d-52b7-4948-9c62-e195af4703df

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*: None.

**More Information**

For more information, see `Unassigning Amazon EBS Volumes`_ in the *AWS OpsWorks User Guide*.

.. _`Unassigning Amazon EBS Volumes`: http://docs.aws.amazon.com/opsworks/latest/userguide/resources-detach.html#resources-detach-ebs



======
Output
======

None

.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
.. _Resource Management: http://docs.aws.amazon.com/opsworks/latest/userguide/resources.html
