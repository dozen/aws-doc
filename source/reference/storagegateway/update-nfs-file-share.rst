[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway update-nfs-file-share:


*********************
update-nfs-file-share
*********************



===========
Description
===========



Updates a file share. This operation is only supported in the file gateway architecture.

 

.. note::

   

  To leave a file share field unchanged, set the corresponding input field to null.

   

 

Updates the following file share setting:

 

 
* Default storage class for your S3 bucket 
 
* Metadata defaults for your S3 bucket 
 
* Allowed NFS clients for your file share 
 
* squash settings 
 
* Write status of your file share 
 

 

.. note::

   

  To leave a file share field unchanged, set the corresponding input field to null. This operation is only supported in file gateways.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/UpdateNFSFileShare>`_


========
Synopsis
========

::

    update-nfs-file-share
  --file-share-arn <value>
  [--kms-encrypted | --no-kms-encrypted]
  [--kms-key <value>]
  [--nfs-file-share-defaults <value>]
  [--default-storage-class <value>]
  [--client-list <value>]
  [--squash <value>]
  [--read-only | --no-read-only]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--file-share-arn`` (string)


  The Amazon Resource Name (ARN) of the file share to be updated. 

  

``--kms-encrypted`` | ``--no-kms-encrypted`` (boolean)


  True to use Amazon S3 server side encryption with your own AWS KMS key, or false to use a key managed by Amazon S3. Optional. 

  

``--kms-key`` (string)


  The KMS key used for Amazon S3 server side encryption. This value can only be set when KmsEncrypted is true. Optional. 

  

``--nfs-file-share-defaults`` (structure)


  The default values for the file share. Optional.

  



Shorthand Syntax::

    FileMode=string,DirectoryMode=string,GroupId=long,OwnerId=long




JSON Syntax::

  {
    "FileMode": "string",
    "DirectoryMode": "string",
    "GroupId": long,
    "OwnerId": long
  }



``--default-storage-class`` (string)


  The default storage class for objects put into an Amazon S3 bucket by a file gateway. Possible values are S3_STANDARD or S3_STANDARD_IA. If this field is not populated, the default value S3_STANDARD is used. Optional.

  

``--client-list`` (list)


  The list of clients that are allowed to access the file gateway. The list must contain either valid IP addresses or valid CIDR blocks.

  



Syntax::

  "string" "string" ...



``--squash`` (string)


  The user mapped to anonymous user. Valid options are the following:

   

   
  * "RootSquash" - Only root is mapped to anonymous user. 
   
  * "NoSquash" - No one is mapped to anonymous user 
   
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

  

  The Amazon Resource Name (ARN) of the updated file share. 

  

  

