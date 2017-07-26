[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 import-image:


************
import-image
************



===========
Description
===========



Import single or multi-volume disk images or EBS snapshots into an Amazon Machine Image (AMI).



========
Synopsis
========

::

    import-image
  [--dry-run | --no-dry-run]
  [--description <value>]
  [--disk-containers <value>]
  [--license-type <value>]
  [--hypervisor <value>]
  [--architecture <value>]
  [--platform <value>]
  [--client-data <value>]
  [--client-token <value>]
  [--role-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--description`` (string)


  A description string for the import image task.

  

``--disk-containers`` (list)


  Information about the disk containers.

  



Shorthand Syntax::

    Description=string,Format=string,Url=string,UserBucket={S3Bucket=string,S3Key=string},DeviceName=string,SnapshotId=string ...




JSON Syntax::

  [
    {
      "Description": "string",
      "Format": "string",
      "Url": "string",
      "UserBucket": {
        "S3Bucket": "string",
        "S3Key": "string"
      },
      "DeviceName": "string",
      "SnapshotId": "string"
    }
    ...
  ]



``--license-type`` (string)


  The license type to be used for the Amazon Machine Image (AMI) after importing.

   

  **Note:** You may only use BYOL if you have existing licenses with rights to use these licenses in a third party cloud like AWS. For more information, see `VM Import/Export Prerequisites`_ in the *Amazon Elastic Compute Cloud User Guide* .

   

  Valid values: ``AWS`` | ``BYOL`` 

  

``--hypervisor`` (string)


  The target hypervisor platform.

   

  Valid values: ``xen`` 

  

``--architecture`` (string)


  The architecture of the virtual machine.

   

  Valid values: ``i386`` | ``x86_64`` 

  

``--platform`` (string)


  The operating system of the virtual machine.

   

  Valid values: ``Windows`` | ``Linux`` 

  

``--client-data`` (structure)


  The client-specific data.

  



Shorthand Syntax::

    UploadStart=timestamp,UploadEnd=timestamp,UploadSize=double,Comment=string




JSON Syntax::

  {
    "UploadStart": timestamp,
    "UploadEnd": timestamp,
    "UploadSize": double,
    "Comment": "string"
  }



``--client-token`` (string)


  The token to enable idempotency for VM import requests.

  

``--role-name`` (string)


  The name of the role to use when not using the default role, 'vmimport'.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ImportTaskId -> (string)

  

  The task ID of the import image task.

  

  

Architecture -> (string)

  

  The architecture of the virtual machine.

  

  

LicenseType -> (string)

  

  The license type of the virtual machine.

  

  

Platform -> (string)

  

  The operating system of the virtual machine.

  

  

Hypervisor -> (string)

  

  The target hypervisor of the import task.

  

  

Description -> (string)

  

  A description of the import task.

  

  

SnapshotDetails -> (list)

  

  Information about the snapshots.

  

  (structure)

    

    Describes the snapshot created from the imported disk.

    

    DiskImageSize -> (double)

      

      The size of the disk in the snapshot, in GiB.

      

      

    Description -> (string)

      

      A description for the snapshot.

      

      

    Format -> (string)

      

      The format of the disk image from which the snapshot is created.

      

      

    Url -> (string)

      

      The URL used to access the disk image.

      

      

    UserBucket -> (structure)

      

      Describes the S3 bucket for the disk image.

      

      S3Bucket -> (string)

        

        The S3 bucket from which the disk image was created.

        

        

      S3Key -> (string)

        

        The key from which the disk image was created.

        

        

      

    DeviceName -> (string)

      

      The block device mapping for the snapshot.

      

      

    SnapshotId -> (string)

      

      The snapshot ID of the disk being imported.

      

      

    Progress -> (string)

      

      The percentage of progress for the task.

      

      

    StatusMessage -> (string)

      

      A detailed status message for the snapshot creation.

      

      

    Status -> (string)

      

      A brief status of the snapshot creation.

      

      

    

  

ImageId -> (string)

  

  The ID of the Amazon Machine Image (AMI) created by the import task.

  

  

Progress -> (string)

  

  The progress of the task.

  

  

StatusMessage -> (string)

  

  A detailed status message of the import task.

  

  

Status -> (string)

  

  A brief status of the task.

  

  



.. _VM Import/Export Prerequisites: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/VMImportPrerequisites.html
