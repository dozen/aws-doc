[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks deregister-instance:


*******************
deregister-instance
*******************



===========
Description
===========



Deregister a registered Amazon EC2 or on-premises instance. This action removes the instance from the stack and returns it to your control. This action can not be used with instances that were created with AWS OpsWorks Stacks.

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DeregisterInstance>`_


========
Synopsis
========

::

    deregister-instance
  --instance-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-id`` (string)


  The instance ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To deregister a registered instance from a stack**

The following ``deregister-instance`` command deregisters a registered instance from its stack. ::

  aws opsworks --region us-east-1 deregister-instance --instance-id 4d6d1710-ded9-42a1-b08e-b043ad7af1e2

*Output*: None.

**More Information**

For more information, see `Deregistering a Registered Instance`_ in the *AWS OpsWorks User Guide*.

.. _`Deregistering a Registered Instance`: http://docs.aws.amazon.com/opsworks/latest/userguide/registered-instances-unassign.html



======
Output
======

None