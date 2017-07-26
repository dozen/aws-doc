[ :ref:`aws <cli:aws>` . :ref:`efs <cli:aws efs>` ]

.. _cli:aws efs describe-file-systems:


*********************
describe-file-systems
*********************



===========
Description
===========



Returns the description of a specific Amazon EFS file system if either the file system ``creation-token`` or the ``file-system-id`` is provided. Otherwise, it returns descriptions of all file systems owned by the caller's AWS account in the AWS Region of the endpoint that you're calling.

 

When retrieving all file system descriptions, you can optionally specify the ``MaxItems`` parameter to limit the number of descriptions in a response. If more file system descriptions remain, Amazon EFS returns a ``NextMarker`` , an opaque token, in the response. In this case, you should send a subsequent request with the ``marker`` request parameter set to the value of ``NextMarker`` . 

 

To retrieve a list of your file system descriptions, this operation is used in an iterative process, where ``describe-file-systems`` is called first without the ``marker`` and then the operation continues to call it with the ``marker`` parameter set to the value of the ``NextMarker`` from the previous response until the response has no ``NextMarker`` . 

 

The implementation may return fewer than ``MaxItems`` file system descriptions while still including a ``NextMarker`` value. 

 

The order of file systems returned in the response of one ``describe-file-systems`` call and the order of file systems returned across the responses of a multi-call iteration is unspecified. 

 

This operation requires permissions for the ``elasticfilesystem:DescribeFileSystems`` action. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticfilesystem-2015-02-01/DescribeFileSystems>`_


``describe-file-systems`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``FileSystems``


========
Synopsis
========

::

    describe-file-systems
  [--max-items <value>]
  [--creation-token <value>]
  [--file-system-id <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--creation-token`` (string)


  (Optional) Restricts the list to the file system with this creation token (String). You specify a creation token when you create an Amazon EFS file system.

  

``--file-system-id`` (string)


  (Optional) ID of the file system whose description you want to retrieve (String).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Marker -> (string)

  

  Present if provided by caller in the request (String).

  

  

FileSystems -> (list)

  

  Array of file system descriptions.

  

  (structure)

    

    Description of the file system.

    

    OwnerId -> (string)

      

      AWS account that created the file system. If the file system was created by an IAM user, the parent account to which the user belongs is the owner.

      

      

    CreationToken -> (string)

      

      Opaque string specified in the request.

      

      

    FileSystemId -> (string)

      

      ID of the file system, assigned by Amazon EFS.

      

      

    CreationTime -> (timestamp)

      

      Time that the file system was created, in seconds (since 1970-01-01T00:00:00Z).

      

      

    LifeCycleState -> (string)

      

      Lifecycle phase of the file system.

      

      

    Name -> (string)

      

      You can add tags to a file system, including a ``Name`` tag. For more information, see  create-tags . If the file system has a ``Name`` tag, Amazon EFS returns the value in this field. 

      

      

    NumberOfMountTargets -> (integer)

      

      Current number of mount targets that the file system has. For more information, see  create-mount-target .

      

      

    SizeInBytes -> (structure)

      

      Latest known metered size (in bytes) of data stored in the file system, in bytes, in its ``Value`` field, and the time at which that size was determined in its ``Timestamp`` field. The ``Timestamp`` value is the integer number of seconds since 1970-01-01T00:00:00Z. Note that the value does not represent the size of a consistent snapshot of the file system, but it is eventually consistent when there are no writes to the file system. That is, the value will represent actual size only if the file system is not modified for a period longer than a couple of hours. Otherwise, the value is not the exact size the file system was at any instant in time. 

      

      Value -> (long)

        

        Latest known metered size (in bytes) of data stored in the file system.

        

        

      Timestamp -> (timestamp)

        

        Time at which the size of data, returned in the ``Value`` field, was determined. The value is the integer number of seconds since 1970-01-01T00:00:00Z.

        

        

      

    PerformanceMode -> (string)

      

      The ``PerformanceMode`` of the file system.

      

      

    

  

NextMarker -> (string)

  

  Present if there are more file systems than returned in the response (String). You can use the ``NextMarker`` in the subsequent request to fetch the descriptions.

  

  

