[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway create-nfs-file-share:


*********************
create-nfs-file-share
*********************



===========
Description
===========



Creates a file share on an existing file gateway. In Storage Gateway, a file share is a file system mount point backed by Amazon S3 cloud storage. Storage Gateway exposes file shares using a Network File System (NFS) interface. This operation is only supported in the file gateway architecture.

 

.. warning::

   

  File gateway requires AWS Security Token Service (AWS STS) to be activated to enable you create a file share. Make sure AWS STS is activated in the region you are creating your file gateway in. If AWS STS is not activated in the region, activate it. For information about how to activate AWS STS, see Activating and Deactivating AWS STS in an AWS Region in the AWS Identity and Access Management User Guide. 

   

  File gateway does not support creating hard or symbolic links on a file share.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/CreateNFSFileShare>`_


========
Synopsis
========

::

    create-nfs-file-share
  --client-token <value>
  [--nfs-file-share-defaults <value>]
  --gateway-arn <value>
  [--kms-encrypted | --no-kms-encrypted]
  [--kms-key <value>]
  --role <value>
  --location-arn <value>
  [--default-storage-class <value>]
  [--client-list <value>]
  [--squash <value>]
  [--read-only | --no-read-only]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--client-token`` (string)


  A unique string value that you supply that is used by file gateway to ensure idempotent file share creation.

  

``--nfs-file-share-defaults`` (structure)


  File share default values. Optional.

  



Shorthand Syntax::

    FileMode=string,DirectoryMode=string,GroupId=long,OwnerId=long




JSON Syntax::

  {
    "FileMode": "string",
    "DirectoryMode": "string",
    "GroupId": long,
    "OwnerId": long
  }



``--gateway-arn`` (string)


  The Amazon Resource Name (ARN) of the file gateway on which you want to create a file share.

  

``--kms-encrypted`` | ``--no-kms-encrypted`` (boolean)


  True to use Amazon S3 server side encryption with your own AWS KMS key, or false to use a key managed by Amazon S3. Optional.

  

``--kms-key`` (string)


  The KMS key used for Amazon S3 server side encryption. This value can only be set when KmsEncrypted is true. Optional.

  

``--role`` (string)


  The ARN of the AWS Identity and Access Management (IAM) role that a file gateway assumes when it accesses the underlying storage. 

  

``--location-arn`` (string)


  The ARN of the backed storage used for storing file data. 

  

``--default-storage-class`` (string)


  The default storage class for objects put into an Amazon S3 bucket by file gateway. Possible values are S3_STANDARD or S3_STANDARD_IA. If this field is not populated, the default value S3_STANDARD is used. Optional.

  

``--client-list`` (list)


  The list of clients that are allowed to access the file gateway. The list must contain either valid IP addresses or valid CIDR blocks. 

  



Syntax::

  "string" "string" ...



``--squash`` (string)


  Maps a user to anonymous user. Valid options are the following: 

   

   
  * "RootSquash" - Only root is mapped to anonymous user. 
   
  * "NoSquash" - No one is mapped to anonymous user. 
   
  * "AllSquash" - Everyone is mapped to anonymous user. 
   

  

``--read-only`` | ``--no-read-only`` (boolean)


  Sets the write status of a file share: "true" if the write status is read-only, and otherwise "false".

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

FileShareARN -> (string)

  

  The Amazon Resource Name (ARN) of the newly created file share. 

  

  

