[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks set-permission:


**************
set-permission
**************



===========
Description
===========



Specifies a user's permissions. For more information, see `Security and Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/workingsecurity.html>`_ .

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/SetPermission>`_


========
Synopsis
========

::

    set-permission
  --stack-id <value>
  --iam-user-arn <value>
  [--allow-ssh | --no-allow-ssh]
  [--allow-sudo | --no-allow-sudo]
  [--level <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-id`` (string)


  The stack ID.

  

``--iam-user-arn`` (string)


  The user's IAM ARN. This can also be a federated user's ARN.

  

``--allow-ssh`` | ``--no-allow-ssh`` (boolean)


  The user is allowed to use SSH to communicate with the instance.

  

``--allow-sudo`` | ``--no-allow-sudo`` (boolean)


  The user is allowed to use **sudo** to elevate privileges.

  

``--level`` (string)


  The user's permission level, which must be set to one of the following strings. You cannot set your own permissions level.

   

   
  * ``deny``   
   
  * ``show``   
   
  * ``deploy``   
   
  * ``manage``   
   
  * ``iam_only``   
   

   

  For more information on the permissions associated with these levels, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To grant per-stack AWS OpsWorks permission levels**

When you import an AWS Identity and Access Management (IAM) user into AWS OpsWorks by calling ``create-user-profile``, the user has only those
permissions that are granted by the attached IAM policies.
You can grant AWS OpsWorks permissions by modifying a user's policies.
However, it is often easier to import a user and then use the ``set-permission`` command to grant
the user one of the standard permission levels for each stack to which the user will need access.

The following example grants permission for the specified stack for a user, who
is identified by Amazon Resource Name (ARN). The example grants the user a Manage permissions level, with sudo and SSH privileges on the stack's
instances. ::

  aws opsworks set-permission --region us-east-1 --stack-id 71c7ca72-55ae-4b6a-8ee1-a8dcded3fa0f --level manage  --iam-user-arn arn:aws:iam::123456789102:user/cli-user-test --allow-ssh --allow-sudo
  

*Output*: None.

**More Information**

For more information, see `Granting AWS OpsWorks Users Per-Stack Permissions`_ in the *AWS OpsWorks User Guide*.

.. _`Granting AWS OpsWorks Users Per-Stack Permissions`: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users-console.html



======
Output
======

None