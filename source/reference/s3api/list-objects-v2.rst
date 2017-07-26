[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api list-objects-v2:


***************
list-objects-v2
***************



===========
Description
===========

Returns some or all (up to 1000) of the objects in a bucket. You can use the request parameters as selection criteria to return a subset of the objects in a bucket. Note: list-objects-v2 is the revised List Objects API and we recommend you use this revised API for new application development.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/ListObjectsV2>`_


``list-objects-v2`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Contents``, ``CommonPrefixes``


========
Synopsis
========

::

    list-objects-v2
  --bucket <value>
  [--delimiter <value>]
  [--encoding-type <value>]
  [--prefix <value>]
  [--fetch-owner | --no-fetch-owner]
  [--start-after <value>]
  [--request-payer <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)
Name of the bucket to list.

``--delimiter`` (string)
A delimiter is a character you use to group keys.

``--encoding-type`` (string)
Encoding type used by Amazon S3 to encode object keys in the response.

  Possible values:

  
  *   ``url``

  

  

``--prefix`` (string)
Limits the response to keys that begin with the specified prefix.

``--fetch-owner`` | ``--no-fetch-owner`` (boolean)
The owner field is not present in listV2 by default, if you want to return owner field with each key in the result then set the fetch owner field to true

``--start-after`` (string)
start-after is where you want Amazon S3 to start listing from. Amazon S3 starts listing after this specified key. start-after can be any key in the bucket

``--request-payer`` (string)
Confirms that the requester knows that she or he will be charged for the list objects request in V2 style. Bucket owners need not specify this parameter in their requests.

  Possible values:

  
  *   ``requester``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

IsTruncated -> (boolean)

  A flag that indicates whether or not Amazon S3 returned all of the results that satisfied the search criteria.

  

Contents -> (list)

  Metadata about each object returned.

  (structure)

    

    Key -> (string)

      

      

    LastModified -> (timestamp)

      

      

    ETag -> (string)

      

      

    Size -> (integer)

      

      

    StorageClass -> (string)

      The class of storage used to store the object.

      

    Owner -> (structure)

      

      DisplayName -> (string)

        

        

      ID -> (string)

        

        

      

    

  

Name -> (string)

  Name of the bucket to list.

  

Prefix -> (string)

  Limits the response to keys that begin with the specified prefix.

  

Delimiter -> (string)

  A delimiter is a character you use to group keys.

  

MaxKeys -> (integer)

  Sets the maximum number of keys returned in the response. The response might contain fewer keys but will never contain more.

  

CommonPrefixes -> (list)

  CommonPrefixes contains all (if there are any) keys between prefix and the next occurrence of the string specified by delimiter

  (structure)

    

    Prefix -> (string)

      

      

    

  

EncodingType -> (string)

  Encoding type used by Amazon S3 to encode object keys in the response.

  

KeyCount -> (integer)

  KeyCount is the number of keys returned with this request. KeyCount will always be less than equals to max-keys field. Say you ask for 50 keys, your result will include less than equals 50 keys

  

ContinuationToken -> (string)

  ContinuationToken indicates Amazon S3 that the list is being continued on this bucket with a token. ContinuationToken is obfuscated and is not a real key

  

NextContinuationToken -> (string)

  NextContinuationToken is sent when isTruncated is true which means there are more keys in the bucket that can be listed. The next list requests to Amazon S3 can be continued with this NextContinuationToken. NextContinuationToken is obfuscated and is not a real key

  

StartAfter -> (string)

  start-after is where you want Amazon S3 to start listing from. Amazon S3 starts listing after this specified key. start-after can be any key in the bucket

  

