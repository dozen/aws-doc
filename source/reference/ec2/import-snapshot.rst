[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 import-snapshot:


***************
import-snapshot
***************



===========
Description
===========



Imports a disk into an EBS snapshot.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ImportSnapshot>`_


========
Synopsis
========

::

    import-snapshot
  [--client-data <value>]
  [--client-token <value>]
  [--description <value>]
  [--disk-container <value>]
  [--dry-run | --no-dry-run]
  [--role-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

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


  Token to enable idempotency for VM import requests.

  

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



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--role-name`` (string)


  The name of the role to use when not using the default role, 'vmimport'.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Description -> (string)

  

  A description of the import snapshot task.

  

  

ImportTaskId -> (string)

  

  The ID of the import snapshot task.

  

  

SnapshotTaskDetail -> (structure)

  

  Information about the import snapshot task.

  

  Description -> (string)

    

    The description of the snapshot.

    

    

  DiskImageSize -> (double)

    

    The size of the disk in the snapshot, in GiB.

    

    

  Format -> (string)

    

    The format of the disk image from which the snapshot is created.

    

    

  Progress -> (string)

    

    The percentage of completion for the import snapshot task.

    

    

  SnapshotId -> (string)

    

    The snapshot ID of the disk being imported.

    

    

  Status -> (string)

    

    A brief status for the import snapshot task.

    

    

  StatusMessage -> (string)

    

    A detailed status message for the import snapshot task.

    

    

  Url -> (string)

    

    The URL of the disk image from which the snapshot is created.

    

    

  UserBucket -> (structure)

    

    The S3 bucket for the disk image.

    

    S3Bucket -> (string)

      

      The S3 bucket from which the disk image was created.

      

      

    S3Key -> (string)

      

      The file name of the disk image.

      

      

    

  

