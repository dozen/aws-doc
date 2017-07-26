[ :ref:`aws <cli:aws>` . :ref:`efs <cli:aws efs>` ]

.. _cli:aws efs describe-mount-targets:


**********************
describe-mount-targets
**********************



===========
Description
===========



Returns the descriptions of all the current mount targets, or a specific mount target, for a file system. When requesting all of the current mount targets, the order of mount targets returned in the response is unspecified.

 

This operation requires permissions for the ``elasticfilesystem:DescribeMountTargets`` action, on either the file system ID that you specify in ``file-system-id`` , or on the file system of the mount target that you specify in ``mount-target-id`` .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticfilesystem-2015-02-01/DescribeMountTargets>`_


``describe-mount-targets`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``MountTargets``


========
Synopsis
========

::

    describe-mount-targets
  [--max-items <value>]
  [--file-system-id <value>]
  [--mount-target-id <value>]
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

   

``--file-system-id`` (string)


  (Optional) ID of the file system whose mount targets you want to list (String). It must be included in your request if ``mount-target-id`` is not included.

  

``--mount-target-id`` (string)


  (Optional) ID of the mount target that you want to have described (String). It must be included in your request if ``file-system-id`` is not included.

  

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

  

  If the request included the ``marker`` , the response returns that value in this field.

  

  

MountTargets -> (list)

  

  Returns the file system's mount targets as an array of ``MountTargetDescription`` objects.

  

  (structure)

    

    Provides a description of a mount target.

    

    OwnerId -> (string)

      

      AWS account ID that owns the resource.

      

      

    MountTargetId -> (string)

      

      System-assigned mount target ID.

      

      

    FileSystemId -> (string)

      

      ID of the file system for which the mount target is intended.

      

      

    SubnetId -> (string)

      

      ID of the mount target's subnet.

      

      

    LifeCycleState -> (string)

      

      Lifecycle state of the mount target.

      

      

    IpAddress -> (string)

      

      Address at which the file system may be mounted via the mount target.

      

      

    NetworkInterfaceId -> (string)

      

      ID of the network interface that Amazon EFS created when it created the mount target.

      

      

    

  

NextMarker -> (string)

  

  If a value is present, there are more mount targets to return. In a subsequent request, you can provide ``marker`` in your request with this value to retrieve the next set of mount targets.

  

  

