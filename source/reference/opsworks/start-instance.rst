[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks start-instance:


**************
start-instance
**************



===========
Description
===========



Starts a specified instance. For more information, see `Starting, Stopping, and Rebooting Instances`_ .

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    start-instance
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

**To start an instance**

The following ``start-instance`` command starts a specified 24/7 instance. ::

  aws opsworks start-instance --instance-id f705ee48-9000-4890-8bd3-20eb05825aaf

**Note**: AWS OpsWorks CLI commands should set the region to us-east-1 regardless of the stack's location.

*Output*: None. Use describe-instances_ to check the instance's status.

.. _describe-instances: http://docs.aws.amazon.com/cli/latest/reference/opsworks/describe-instances.html

**Tip** You can start every offline instance in a stack with one command by calling start-stack_.

.. _start-stack: http://docs.aws.amazon.com/cli/latest/reference/opsworks/start-stack.html

**More Information**

For more information, see `Manually Starting, Stopping, and Rebooting 24/7 Instances`_ in the *AWS OpsWorks User Guide*.

.. _`Manually Starting, Stopping, and Rebooting 24/7 Instances`: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-starting.html



======
Output
======

None

.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
.. _Starting, Stopping, and Rebooting Instances: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-starting.html
