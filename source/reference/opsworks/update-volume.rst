[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks update-volume:


*************
update-volume
*************



===========
Description
===========



Updates an Amazon EBS volume's name or mount point. For more information, see `Resource Management`_ .

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    update-volume
  --volume-id <value>
  [--name <value>]
  [--mount-point <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--volume-id`` (string)


  The volume ID.

  

``--name`` (string)


  The new name.

  

``--mount-point`` (string)


  The new mount point.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To update a registered volume**

The following example updates a registered Amazon Elastic Block Store (Amazon EBS) volume's mount point.
The volume is identified by its volume ID, which is the GUID that AWS OpsWorks assigns to the volume when
you register it with a stack, not the Amazon Elastic Compute Cloud (Amazon EC2) volume ID.::

  aws opsworks --region us-east-1 update-volume --volume-id 8430177d-52b7-4948-9c62-e195af4703df --mount-point /mnt/myvol

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
