[ :ref:`aws <cli:aws>` . :ref:`glacier <cli:aws glacier>` ]

.. _cli:aws glacier list-jobs:


*********
list-jobs
*********



===========
Description
===========



This operation lists jobs for a vault, including jobs that are in-progress and jobs that have recently finished.

 

.. note::

   

  Amazon Glacier retains recently completed jobs for a period before deleting them; however, it eventually removes completed jobs. The output of completed jobs can be retrieved. Retaining completed jobs for a period of time after they have completed enables you to get a job output in the event you miss the job completion notification or your first attempt to download it fails. For example, suppose you start an archive retrieval job to download an archive. After the job completes, you start to download the archive but encounter a network error. In this scenario, you can retry and download the archive while the job exists.

   

 

To retrieve an archive or retrieve a vault inventory from Amazon Glacier, you first initiate a job, and after the job completes, you download the data. For an archive retrieval, the output is the archive data. For an inventory retrieval, it is the inventory list. The List Job operation returns a list of these jobs sorted by job initiation time.

 

The List Jobs operation supports pagination. You should always check the response ``Marker`` field. If there are no more jobs to list, the ``Marker`` field is set to ``null`` . If there are more jobs to list, the ``Marker`` field is set to a non-null value, which you can use to continue the pagination of the list. To return a list of jobs that begins at a specific job, set the marker request parameter to the ``Marker`` value for that job that you obtained from a previous List Jobs request.

 

You can set a maximum limit for the number of jobs returned in the response by specifying the ``limit`` parameter in the request. The default limit is 1000. The number of jobs returned might be fewer than the limit, but the number of returned jobs never exceeds the limit.

 

Additionally, you can filter the jobs list returned by specifying the optional ``statuscode`` parameter or ``completed`` parameter, or both. Using the ``statuscode`` parameter, you can specify to return only jobs that match either the ``InProgress`` , ``Succeeded`` , or ``Failed`` status. Using the ``completed`` parameter, you can specify to return only jobs that were completed (``true`` ) or jobs that were not completed (``false`` ).

 

For the underlying REST API, see `List Jobs <http://docs.aws.amazon.com/amazonglacier/latest/dev/api-jobs-get.html>`_ . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/glacier-2012-06-01/ListJobs>`_


``list-jobs`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``JobList``


========
Synopsis
========

