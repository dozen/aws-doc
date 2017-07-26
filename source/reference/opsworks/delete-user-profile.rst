[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks delete-user-profile:


*******************
delete-user-profile
*******************



===========
Description
===========



Deletes a user profile.

 

**Required Permissions** : To use this action, an IAM user must have an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    delete-user-profile
  --iam-user-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--iam-user-arn`` (string)


  The user's IAM ARN.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a user profile and remove an IAM user from AWS OpsWorks**

The following example deletes the user profile for a specified AWS Identity and Access Management
(IAM) user, who
is identified by Amazon Resource Name (ARN). The operation removes the user from AWS OpsWorks, but
does not delete the IAM user. You must use the IAM console, CLI, or API for that task. ::

  aws opsworks --region us-east-1 delete-user-profile --iam-user-arn arn:aws:iam::123456789102:user/cli-user-test

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*: None.

**More Information**

For more information, see `Importing Users into AWS OpsWorks`_ in the *AWS OpsWorks User Guide*.

.. _`Importing Users into AWS OpsWorks`: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users-manage-import.html



======
Output
======

None

.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
