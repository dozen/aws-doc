[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks unassign-volume:


***************
unassign-volume
***************



===========
Description
===========



Unassigns an assigned Amazon EBS volume. The volume remains registered with the stack. For more information, see `Resource Management <http://docs.aws.amazon.com/opsworks/latest/userguide/resources.html>`_ .

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/UnassignVolume>`_


========
Synopsis
========

::

    unassign-volume
  --volume-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--volume-id`` (string)


  The volume ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To unassign a volume from its instance**

The following example unassigns a registered Amazon Elastic Block Store (Amazon EBS) volume from its instance.
The volume is identified by its volume ID, which is the GUID that AWS OpsWorks assigns when
you register the volume with a stack, not the Amazon Elastic Compute Cloud (Amazon EC2) volume ID. ::

  aws opsworks --region us-east-1 unassign-volume --volume-id 8430177d-52b7-4948-9c62-e195af4703df

*Output*: None.

**More Information**

For more information, see `Unassigning Amazon EBS Volumes`_ in the *AWS OpsWorks User Guide*.

.. _`Unassigning Amazon EBS Volumes`: http://docs.aws.amazon.com/opsworks/latest/userguide/resources-detach.html#resources-detach-ebs



======
Output
======

None