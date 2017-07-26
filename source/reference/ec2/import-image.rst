[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 import-image:


************
import-image
************



===========
Description
===========



Import single or multi-volume disk images or EBS snapshots into an Amazon Machine Image (AMI). For more information, see `Importing a VM as an Image Using VM Import/Export <http://docs.aws.amazon.com/vm-import/latest/userguide/vmimport-image-import.html>`_ in the *VM Import/Export User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ImportImage>`_


========
Synopsis
========

::

    import-image
  [--architecture <value>]
  [--client-data <value>]
  [--client-token <value>]
  [--description <value>]
  [--disk-containers <value>]
  [--dry-run | --no-dry-run]
  [--hypervisor <value>]
  [--license-type <value>]
  [--platform <value>]
  [--role-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--architecture`` (string)


  The architecture of the virtual machine.

   

  Valid values: ``i386`` | ``x86_64``  

  

``--client-data`` (structure)


  The client-specific data.

  



Shorthand Syntax::

    Comment=string,UploadEnd=timestamp,UploadSize=double,UploadStart=timestamp




JSON Syntax::

  {
    "Comment": "string",
    "UploadEnd": timestamp,
    "UploadSize": double,
    "UploadStart": timestamp
  }



``--client-token`` (string)


  The token to enable idempotency for VM import requests.

  

``--description`` (string)


  A description string for the import image task.

  

``--disk-containers`` (list)


  Information about the disk containers.

  



Shorthand Syntax::

    Description=string,DeviceName=string,Format=string,SnapshotId=string,Url=string,UserBucket={S3Bucket=string,S3Key=string} ...




JSON Syntax::

  [
    {
      "Description": "string",
      "DeviceName": "string",
      "Format": "string",
      "SnapshotId": "string",
      "Url": "string",
      "UserBucket": {
        "S3Bucket": "string",
        "S3Key": "string"
      }
    }
    ...
  ]



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--hypervisor`` (string)


  The target hypervisor platform.

   

  Valid values: ``xen``  

  

``--license-type`` (string)


  The license type to be used for the Amazon Machine Image (AMI) after importing.

   

   **Note:** You may only use BYOL if you have existing licenses with rights to use these licenses in a third party cloud like AWS. For more information, see `Prerequisites <http://docs.aws.amazon.com/vm-import/latest/userguide/vmimport-image-import.html#prerequisites-image>`_ in the VM Import/Export User Guide.

   

  Valid values: ``AWS`` | ``BYOL``  

  

``--platform`` (string)


  The operating system of the virtual machine.

   

  Valid values: ``Windows`` | ``Linux``  

  

``--role-name`` (string)


  The name of the role to use when not using the default role, 'vmimport'.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Architecture -> (string)

  

  The architecture of the virtual machine.

  

  

Description -> (string)

  

  A description of the import task.

  

  

Hypervisor -> (string)

  

  The target hypervisor of the import task.

  

  

ImageId -> (string)

  

  The ID of the Amazon Machine Image (AMI) created by the import task.

  

  

ImportTaskId -> (string)

  

  The task ID of the import image task.

  

  

LicenseType -> (string)

  

  The license type of the virtual machine.

  

  

Platform -> (string)

  

  The operating system of the virtual machine.

  

  

Progress -> (string)

  

  The progress of the task.

  

  

SnapshotDetails -> (list)

  

  Information about the snapshots.

  

  (structure)

    

    Describes the snapshot created from the imported disk.

    

    Description -> (string)

      

      A description for the snapshot.

      

      

    DeviceName -> (string)

      

      The block device mapping for the snapshot.

      

      

    DiskImageSize -> (double)

      

      The size of the disk in the snapshot, in GiB.

      

      

    Format -> (string)

      

      The format of the disk image from which the snapshot is created.

      

      

    Progress -> (string)

      

      The percentage of progress for the task.

      

      

    SnapshotId -> (string)

      

      The snapshot ID of the disk being imported.

      

      

    Status -> (string)

      

      A brief status of the snapshot creation.

      

      

    StatusMessage -> (string)

      

      A detailed status message for the snapshot creation.

      

      

    Url -> (string)

      

      The URL used to access the disk image.

      

      

    UserBucket -> (structure)

      

      The S3 bucket for the disk image.

      

      S3Bucket -> (string)

        

        The S3 bucket from which the disk image was created.

        

        

      S3Key -> (string)

        

        The file name of the disk image.

        

        

      

    

  

Status -> (string)

  

  A brief status of the task.

  

  

StatusMessage -> (string)

  

  A detailed status message of the import task.

  

  

