[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks create-user-profile:


*******************
create-user-profile
*******************



===========
Description
===========



Creates a new user profile.

 

 **Required Permissions** : To use this action, an IAM user must have an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/CreateUserProfile>`_


========
Synopsis
========

::

    create-user-profile
  --iam-user-arn <value>
  [--ssh-username <value>]
  [--ssh-public-key <value>]
  [--allow-self-management | --no-allow-self-management]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--iam-user-arn`` (string)


  The user's IAM ARN; this can also be a federated user's ARN.

  

``--ssh-username`` (string)


  The user's SSH user name. The allowable characters are [a-z], [A-Z], [0-9], '-', and '_'. If the specified name includes other punctuation marks, AWS OpsWorks Stacks removes them. For example, ``my.name`` will be changed to ``myname`` . If you do not specify an SSH user name, AWS OpsWorks Stacks generates one from the IAM user name. 

  

``--ssh-public-key`` (string)


  The user's public SSH key.

  

``--allow-self-management`` | ``--no-allow-self-management`` (boolean)


  Whether users can specify their own SSH public key through the My Settings page. For more information, see `Setting an IAM User's Public SSH Key <http://docs.aws.amazon.com/opsworks/latest/userguide/security-settingsshkey.html>`_ .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a user profile**

You import an AWS Identity and Access Manager (IAM) user into AWS OpsWorks by calling `create-user-profile` to create a user profile.
The following example creates a user profile for the cli-user-test IAM user, who
is identified by Amazon Resource Name (ARN). The example assigns the user an SSH username of ``myusername`` and enables self management,
which allows the user to specify an SSH public key. ::

  aws opsworks --region us-east-1 create-user-profile --iam-user-arn arn:aws:iam::123456789102:user/cli-user-test --ssh-username myusername --allow-self-management

*Output*::

  {
    "IamUserArn": "arn:aws:iam::123456789102:user/cli-user-test"
  }

**Tip**: This command imports an IAM user into AWS OpsWorks, but only with the permissions that are
granted by the attached policies. You can grant per-stack AWS OpsWorks permissions by using the ``set-permissions`` command.

**More Information**

For more information, see `Importing Users into AWS OpsWorks`_ in the *AWS OpsWorks User Guide*.

.. _`Importing Users into AWS OpsWorks`: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users-manage-import.html



======
Output
======

IamUserArn -> (string)

  

  The user's IAM ARN.

  

  

