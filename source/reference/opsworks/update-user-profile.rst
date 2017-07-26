[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks update-user-profile:


*******************
update-user-profile
*******************



===========
Description
===========



Updates a specified user profile.

 

 **Required Permissions** : To use this action, an IAM user must have an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/UpdateUserProfile>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--iam-user-arn`` (string)


  The user IAM ARN. This can also be a federated user's ARN.

  

``--ssh-username`` (string)


  The user's SSH user name. The allowable characters are [a-z], [A-Z], [0-9], '-', and '_'. If the specified name includes other punctuation marks, AWS OpsWorks Stacks removes them. For example, ``my.name`` will be changed to ``myname`` . If you do not specify an SSH user name, AWS OpsWorks Stacks generates one from the IAM user name. 

  

``--ssh-public-key`` (string)


  The user's new SSH public key.

  

``--allow-self-management`` | ``--no-allow-self-management`` (boolean)


  Whether users can specify their own SSH public key through the My Settings page. For more information, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/security-settingsshkey.html>`_ .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None