[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-ssh-public-key:


******************
get-ssh-public-key
******************



===========
Description
===========



Retrieves the specified SSH public key, including metadata about the key.

 

The SSH public key retrieved by this action is used only for authenticating the associated IAM user to an AWS CodeCommit repository. For more information about using SSH keys to authenticate to an AWS CodeCommit repository, see `Set up AWS CodeCommit for SSH Connections <http://docs.aws.amazon.com/codecommit/latest/userguide/setting-up-credentials-ssh.html>`_ in the *AWS CodeCommit User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/GetSSHPublicKey>`_


========
Synopsis
========

::

    get-ssh-public-key
  --user-name <value>
  --ssh-public-key-id <value>
  --encoding <value>
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

  

``--encoding`` (string)


  Specifies the public key encoding format to use in the response. To retrieve the public key in ssh-rsa format, use ``SSH`` . To retrieve the public key in PEM format, use ``PEM`` .

  

  Possible values:

  
  *   ``SSH``

  
  *   ``PEM``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

SSHPublicKey -> (structure)

  

  A structure containing details about the SSH public key.

  

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

    

    

  

