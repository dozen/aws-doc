[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks start-instance:


**************
start-instance
**************



===========
Description
===========



Starts a specified instance. For more information, see `Starting, Stopping, and Rebooting Instances <http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-starting.html>`_ .

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/StartInstance>`_


========
Synopsis
========

::

    start-instance
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

**To start an instance**

The following ``start-instance`` command starts a specified 24/7 instance. ::

  aws opsworks start-instance --instance-id f705ee48-9000-4890-8bd3-20eb05825aaf

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