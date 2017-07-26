[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-ssh-public-key:


*********************
delete-ssh-public-key
*********************



===========
Description
===========



Deletes the specified SSH public key.

 

The SSH public key deleted by this action is used only for authenticating the associated IAM user to an AWS CodeCommit repository. For more information about using SSH keys to authenticate to an AWS CodeCommit repository, see `Set up AWS CodeCommit for SSH Connections`_ in the *AWS CodeCommit User Guide* .



========
Synopsis
========

::

    delete-ssh-public-key
  --user-name <value>
  --ssh-public-key-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the IAM user associated with the SSH public key.

  

``--ssh-public-key-id`` (string)


  The unique identifier for the SSH public key.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _Set up AWS CodeCommit for SSH Connections: http://docs.aws.amazon.com/codecommit/latest/userguide/setting-up-credentials-ssh.html
