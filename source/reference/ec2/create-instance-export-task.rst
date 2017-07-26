[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-instance-export-task:


***************************
create-instance-export-task
***************************



===========
Description
===========



Exports a running or stopped instance to an S3 bucket.

 

For information about the supported operating systems, image formats, and known limitations for the types of instances you can export, see `Exporting EC2 Instances`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    create-instance-export-task
  [--description <value>]
  --instance-id <value>
  [--target-environment <value>]
  [--export-to-s3-task <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--description`` (string)


  A description for the conversion task or the resource being exported. The maximum length is 255 bytes.

  

``--instance-id`` (string)


  The ID of the instance.

  

``--target-environment`` (string)


  The target virtualization environment.

  

  Possible values:

  
  *   ``citrix``

  
  *   ``vmware``

  
  *   ``microsoft``

  

  

``--export-to-s3-task`` (structure)


  The format and location for an instance export task.

  



Shorthand Syntax::

    DiskImageFormat=string,ContainerFormat=string,S3Bucket=string,S3Prefix=string




JSON Syntax::

  {
    "DiskImageFormat": "VMDK"|"RAW"|"VHD",
    "ContainerFormat": "ova",
    "S3Bucket": "string",
    "S3Prefix": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To export an instance**

This example command creates a task to export the instance i-38e485d8 to the Amazon S3 bucket
myexportbucket.

Command::

  aws ec2 create-instance-export-task --description "RHEL5 instance" --instance-id i-38e485d8 --target-environment vmware --export-to-s3-task DiskImageFormat=vmdk,ContainerFormat=ova,S3Bucket=myexportbucket,S3Prefix=RHEL5

Output::

  {
      "ExportTask": {
          "State": "active",
          "InstanceExportDetails": {
              "InstanceId": "i-38e485d8",
              "TargetEnvironment": "vmware"
          },
          "ExportToS3Task": {
              "S3Bucket": "myexportbucket",
              "S3Key": "RHEL5export-i-fh8sjjsq.ova",
              "DiskImageFormat": "vmdk",
              "ContainerFormat": "ova"
          },
          "Description": "RHEL5 instance",
          "ExportTaskId": "export-i-fh8sjjsq"
      }
  }


======
Output
======

ExportTask -> (structure)

  

  Information about the instance export task.

  

  ExportTaskId -> (string)

    

    The ID of the export task.

    

    

  Description -> (string)

    

    A description of the resource being exported.

    

    

  State -> (string)

    

    The state of the export task.

    

    

  StatusMessage -> (string)

    

    The status message related to the export task.

    

    

  InstanceExportDetails -> (structure)

    

    Information about the instance to export.

    

    InstanceId -> (string)

      

      The ID of the resource being exported.

      

      

    TargetEnvironment -> (string)

      

      The target virtualization environment.

      

      

    

  ExportToS3Task -> (structure)

    

    Information about the export task.

    

    DiskImageFormat -> (string)

      

      The format for the exported image.

      

      

    ContainerFormat -> (string)

      

      The container format used to combine disk images with metadata (such as OVF). If absent, only the disk image is exported.

      

      

    S3Bucket -> (string)

      

      The S3 bucket for the destination image. The destination bucket must exist and grant WRITE and READ_ACP permissions to the AWS account ``vm-import-export@amazon.com`` .

      

      

    S3Key -> (string)

      

      The encryption key for your S3 bucket.

      

      

    

  



.. _Exporting EC2 Instances: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ExportingEC2Instances.html
