[ :ref:`aws <cli:aws>` . :ref:`efs <cli:aws efs>` ]

.. _cli:aws efs describe-mount-targets:


**********************
describe-mount-targets
**********************



===========
Description
===========



Returns the descriptions of all the current mount targets, or a specific mount target, for a file system. When requesting all of the current mount targets, the order of mount targets returned in the response is unspecified.

 

This operation requires permission for the ``elasticfilesystem:DescribeMountTargets`` action, on either the file system id that you specify in ``file-system-id`` , or on the file system of the mount target that you specify in ``mount-target-id`` .



.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.efs true`` 



========
Synopsis
========

::

    describe-mount-targets
  [--max-items <value>]
  [--marker <value>]
  [--file-system-id <value>]
  [--mount-target-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--max-items`` (integer)


  Optional. Maximum number of mount targets to return in the response. It must be an integer with a value greater than zero.

  

``--marker`` (string)


  Optional. String. Opaque pagination token returned from a previous ``describe-mount-targets`` operation. If present, it specifies to continue the list from where the previous returning call left off.

  

``--file-system-id`` (string)


  Optional. String. The ID of the file system whose mount targets you want to list. It must be included in your request if ``mount-target-id`` is not included.

  

``--mount-target-id`` (string)


  Optional. String. The ID of the mount target that you want to have described. It must be included in your request if ``file-system-id`` is not included.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Marker -> (string)

  

  If the request included the ``marker`` , the response returns that value in this field.

  

  

MountTargets -> (list)

  

  Returns the file system's mount targets as an array of ``MountTargetDescription`` objects.

  

  (structure)

    

    This object provides description of a mount target.

    

    OwnerId -> (string)

      

      The AWS account ID that owns the resource.

      

      

    MountTargetId -> (string)

      

      The system-assigned mount target ID. 

      

      

    FileSystemId -> (string)

      

      The ID of the file system for which the mount target is intended.

      

      

    SubnetId -> (string)

      

      The ID of the subnet that the mount target is in.

      

      

    LifeCycleState -> (string)

      

      The lifecycle state the mount target is in.

      

      

    IpAddress -> (string)

      

      The address at which the file system may be mounted via the mount target.

      

      

    NetworkInterfaceId -> (string)

      

      The ID of the network interface that Amazon EFS created when it created the mount target.

      

      

    

  

NextMarker -> (string)

  

  If a value is present, there are more mount targets to return. In a subsequent request, you can provide ``marker`` in your request with this value to retrieve the next set of mount targets.

  

  

