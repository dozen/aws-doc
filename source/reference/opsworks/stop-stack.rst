[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks stop-stack:


**********
stop-stack
**********



===========
Description
===========



Stops a specified stack.

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/StopStack>`_


========
Synopsis
========

::

    stop-stack
  --stack-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-id`` (string)


  The stack ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To stop a stack's instances**

The following example stops all of a stack's 24/7 instances.
To stop a particular instance, use ``stop-instance``. ::

  aws opsworks --region us-east-1 stop-stack --stack-id 8c428b08-a1a1-46ce-a5f8-feddc43771b8

*Output*: No output.

**More Information**

For more information, see `Stopping an Instance`_ in the *AWS OpsWorks User Guide*.

.. _`Stopping an Instance`: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-starting.html#workinginstances-starting-stop



======
Output
======

None