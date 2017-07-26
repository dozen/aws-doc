[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway describe-nfs-file-shares:


************************
describe-nfs-file-shares
************************



===========
Description
===========



Gets a description for one or more file shares from a file gateway. This operation is only supported in file gateways.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/DescribeNFSFileShares>`_


========
Synopsis
========

::

    describe-nfs-file-shares
  --file-share-arn-list <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--file-share-arn-list`` (list)


  An array containing the Amazon Resource Name (ARN) of each file share to be described. 

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

NFSFileShareInfoList -> (list)

  

  An array containing a description for each requested file share. 

  

  (structure)

    

    The Unix file permissions and ownership information assigned, by default, to native S3 objects when file gateway discovers them in S3 buckets. This operation is only supported in file gateways.

    

    NFSFileShareDefaults -> (structure)

      

      Describes file share default values. Files and folders stored as Amazon S3 objects in S3 buckets don't, by default, have Unix file permissions assigned to them. Upon discovery in an S3 bucket by Storage Gateway, the S3 objects that represent files and folders are assigned these default Unix permissions. This operation is only supported in the file gateway architecture.

      

      FileMode -> (string)

        

        The Unix file mode in the form "nnnn". For example, "0666" represents the default file mode inside the file share. The default value is 0666. 

        

        

      DirectoryMode -> (string)

        

        The Unix directory mode in the form "nnnn". For example, "0666" represents the default access mode for all directories inside the file share. The default value is 0777.

        

        

      GroupId -> (long)

        

        The default group ID for the file share (unless the files have another group ID specified). The default value is nfsnobody. 

        

        

      OwnerId -> (long)

        

        The default owner ID for files in the file share (unless the files have another owner ID specified). The default value is nfsnobody. 

        

        

      

    FileShareARN -> (string)

      

      The Amazon Resource Name (ARN) of the file share. 

      

      

    FileShareId -> (string)

      

      The ID of the file share. 

      

      

    FileShareStatus -> (string)

      

      The status of the file share. Possible values are CREATING, UPDATING, AVAILABLE and DELETING. 

      

      

    GatewayARN -> (string)

      

      The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

      

      

    KMSEncrypted -> (boolean)

      

      True to use Amazon S3 server side encryption with your own KMS key, or false to use a key managed by Amazon S3. Optional. 

      

      

    KMSKey -> (string)

      

      The ARN of the KMS key used for Amazon S3 server side encryption. 

      

      

    Path -> (string)

      

      The file share path used by the NFS client to identify the mount point. 

      

      

    Role -> (string)

      

      The ARN of the IAM role that file gateway assumes when it accesses the underlying storage. 

      

      

    LocationARN -> (string)

      

      The ARN of the backend storage used for storing file data. 

      

      

    DefaultStorageClass -> (string)

      

      The default storage class for objects put into an Amazon S3 bucket by file gateway. Possible values are S3_STANDARD or S3_STANDARD_IA. If this field is not populated, the default value S3_STANDARD is used. Optional.

      

      

    ClientList -> (list)

      

      The list of clients that are allowed to access the file gateway. The list must contain either valid IP addresses or valid CIDR blocks. 

      

      (string)

        

        

      

    Squash -> (string)

      

      The user mapped to anonymous user. Valid options are the following: 

       

       
      * "RootSquash" - Only root is mapped to anonymous user. 
       
      * "NoSquash" - No one is mapped to anonymous user 
       
      * "AllSquash" - Everyone is mapped to anonymous user. 
       

      

      

    ReadOnly -> (boolean)

      

      A value that indicates whether the write status of a file share is read-only: "true" if write status is read-only, and otherwise "false".

      

      

    

  

