[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-ssh-public-key:


******************
get-ssh-public-key
******************



===========
Description
===========



Retrieves the specified SSH public key, including metadata about the key.

 

The SSH public key retrieved by this action is used only for authenticating the associated IAM user to an AWS CodeCommit repository. For more information about using SSH keys to authenticate to an AWS CodeCommit repository, see `Set up AWS CodeCommit for SSH Connections`_ in the *AWS CodeCommit User Guide* .



========
Synopsis
========

::

    get-ssh-public-key
  --user-name <value>
  --ssh-public-key-id <value>
  --encoding <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the IAM user associated with the SSH public key.

  

``--ssh-public-key-id`` (string)


  The unique identifier for the SSH public key.

  

``--encoding`` (string)


  Specifies the public key encoding format to use in the response. To retrieve the public key in ssh-rsa format, use ``SSH`` . To retrieve the public key in PEM format, use ``PEM`` .

  

  Possible values:

  
  *   ``SSH``

  
  *   ``PEM``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

SSHPublicKey -> (structure)

  

  Information about the SSH public key.

  

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
