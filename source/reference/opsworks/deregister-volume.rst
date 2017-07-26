[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks deregister-volume:


*****************
deregister-volume
*****************



===========
Description
===========



Deregisters an Amazon EBS volume. The volume can then be registered by another stack. For more information, see `Resource Management <http://docs.aws.amazon.com/opsworks/latest/userguide/resources.html>`_ .

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DeregisterVolume>`_


========
Synopsis
========

::

    deregister-volume
  --volume-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--volume-id`` (string)


  The AWS OpsWorks Stacks volume ID, which is the GUID that AWS OpsWorks Stacks assigned to the instance when you registered the volume with the stack, not the Amazon EC2 volume ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To deregister an Amazon EBS volume**

The following example deregisters an EBS volume from its stack.
The volume is identified by its volume ID, which is the GUID that AWS OpsWorks assigned when
you registered the volume with the stack, not the EC2 volume ID. ::

  aws opsworks deregister-volume --region us-east-1 --volume-id 5c48ef52-3144-4bf5-beaa-fda4deb23d4d

*Output*: None.

**More Information**

For more information, see `Deregistering Amazon EBS Volumes`_ in the *AWS OpsWorks User Guide*.

.. _`Deregistering Amazon EBS Volumes`: http://docs.aws.amazon.com/opsworks/latest/userguide/resources-dereg.html#resources-dereg-ebs


======
Output
======

None