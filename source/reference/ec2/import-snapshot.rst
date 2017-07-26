[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 import-snapshot:


***************
import-snapshot
***************



===========
Description
===========



Imports a disk into an EBS snapshot.



========
Synopsis
========

::

    import-snapshot
  [--dry-run | --no-dry-run]
  [--description <value>]
  [--disk-container <value>]
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


  The description string for the import snapshot task.

  

``--disk-container`` (structure)


  Information about the disk container.

  



Shorthand Syntax::

    Description=string,Format=string,Url=string,UserBucket={S3Bucket=string,S3Key=string}




JSON Syntax::

  {
    "Description": "string",
    "Format": "string",
    "Url": "string",
    "UserBucket": {
      "S3Bucket": "string",
      "S3Key": "string"
    }
  }



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


  Token to enable idempotency for VM import requests.

  

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

  

  The ID of the import snapshot task.

  

  

SnapshotTaskDetail -> (structure)

  

  Information about the import snapshot task.

  

  DiskImageSize -> (double)

    

    The size of the disk in the snapshot, in GiB.

    

    

  Description -> (string)

    

    The description of the snapshot.

    

    

  Format -> (string)

    

    The format of the disk image from which the snapshot is created.

    

    

  Url -> (string)

    

    The URL of the disk image from which the snapshot is created.

    

    

  UserBucket -> (structure)

    

    The S3 bucket for the disk image.

    

    S3Bucket -> (string)

      

      The S3 bucket from which the disk image was created.

      

      

    S3Key -> (string)

      

      The key from which the disk image was created.

      

      

    

  SnapshotId -> (string)

    

    The snapshot ID of the disk being imported.

    

    

  Progress -> (string)

    

    The percentage of completion for the import snapshot task.

    

    

  StatusMessage -> (string)

    

    A detailed status message for the import snapshot task.

    

    

  Status -> (string)

    

    A brief status for the import snapshot task.

    

    

  

Description -> (string)

  

  A description of the import snapshot task.

  

  

