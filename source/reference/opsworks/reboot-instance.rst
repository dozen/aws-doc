[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks reboot-instance:


***************
reboot-instance
***************



===========
Description
===========



Reboots a specified instance. For more information, see `Starting, Stopping, and Rebooting Instances <http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-starting.html>`_ .

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/RebootInstance>`_


========
Synopsis
========

::

    reboot-instance
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

**To reboot an instance**

The following example reboots an instance. ::

  aws opsworks --region us-east-1 reboot-instance --instance-id dfe18b02-5327-493d-91a4-c5c0c448927f

*Output*: None.

**More Information**

For more information, see `Rebooting an Instance`_ in the *AWS OpsWorks User Guide*.

.. _`Rebooting an Instance`: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-starting.html#workinginstances-starting-reboot



======
Output
======

None