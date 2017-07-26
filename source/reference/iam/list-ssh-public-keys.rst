[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-ssh-public-keys:


********************
list-ssh-public-keys
********************



===========
Description
===========



Returns information about the SSH public keys associated with the specified IAM user. If there are none, the action returns an empty list.

 

The SSH public keys returned by this action are used only for authenticating the IAM user to an AWS CodeCommit repository. For more information about using SSH keys to authenticate to an AWS CodeCommit repository, see `Set up AWS CodeCommit for SSH Connections`_ in the *AWS CodeCommit User Guide* .

 

Although each user is limited to a small number of keys, you can still paginate the results using the ``MaxItems`` and ``Marker`` parameters.



========
Synopsis
========

::

    list-ssh-public-keys
  [--user-name <value>]
  [--marker <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the IAM user to list SSH public keys for. If none is specified, the UserName field is determined implicitly based on the AWS access key used to sign the request.

  

``--marker`` (string)


  Use this parameter only when paginating results and only after you receive a response indicating that the results are truncated. Set it to the value of the ``Marker`` element in the response that you received to indicate where the next call should start.

  

``--max-items`` (integer)


  Use this only when paginating results to indicate the maximum number of items you want in the response. If additional items exist beyond the maximum you specify, the ``IsTruncated`` response element is ``true`` .

   

  This parameter is optional. If you do not include it, it defaults to 100. Note that IAM might return fewer results, even when there are more results available. In that case, the ``IsTruncated`` response element returns ``true`` and ``Marker`` contains a value to include in the subsequent call that tells the service where to continue from. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

SSHPublicKeys -> (list)

  

  A list of SSH public keys.

  

  (structure)

    

    Contains information about an SSH public key, without the key's body or fingerprint.

     

    This data type is used as a response element in the  list-ssh-public-keys action.

    

    UserName -> (string)

      

      The name of the IAM user associated with the SSH public key.

      

      

    SSHPublicKeyId -> (string)

      

      The unique identifier for the SSH public key.

      

      

    Status -> (string)

      

      The status of the SSH public key. ``Active`` means the key can be used for authentication with an AWS CodeCommit repository. ``Inactive`` means the key cannot be used.

      

      

    UploadDate -> (timestamp)

      

      The date and time, in `ISO 8601 date-time format`_ , when the SSH public key was uploaded.

      

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

  

  

Marker -> (string)

  

  When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  



.. _ISO 8601 date-time format: http://www.iso.org/iso/iso8601
.. _Set up AWS CodeCommit for SSH Connections: http://docs.aws.amazon.com/codecommit/latest/userguide/setting-up-credentials-ssh.html
