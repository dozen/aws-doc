[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier describe-job:


************
describe-job
************



===========
Description
===========



This operation returns information about a job you previously initiated, including the job initiation date, the user who initiated the job, the job status code/message and the Amazon SNS topic to notify after Amazon Glacier completes the job. For more information about initiating a job, see  initiate-job . 

 

.. note::

  

  This operation enables you to check the status of your job. However, it is strongly recommended that you set up an Amazon SNS topic and specify it in your initiate job request so that Amazon Glacier can notify the topic after it completes the job. 

  

 

A job ID will not expire for at least 24 hours after Amazon Glacier completes the job. 

 

An AWS account has full permission to perform all operations (actions). However, AWS Identity and Access Management (IAM) users don't have any permissions by default. You must grant them explicit permission to perform specific actions. For more information, see `Access Control Using AWS Identity and Access Management (IAM)`_ .

 

For information about the underlying REST API, go to `Working with Archives in Amazon Glacier`_ in the *Amazon Glacier Developer Guide* . 



========
Synopsis
========

::

    describe-job
  --account-id <value>
  --vault-name <value>
  --job-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID of the account that owns the vault. You can either specify an AWS account ID or optionally a single apos``-`` apos (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you use an account ID, do not include any hyphens (apos-apos) in the ID. 

  

``--vault-name`` (string)


  The name of the vault.

  

``--job-id`` (string)


  The ID of the job to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON job-id provided. The JSON job-id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command retrieves information about an inventory retrieval job on a vault named ``my-vault``::

  aws glacier describe-job --account-id - --vault-name my-vault --job-id zbxcm3Z_3z5UkoroF7SuZKrxgGoDc3RloGduS7Eg-RO47Yc6FxsdGBgf_Q2DK5Ejh18CnTS5XW4_XqlNHS61dsO4CnMW

Output::

  {
      "InventoryRetrievalParameters": {
          "Format": "JSON"
      },
      "VaultARN": "arn:aws:glacier:us-west-2:0123456789012:vaults/my-vault",
      "Completed": false,
      "JobId": "zbxcm3Z_3z5UkoroF7SuZKrxgGoDc3RloGduS7Eg-RO47Yc6FxsdGBgf_Q2DK5Ejh18CnTS5XW4_XqlNHS61dsO4CnMW",
      "Action": "InventoryRetrieval",
      "CreationDate": "2015-07-17T20:23:41.616Z",
      "StatusCode": "InProgress"
  }

The job ID can be found in the output of ``aws glacier initiate-job`` and ``aws glacier list-jobs``.
Amazon Glacier requires an account ID argument when performing operations, but you can use a hyphen to specify the in-use account.


======
Output
======

JobId -> (string)

  

  An opaque job-id that identifies an Amazon Glacier job.

  

  

JobDescription -> (string)

  

  The job description you provided when you initiated the job.

  

  

Action -> (string)

  

  The job type. It is either ArchiveRetrieval or InventoryRetrieval.

  

  

ArchiveId -> (string)

  

  For an ArchiveRetrieval job, this is the archive ID requested for download. Otherwise, this field is null.

  

  

VaultARN -> (string)

  

  The Amazon Resource Name (ARN) of the vault from which the archive retrieval was requested.

  

  

CreationDate -> (string)

  

  The UTC date when the job was created. A job-id representation of ISO 8601 date format, for example, "2012-03-20T17:03:43.221Z".

  

  

Completed -> (boolean)

  

  The job status. When a job is completed, you get the job's output.

  

  

StatusCode -> (string)

  

  The status code can be InProgress, Succeeded, or Failed, and indicates the status of the job.

  

  

StatusMessage -> (string)

  

  A friendly message that describes the job status.

  

  

ArchiveSizeInBytes -> (long)

  

  For an ArchiveRetrieval job, this is the size in bytes of the archive being requested for download. For the InventoryRetrieval job, the value is null.

  

  

InventorySizeInBytes -> (long)

  

  For an InventoryRetrieval job, this is the size in bytes of the inventory requested for download. For the ArchiveRetrieval job, the value is null.

  

  

SNSTopic -> (string)

  

  An Amazon Simple Notification Service (Amazon SNS) topic that receives notification.

  

  

CompletionDate -> (string)

  

  The UTC time that the archive retrieval request completed. While the job is in progress, the value will be null.

  

  

SHA256TreeHash -> (string)

  

  For an ArchiveRetrieval job, it is the checksum of the archive. Otherwise, the value is null.

   

  The SHA256 tree hash value for the requested range of an archive. If the Initiate a Job request for an archive specified a tree-hash aligned range, then this field returns a value. 

   

  For the specific case when the whole archive is retrieved, this value is the same as the ArchiveSHA256TreeHash value. 

   

  This field is null in the following situations: 

   
  * Archive retrieval jobs that specify a range that is not tree-hash aligned.
   

   

   
  * Archival jobs that specify a range that is equal to the whole archive and the job status is InProgress.
   

   

   
  * Inventory jobs.
   

   

  

  

ArchiveSHA256TreeHash -> (string)

  

  The SHA256 tree hash of the entire archive for an archive retrieval. For inventory retrieval jobs, this field is null. 

  

  

RetrievalByteRange -> (string)

  

  The retrieved byte range for archive retrieval jobs in the form "*StartByteValue* -*EndByteValue* " If no range was specified in the archive retrieval, then the whole archive is retrieved and *StartByteValue* equals 0 and *EndByteValue* equals the size of the archive minus 1. For inventory retrieval jobs this field is null. 

  

  

InventoryRetrievalParameters -> (structure)

  

  Parameters used for range inventory retrieval.

  

  Format -> (string)

    

    The output format for the vault inventory list, which is set by the **initiate-job** request when initiating a job to retrieve a vault inventory. Valid values are "CSV" and "JSON".

    

    

  StartDate -> (string)

    

    The start of the date range in UTC for vault inventory retrieval that includes archives created on or after this date. A job-id representation of ISO 8601 date format, for example, 2013-03-20T17:03:43Z.

    

    

  EndDate -> (string)

    

    The end of the date range in UTC for vault inventory retrieval that includes archives created before this date. A job-id representation of ISO 8601 date format, for example, 2013-03-20T17:03:43Z.

    

    

  Limit -> (string)

    

    Specifies the maximum number of inventory items returned per vault inventory retrieval request. This limit is set when initiating the job with the a **initiate-job** request. 

    

    

  Marker -> (string)

    

    An opaque job-id that represents where to continue pagination of the vault inventory retrieval results. You use the marker in a new **initiate-job** request to obtain additional inventory items. If there are no more inventory items, this value is ``null`` . For more information, see `Range Inventory Retrieval`_ .

    

    

  



.. _Access Control Using AWS Identity and Access Management (IAM): http://docs.aws.amazon.com/amazonglacier/latest/dev/using-iam-with-amazon-glacier.html
.. _Range Inventory Retrieval: http://docs.aws.amazon.com/amazonglacier/latest/dev/api-initiate-job-post.html#api-initiate-job-post-vault-inventory-list-filtering
.. _Working with Archives in Amazon Glacier: http://docs.aws.amazon.com/amazonglacier/latest/dev/api-describe-job-get.html
