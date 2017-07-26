[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam upload-ssh-public-key:


*********************
upload-ssh-public-key
*********************



===========
Description
===========



Uploads an SSH public key and associates it with the specified IAM user.

 

The SSH public key uploaded by this action can be used only for authenticating the associated IAM user to an AWS CodeCommit repository. For more information about using SSH keys to authenticate to an AWS CodeCommit repository, see `Set up AWS CodeCommit for SSH Connections`_ in the *AWS CodeCommit User Guide* .



========
Synopsis
========

::

    upload-ssh-public-key
  --user-name <value>
  --ssh-public-key-body <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the IAM user to associate the SSH public key with.

  

``--ssh-public-key-body`` (string)


  The SSH public key. The public key must be encoded in ssh-rsa format or PEM format.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

SSHPublicKey -> (structure)

  

  Contains information about the SSH public key.

  

  UserName -> (string)

    

    The name of the IAM user associated with the SSH public key.

    

    

  SSHPublicKeyId -> (string)

    

    The unique identifier for the SSH public key.

    

    

  Fingerprint -> (string)

    

    The MD5 message digest of the SSH public key.

    

    

  SSHPublicKeyBody -> (string)

    

    The SSH public key.

    

    

  Status -> (string)

    

    The status of the SSH public key. ``Active`` means the key can be used for authentication with an AWS CodeCommit repository. ``Inactive`` means the key cannot be used.

    

    

  UploadDate -> (timestamp)

    

    The date and time, in `ISO 8601 date-time format`_ , when the SSH public key was uploaded.

    

    

  



.. _ISO 8601 date-time format: http://www.iso.org/iso/iso8601
.. _Set up AWS CodeCommit for SSH Connections: http://docs.aws.amazon.com/codecommit/latest/userguide/setting-up-credentials-ssh.html
