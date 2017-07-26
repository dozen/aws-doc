[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks update-my-user-profile:


**********************
update-my-user-profile
**********************



===========
Description
===========



Updates a user's SSH public key.

 

**Required Permissions** : To use this action, an IAM user must have self-management enabled or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    update-my-user-profile
  [--ssh-public-key <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--ssh-public-key`` (string)


  The user's SSH public key.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To update a user's profile**

The following example updates the ``development`` user's profile to use a specified SSH public key.
The user's AWS credentials are represented by the ``development`` profile in the ``credentials`` file
(``~\.aws\credentials``), and the key is in a ``.pem`` file in the working directory. ::

  aws opsworks --region us-east-1 --profile development update-my-user-profile --ssh-public-key file://development_key.pem

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*: None.

**More Information**

For more information, see `Editing AWS OpsWorks User Settings`_ in the *AWS OpsWorks User Guide*.

.. _`Editing AWS OpsWorks User Settings`: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users-manage-edit.html



======
Output
======

None

.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
