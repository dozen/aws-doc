[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam update-ssh-public-key:


*********************
update-ssh-public-key
*********************



===========
Description
===========



Sets the status of the specified SSH public key to active or inactive. SSH public keys that are inactive cannot be used for authentication. This action can be used to disable a user's SSH public key as part of a key rotation work flow. 

 

The SSH public key affected by this action is used only for authenticating the associated IAM user to an AWS CodeCommit repository. For more information about using SSH keys to authenticate to an AWS CodeCommit repository, see `Set up AWS CodeCommit for SSH Connections`_ in the *AWS CodeCommit User Guide* .



========
Synopsis
========

::

    update-ssh-public-key
  --user-name <value>
  --ssh-public-key-id <value>
  --status <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the IAM user associated with the SSH public key.

  

``--ssh-public-key-id`` (string)


  The unique identifier for the SSH public key.

  

``--status`` (string)


  The status to assign to the SSH public key. ``Active`` means the key can be used for authentication with an AWS CodeCommit repository. ``Inactive`` means the key cannot be used.

  

  Possible values:

  
  *   ``Active``

  
  *   ``Inactive``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _Set up AWS CodeCommit for SSH Connections: http://docs.aws.amazon.com/codecommit/latest/userguide/setting-up-credentials-ssh.html
