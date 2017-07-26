[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier initiate-job:


************
initiate-job
************



===========
Description
===========



This operation initiates a job of the specified type. In this release, you can initiate a job to retrieve either an archive or a vault inventory (a list of archives in a vault). 

 

Retrieving data from Amazon Glacier is a two-step process: 

 

 
* Initiate a retrieval job. 

.. note::

  A data retrieval policy can cause your initiate retrieval job request to fail with a PolicyEnforcedException exception. For more information about data retrieval policies, see `Amazon Glacier Data Retrieval Policies`_ . For more information about the PolicyEnforcedException exception, see `Error Responses`_ . 

 
 
* After the job completes, download the bytes.
 

 

The retrieval request is executed asynchronously. When you initiate a retrieval job, Amazon Glacier creates a job and returns a job ID in the response. When Amazon Glacier completes the job, you can get the job output (archive or inventory data). For information about getting job output, see  get-job-output operation. 

 

The job must complete before you can get its output. To determine when a job is complete, you have the following options:

 

 
* **Use Amazon SNS Notification** You can specify an Amazon Simple Notification Service (Amazon SNS) topic to which Amazon Glacier can post a notification after the job is completed. You can specify an SNS topic per job request. The notification is sent only after Amazon Glacier completes the job. In addition to specifying an SNS topic per job request, you can configure vault notifications for a vault so that job notifications are always sent. For more information, see  set-vault-notifications . 
 
* **Get job details** You can make a  describe-job request to obtain job status information while a job is in progress. However, it is more efficient to use an Amazon SNS notification to determine when a job is complete. 
 

 

.. note::

  

  The information you get via notification is same that you get by calling  describe-job .

  

 

If for a specific event, you add both the notification configuration on the vault and also specify an SNS topic in your initiate job request, Amazon Glacier sends both notifications. For more information, see  set-vault-notifications .

 

An AWS account has full permission to perform all operations (actions). However, AWS Identity and Access Management (IAM) users don't have any permissions by default. You must grant them explicit permission to perform specific actions. For more information, see `Access Control Using AWS Identity and Access Management (IAM)`_ .

 

**About the Vault Inventory** 

 

Amazon Glacier prepares an inventory for each vault periodically, every 24 hours. When you initiate a job for a vault inventory, Amazon Glacier returns the last inventory for the vault. The inventory data you get might be up to a day or two days old. Also, the initiate inventory job might take some time to complete before you can download the vault inventory. So you do not want to retrieve a vault inventory for each vault operation. However, in some scenarios, you might find the vault inventory useful. For example, when you upload an archive, you can provide an archive description but not an archive name. Amazon Glacier provides you a unique archive ID, an opaque vault-name of characters. So, you might maintain your own database that maps archive names to their corresponding Amazon Glacier assigned archive IDs. You might find the vault inventory useful in the event you need to reconcile information in your database with the actual vault inventory. 

 

**Range Inventory Retrieval** 

 

You can limit the number of inventory items retrieved by filtering on the archive creation date or by setting a limit.

 

*Filtering by Archive Creation Date* 

 

You can retrieve inventory items for archives created between ``StartDate`` and ``EndDate`` by specifying values for these parameters in the **initiate-job** request. Archives created on or after the ``StartDate`` and before the ``EndDate`` will be returned. If you only provide the ``StartDate`` without the ``EndDate`` , you will retrieve the inventory for all archives created on or after the ``StartDate`` . If you only provide the ``EndDate`` without the ``StartDate`` , you will get back the inventory for all archives created before the ``EndDate`` .

 

*Limiting Inventory Items per Retrieval* 

 

You can limit the number of inventory items returned by setting the ``Limit`` parameter in the **initiate-job** request. The inventory job output will contain inventory items up to the specified ``Limit`` . If there are more inventory items available, the result is paginated. After a job is complete you can use the  describe-job operation to get a marker that you use in a subsequent **initiate-job** request. The marker will indicate the starting point to retrieve the next set of inventory items. You can page through your entire inventory by repeatedly making **initiate-job** requests with the marker from the previous **describe-job** output, until you get a marker from **describe-job** that returns null, indicating that there are no more inventory items available.

 

You can use the ``Limit`` parameter together with the date range parameters.

 

**About Ranged Archive Retrieval** 

 

You can initiate an archive retrieval for the whole archive or a range of the archive. In the case of ranged archive retrieval, you specify a byte range to return or the whole archive. The range specified must be megabyte (MB) aligned, that is the range start value must be divisible by 1 MB and range end value plus 1 must be divisible by 1 MB or equal the end of the archive. If the ranged archive retrieval is not megabyte aligned, this operation returns a 400 response. Furthermore, to ensure you get checksum values for data you download using Get Job Output API, the range must be tree hash aligned. 

 

An AWS account has full permission to perform all operations (actions). However, AWS Identity and Access Management (IAM) users don't have any permissions by default. You must grant them explicit permission to perform specific actions. For more information, see `Access Control Using AWS Identity and Access Management (IAM)`_ .

 

For conceptual information and the underlying REST API, go to `Initiate a Job`_ and `Downloading a Vault Inventory`_  



========
Synopsis
========

::

    initiate-job
  --account-id <value>
  --vault-name <value>
  [--job-parameters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID of the account that owns the vault. You can either specify an AWS account ID or optionally a single apos``-`` apos (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you use an account ID, do not include any hyphens (apos-apos) in the ID.

  

``--vault-name`` (string)


  The name of the vault.

  

``--job-parameters`` (structure)


  Provides options for specifying job information.

  



Shorthand Syntax::

    Format=string,Type=string,ArchiveId=string,Description=string,SNSTopic=string,RetrievalByteRange=string,InventoryRetrievalParameters={StartDate=string,EndDate=string,Limit=string,Marker=string}




JSON Syntax::

  {
    "Format": "string",
    "Type": "string",
    "ArchiveId": "string",
    "Description": "string",
    "SNSTopic": "string",
    "RetrievalByteRange": "string",
    "InventoryRetrievalParameters": {
      "StartDate": "string",
      "EndDate": "string",
      "Limit": "string",
      "Marker": "string"
    }
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON vault-name provided. The JSON vault-name follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command initiates a job to get an inventory of the vault ``my-vault``::

  aws glacier initiate-job --account-id - --vault-name my-vault --job-parameters '{"Type": "inventory-retrieval"}'

Output::

  {
      "location": "/0123456789012/vaults/my-vault/jobs/zbxcm3Z_3z5UkoroF7SuZKrxgGoDc3RloGduS7Eg-RO47Yc6FxsdGBgf_Q2DK5Ejh18CnTS5XW4_XqlNHS61dsO4CnMW",
      "jobId": "zbxcm3Z_3z5UkoroF7SuZKrxgGoDc3RloGduS7Eg-RO47Yc6FxsdGBgf_Q2DK5Ejh18CnTS5XW4_XqlNHS61dsO4CnMW"
  }

Amazon Glacier requires an account ID argument when performing operations, but you can use a hyphen to specify the in-use account.

The following command initiates a job to retrieve an archive from the vault ``my-vault``::

  aws glacier initiate-job --account-id - --vault-name my-vault --job-parameters file://job-archive-retrieval.json

``job-archive-retrieval.json`` is a JSON file in the local folder that specifies the type of job, archive ID, and some optional parameters::

  {
    "Type": "archive-retrieval",
    "ArchiveId": "kKB7ymWJVpPSwhGP6ycSOAekp9ZYe_--zM_mw6k76ZFGEIWQX-ybtRDvc2VkPSDtfKmQrj0IRQLSGsNuDp-AJVlu2ccmDSyDUmZwKbwbpAdGATGDiB3hHO0bjbGehXTcApVud_wyDw",
    "Description": "Retrieve archive on 2015-07-17",
    "SNSTopic": "arn:aws:sns:us-west-2:0123456789012:my-topic"
  }

Archive IDs are available in the output of ``aws glacier upload-archive`` and ``aws glacier get-job-output``.

Output::

  {
      "location": "/011685312445/vaults/mwunderl/jobs/l7IL5-EkXyEY9Ws95fClzIbk2O5uLYaFdAYOi-azsX_Z8V6NH4yERHzars8wTKYQMX6nBDI9cMNHzyZJO59-8N9aHWav",
      "jobId": "l7IL5-EkXy2O5uLYaFdAYOiEY9Ws95fClzIbk-azsX_Z8V6NH4yERHzars8wTKYQMX6nBDI9cMNHzyZJO59-8N9aHWav"
  }

See `Initiate Job`_ in the *Amazon Glacier API Reference* for details on the job parameters format.

.. _`Initiate Job`: http://docs.aws.amazon.com/amazonglacier/latest/dev/api-initiate-job-post.html

======
Output
======

location -> (string)

  

  The relative URI path of the job.

  

  

jobId -> (string)

  

  The ID of the job.

  

  



.. _Error Responses: http://docs.aws.amazon.com/amazonglacier/latest/dev/api-error-responses.html
.. _Amazon Glacier Data Retrieval Policies: http://docs.aws.amazon.com/amazonglacier/latest/dev/data-retrieval-policy.html
.. _Downloading a Vault Inventory: http://docs.aws.amazon.com/amazonglacier/latest/dev/vault-inventory.html
.. _Initiate a Job: http://docs.aws.amazon.com/amazonglacier/latest/dev/api-initiate-job-post.html
.. _Access Control Using AWS Identity and Access Management (IAM): http://docs.aws.amazon.com/amazonglacier/latest/dev/using-iam-with-amazon-glacier.html
