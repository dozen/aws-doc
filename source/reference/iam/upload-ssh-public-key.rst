[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam upload-ssh-public-key:


*********************
upload-ssh-public-key
*********************



===========
Description
===========



Uploads an SSH public key and associates it with the specified IAM user.

 

The SSH public key uploaded by this action can be used only for authenticating the associated IAM user to an AWS CodeCommit repository. For more information about using SSH keys to authenticate to an AWS CodeCommit repository, see `Set up AWS CodeCommit for SSH Connections <http://docs.aws.amazon.com/codecommit/latest/userguide/setting-up-credentials-ssh.html>`_ in the *AWS CodeCommit User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/UploadSSHPublicKey>`_


========
Synopsis
========

::

    upload-ssh-public-key
  --user-name <value>
  --ssh-public-key-body <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-name`` (string)


  The name of the IAM user to associate the SSH public key with.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--ssh-public-key-body`` (string)


  The SSH public key. The public key must be encoded in ssh-rsa format or PEM format.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ used to validate this parameter is a string of characters consisting of any printable ASCII character ranging from the space character (\u0020) through end of the ASCII character range as well as the printable characters in the Basic Latin and Latin-1 Supplement character set (through \u00FF). It also includes the special characters tab (\u0009), line feed (\u000A), and carriage return (\u000D).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

    

    The date and time, in `ISO 8601 date-time format <http://www.iso.org/iso/iso8601>`_ , when the SSH public key was uploaded.

    

    

  

