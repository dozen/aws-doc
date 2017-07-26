[ :ref:`aws <cli:aws>` . :ref:`efs <cli:aws efs>` ]

.. _cli:aws efs describe-file-systems:


*********************
describe-file-systems
*********************



===========
Description
===========



Returns the description of a specific Amazon EFS file system if either the file system ``creation-token`` or the ``file-system-id`` is provided; otherwise, returns descriptions of all file systems owned by the caller's AWS account in the AWS region of the endpoint that you're calling.

 

When retrieving all file system descriptions, you can optionally specify the ``max-items`` parameter to limit the number of descriptions in a response. If more file system descriptions remain, Amazon EFS returns a ``NextMarker`` , an opaque token, in the response. In this case, you should send a subsequent request with the ``marker`` request parameter set to the value of ``NextMarker`` . 

 

So to retrieve a list of your file system descriptions, the expected usage of this API is an iterative process of first calling ``describe-file-systems`` without the ``marker`` and then continuing to call it with the ``marker`` parameter set to the value of the ``NextMarker`` from the previous response until the response has no ``NextMarker`` . 

 

Note that the implementation may return fewer than ``max-items`` file system descriptions while still including a ``NextMarker`` value. 

 

The order of file systems returned in the response of one ``describe-file-systems`` call, and the order of file systems returned across the responses of a multi-call iteration, is unspecified. 

 

This operation requires permission for the ``elasticfilesystem:DescribeFileSystems`` action. 



.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.efs true`` 



========
Synopsis
========

::

    describe-file-systems
  [--max-items <value>]
  [--marker <value>]
  [--creation-token <value>]
  [--file-system-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--max-items`` (integer)


  Optional integer. Specifies the maximum number of file systems to return in the response. This parameter value must be greater than 0. The number of items Amazon EFS returns will be the minimum of the ``max-items`` parameter specified in the request and the service's internal maximum number of items per page. 

  

``--marker`` (string)


  Optional string. Opaque pagination token returned from a previous ``describe-file-systems`` operation. If present, specifies to continue the list from where the returning call had left off. 

  

``--creation-token`` (string)


  Optional string. Restricts the list to the file system with this creation token (you specify a creation token at the time of creating an Amazon EFS file system). 

  

``--file-system-id`` (string)


  Optional string. File system ID whose description you want to retrieve. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Marker -> (string)

  

  A string, present if provided by caller in the request.

  

  

FileSystems -> (list)

  

  An array of file system descriptions.

  

  (structure)

    

    This object provides description of a file system.

    

    OwnerId -> (string)

      

      The AWS account that created the file system. If the file system was created by an IAM user, the parent account to which the user belongs is the owner.

      

      

    CreationToken -> (string)

      

      Opaque string specified in the request. 

      

      

    FileSystemId -> (string)

      

      The file system ID assigned by Amazon EFS.

      

      

    CreationTime -> (timestamp)

      

      The time at which the file system was created, in seconds, since 1970-01-01T00:00:00Z.

      

      

    LifeCycleState -> (string)

      

      A predefined string value that indicates the lifecycle phase of the file system. 

      

      

    Name -> (string)

      

      You can add tags to a file system (see  create-tags ) including a "Name" tag. If the file system has a "Name" tag, Amazon EFS returns the value in this field. 

      

      

    NumberOfMountTargets -> (integer)

      

      The current number of mount targets (see  create-mount-target ) the file system has.

      

      

    SizeInBytes -> (structure)

      

      This object provides the latest known metered size of data stored in the file system, in bytes, in its ``Value`` field, and the time at which that size was determined in its ``Timestamp`` field. The ``Timestamp`` value is the integer number of seconds since 1970-01-01T00:00:00Z. Note that the value does not represent the size of a consistent snapshot of the file system, but it is eventually consistent when there are no writes to the file system. That is, the value will represent actual size only if the file system is not modified for a period longer than a couple of hours. Otherwise, the value is not the exact size the file system was at any instant in time. 

      

      Value -> (long)

        

        The latest known metered size, in bytes, of data stored in the file system.

        

        

      Timestamp -> (timestamp)

        

        The time at which the size of data, returned in the ``Value`` field, was determined. The value is the integer number of seconds since 1970-01-01T00:00:00Z.

        

        

      

    

  

NextMarker -> (string)

  

  A string, present if there are more file systems than returned in the response. You can use the ``NextMarker`` in the subsequent request to fetch the descriptions.

  

  

