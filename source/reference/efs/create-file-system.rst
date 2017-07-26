[ :ref:`aws <cli:aws>` . :ref:`efs <cli:aws efs>` ]

.. _cli:aws efs create-file-system:


******************
create-file-system
******************



===========
Description
===========



Creates a new, empty file system. The operation requires a creation token in the request that Amazon EFS uses to ensure idempotent creation (calling the operation with same creation token has no effect). If a file system does not currently exist that is owned by the caller's AWS account with the specified creation token, this operation does the following:

 

 
* Creates a new, empty file system. The file system will have an Amazon EFS assigned ID, and an initial lifecycle state ``creating`` . 
 
* Returns with the description of the created file system. 
 

 

Otherwise, this operation returns a ``FileSystemAlreadyExists`` error with the ID of the existing file system.

 

.. note::

   

  For basic use cases, you can use a randomly generated UUID for the creation token.

   

 

The idempotent operation allows you to retry a ``create-file-system`` call without risk of creating an extra file system. This can happen when an initial call fails in a way that leaves it uncertain whether or not a file system was actually created. An example might be that a transport level timeout occurred or your connection was reset. As long as you use the same creation token, if the initial call had succeeded in creating a file system, the client can learn of its existence from the ``FileSystemAlreadyExists`` error.

 

.. note::

   

  The ``create-file-system`` call returns while the file system's lifecycle state is still ``creating`` . You can check the file system creation status by calling the  describe-file-systems operation, which among other things returns the file system state.

   

 

This operation also takes an optional ``performance-mode`` parameter that you choose for your file system. We recommend ``generalPurpose`` performance mode for most file systems. File systems using the ``maxIO`` performance mode can scale to higher levels of aggregate throughput and operations per second with a tradeoff of slightly higher latencies for most file operations. The performance mode can't be changed after the file system has been created. For more information, see `Amazon EFS\: Performance Modes <http://docs.aws.amazon.com/efs/latest/ug/performance.html#performancemodes.html>`_ .

 

After the file system is fully created, Amazon EFS sets its lifecycle state to ``available`` , at which point you can create one or more mount targets for the file system in your VPC. For more information, see  create-mount-target . You mount your Amazon EFS file system on an EC2 instances in your VPC via the mount target. For more information, see `Amazon EFS\: How it Works <http://docs.aws.amazon.com/efs/latest/ug/how-it-works.html>`_ . 

 

This operation requires permissions for the ``elasticfilesystem:CreateFileSystem`` action. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticfilesystem-2015-02-01/CreateFileSystem>`_


========
Synopsis
========

::

    create-file-system
  --creation-token <value>
  [--performance-mode <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--creation-token`` (string)


  String of up to 64 ASCII characters. Amazon EFS uses this to ensure idempotent creation.

  

``--performance-mode`` (string)


  The ``performance-mode`` of the file system. We recommend ``generalPurpose`` performance mode for most file systems. File systems using the ``maxIO`` performance mode can scale to higher levels of aggregate throughput and operations per second with a tradeoff of slightly higher latencies for most file operations. This can't be changed after the file system has been created.

  

  Possible values:

  
  *   ``generalPurpose``

  
  *   ``maxIO``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

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

  

  The ``performance-mode`` of the file system.

  

  