::

    list-jobs
  --account-id <value>
  --vault-name <value>
  [--statuscode <value>]
  [--completed <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--account-id`` (string)


  The ``AccountId`` value is the AWS account ID of the account that owns the vault. You can either specify an AWS account ID or optionally a single '``-`` ' (hyphen), in which case Amazon Glacier uses the AWS account ID associated with the credentials used to sign the request. If you use an account ID, do not include any hyphens ('-') in the ID. 

  

``--vault-name`` (string)


  The name of the vault.

  

``--statuscode`` (string)


  The type of job status to return. You can specify the following values: ``InProgress`` , ``Succeeded`` , or ``Failed`` .

  

``--completed`` (string)


  The state of the jobs to return. You can specify ``true`` or ``false`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON account-id provided. The JSON account-id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (string)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (string)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command lists in-progress and recently completed jobs for a vault named ``my-vault``::

  aws glacier list-jobs --account-id - --vault-name my-vault

Output::

  {
      "JobList": [
          {
              "VaultARN": "arn:aws:glacier:us-west-2:0123456789012:vaults/my-vault",
              "RetrievalByteRange": "0-3145727",
              "SNSTopic": "arn:aws:sns:us-west-2:0123456789012:my-vault",
              "Completed": false,
              "SHA256TreeHash": "9628195fcdbcbbe76cdde932d4646fa7de5f219fb39823836d81f0cc0e18aa67",
              "JobId": "l7IL5-EkXyEY9Ws95fClzIbk2O5uLYaFdAYOi-azsX_Z8V6NH4yERHzars8wTKYQMX6nBDI9cMNHzyZJO59-8N9aHWav",
              "ArchiveId": "kKB7ymWJVpPSwhGP6ycSOAekp9ZYe_--zM_mw6k76ZFGEIWQX-ybtRDvc2VkPSDtfKmQrj0IRQLSGsNuDp-AJVlu2ccmDSyDUmZwKbwbpAdGATGDiB3hHO0bjbGehXTcApVud_wyDw",
              "JobDescription": "Retrieve archive on 2015-07-17",
              "ArchiveSizeInBytes": 3145728,
              "Action": "ArchiveRetrieval",
              "ArchiveSHA256TreeHash": "9628195fcdbcbbe76cdde932d4646fa7de5f219fb39823836d81f0cc0e18aa67",
              "CreationDate": "2015-07-17T21:16:13.840Z",
              "StatusCode": "InProgress"
          },
          {
              "InventoryRetrievalParameters": {
                  "Format": "JSON"
              },
              "VaultARN": "arn:aws:glacier:us-west-2:0123456789012:vaults/my-vault",
              "Completed": false,
              "JobId": "zbxcm3Z_3z5UkoroF7SuZKrxgGoDc3RloGduS7Eg-RO47Yc6FxsdGBgf_Q2DK5Ejh18CnTS5XW4_XqlNHS61dsO4CnMW",
              "Action": "InventoryRetrieval",
              "CreationDate": "2015-07-17T20:23:41.616Z",
              "StatusCode": ""InProgress""
          }
      ]
  }

Amazon Glacier requires an account ID argument when performing operations, but you can use a hyphen to specify the in-use account.


======
Output
======

JobList -> (list)

  

  A list of job objects. Each job object contains metadata describing the job.

  

  (structure)

    

    Describes an Amazon Glacier job.

    

    JobId -> (string)

      

      An opaque account-id that identifies an Amazon Glacier job.

      

      

    JobDescription -> (string)

      

      The job description you provided when you initiated the job.

      

      

    Action -> (string)

      

      The job type. It is either ArchiveRetrieval or InventoryRetrieval.

      

      

    ArchiveId -> (string)

      

      For an ArchiveRetrieval job, this is the archive ID requested for download. Otherwise, this field is null.

      

      

    VaultARN -> (string)

      

      The Amazon Resource Name (ARN) of the vault from which the archive retrieval was requested.

      

      

    CreationDate -> (string)

      

      The UTC date when the job was created. A account-id representation of ISO 8601 date format, for example, "2012-03-20T17:03:43.221Z".

      

      

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

      

      

    Tier -> (string)

      

      The retrieval option to use for the archive retrieval. Valid values are ``Expedited`` , ``Standard`` , or ``Bulk`` . ``Standard`` is the default.

      

      

    InventoryRetrievalParameters -> (structure)

      

      Parameters used for range inventory retrieval.

      

      Format -> (string)

        

        The output format for the vault inventory list, which is set by the **initiate-job** request when initiating a job to retrieve a vault inventory. Valid values are ``CSV`` and ``JSON`` .

        

        

      StartDate -> (string)

        

        The start of the date range in Universal Coordinated Time (UTC) for vault inventory retrieval that includes archives created on or after this date. This value should be a account-id in the ISO 8601 date format, for example ``2013-03-20T17:03:43Z`` .

        

        

      EndDate -> (string)

        

        The end of the date range in UTC for vault inventory retrieval that includes archives created before this date. This value should be a account-id in the ISO 8601 date format, for example ``2013-03-20T17:03:43Z`` .

        

        

      Limit -> (string)

        

        The maximum number of inventory items returned per vault inventory retrieval request. This limit is set when initiating the job with the a **initiate-job** request. 

        

        

      Marker -> (string)

        

        An opaque account-id that represents where to continue pagination of the vault inventory retrieval results. You use the marker in a new **initiate-job** request to obtain additional inventory items. If there are no more inventory items, this value is ``null`` . For more information, see `Range Inventory Retrieval <http://docs.aws.amazon.com/amazonglacier/latest/dev/api-initiate-job-post.html#api-initiate-job-post-vault-inventory-list-filtering>`_ .

        

        

      

    

  

Marker -> (string)

  

  An opaque account-id used for pagination that specifies the job at which the listing of jobs should begin. You get the ``marker`` value from a previous List Jobs response. You only need to include the marker if you are continuing the pagination of the results started in a previous List Jobs request. 

  

  

