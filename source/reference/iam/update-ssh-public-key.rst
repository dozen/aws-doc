[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam update-ssh-public-key:


*********************
update-ssh-public-key
*********************



===========
Description
===========



Sets the status of an IAM user's SSH public key to active or inactive. SSH public keys that are inactive cannot be used for authentication. This action can be used to disable a user's SSH public key as part of a key rotation work flow.

 

The SSH public key affected by this action is used only for authenticating the associated IAM user to an AWS CodeCommit repository. For more information about using SSH keys to authenticate to an AWS CodeCommit repository, see `Set up AWS CodeCommit for SSH Connections <http://docs.aws.amazon.com/codecommit/latest/userguide/setting-up-credentials-ssh.html>`_ in the *AWS CodeCommit User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/UpdateSSHPublicKey>`_


========
Synopsis
========

::

    update-ssh-public-key
  --user-name <value>
  --ssh-public-key-id <value>
  --status <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-name`` (string)


  The name of the IAM user associated with the SSH public key.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--ssh-public-key-id`` (string)


  The unique identifier for the SSH public key.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters that can consist of any upper or lowercased letter or digit.

  

``--status`` (string)


  The status to assign to the SSH public key. ``Active`` means the key can be used for authentication with an AWS CodeCommit repository. ``Inactive`` means the key cannot be used.

  

  Possible values:

  
  *   ``Active``

  
  *   ``Inactive``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None