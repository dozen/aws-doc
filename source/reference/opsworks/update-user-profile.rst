[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks update-user-profile:


*******************
update-user-profile
*******************



===========
Description
===========



Updates a specified user profile.

 

**Required Permissions** : To use this action, an IAM user must have an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    update-user-profile
  --iam-user-arn <value>
  [--ssh-username <value>]
  [--ssh-public-key <value>]
  [--allow-self-management | --no-allow-self-management]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--iam-user-arn`` (string)


  The user IAM ARN.

  

``--ssh-username`` (string)


  The user's SSH user name. The allowable characters are [a-z], [A-Z], [0-9], '-', and '_'. If the specified name includes other punctuation marks, AWS OpsWorks removes them. For example, ``my.name`` will be changed to ``myname`` . If you do not specify an SSH user name, AWS OpsWorks generates one from the IAM user name. 

  

``--ssh-public-key`` (string)


  The user's new SSH public key.

  

``--allow-self-management`` | ``--no-allow-self-management`` (boolean)


  Whether users can specify their own SSH public key through the My Settings page. For more information, see `Managing User Permissions`_ .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/security-settingsshkey.html
