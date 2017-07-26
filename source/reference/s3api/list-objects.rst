[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api list-objects:


************
list-objects
************



===========
Description
===========

Returns some or all (up to 1000) of the objects in a bucket. You can use the request parameters as selection criteria to return a subset of the objects in a bucket.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/ListObjects>`_


``list-objects`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Contents``, ``CommonPrefixes``


========
Synopsis
========

::

    list-objects
  --bucket <value>
  [--delimiter <value>]
  [--encoding-type <value>]
  [--prefix <value>]
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


``--delimiter`` (string)
A delimiter is a character you use to group keys.

``--encoding-type`` (string)
Requests Amazon S3 to encode the object keys in the response and specifies the encoding method to use. An object key may contain any Unicode character; however, XML 1.0 parser cannot parse some characters, such as characters with an ASCII value from 0 to 10. For characters that are not supported in XML 1.0, you can add this parameter to request that Amazon S3 encode the keys in the response.

  Possible values:

  
  *   ``url``

  

  

``--prefix`` (string)
Limits the response to keys that begin with the specified prefix.

``--request-payer`` (string)
Confirms that the requester knows that she or he will be charged for the list objects request. Bucket owners need not specify this parameter in their requests.

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



========
Examples
========

The following example uses the ``list-objects`` command to display the names of all the objects in the specified bucket::

  aws s3api list-objects --bucket text-content --query 'Contents[].{Key: Key, Size: Size}'

The example uses the ``--query`` argument to filter the output of
``list-objects`` down to the key value and size for each object

For more information about objects, see `Working with Amazon S3 Objects`_ in the *Amazon S3 Developer Guide*.

.. _`Working with Amazon S3 Objects`: http://docs.aws.amazon.com/AmazonS3/latest/dev/UsingObjects.html


======
Output
======

IsTruncated -> (boolean)

  A flag that indicates whether or not Amazon S3 returned all of the results that satisfied the search criteria.

  

Marker -> (string)

  

  

NextMarker -> (string)

  When response is truncated (the IsTruncated element value in the response is true), you can use the key name in this field as marker in the subsequent request to get next set of objects. Amazon S3 lists objects in alphabetical order Note: This element is returned only if you have delimiter request parameter specified. If response does not include the NextMaker and it is truncated, you can use the value of the last Key in the response as the marker in the subsequent request to get the next set of object keys.

  

Contents -> (list)

  

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

  

  

Prefix -> (string)

  

  

Delimiter -> (string)

  

  

MaxKeys -> (integer)

  

  

CommonPrefixes -> (list)

  

  (structure)

    

    Prefix -> (string)

      

      

    

  

EncodingType -> (string)

  Encoding type used by Amazon S3 to encode object keys in the response.

  

