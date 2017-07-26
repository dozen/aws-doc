[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks stop-instance:


*************
stop-instance
*************



===========
Description
===========



Stops a specified instance. When you stop a standard instance, the data disappears and must be reinstalled when you restart the instance. You can stop an Amazon EBS-backed instance without losing data. For more information, see `Starting, Stopping, and Rebooting Instances <http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-starting.html>`_ .

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/StopInstance>`_


========
Synopsis
========

::

    stop-instance
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

**To stop an instance**

The following example stops a specified instance, which is identified by its instance ID.
You can obtain an instance ID by going to the instance's details page on the AWS OpsWorks console or by
running the ``describe-instances`` command. ::

  aws opsworks stop-instance --region us-east-1 --instance-id 3a21cfac-4a1f-4ce2-a921-b2cfba6f7771

You can restart a stopped instance by calling ``start-instance`` or by deleting the instance by calling
``delete-instance``.

*Output*: None.

**More Information**

For more information, see `Stopping an Instance`_ in the *AWS OpsWorks User Guide*.

.. _`Stopping an Instance`: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-starting.html#workinginstances-starting-stop




======
Output
======

None