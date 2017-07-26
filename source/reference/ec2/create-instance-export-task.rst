[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-instance-export-task:


***************************
create-instance-export-task
***************************



===========
Description
===========



Exports a running or stopped instance to an S3 bucket.

 

For information about the supported operating systems, image formats, and known limitations for the types of instances you can export, see `Exporting an Instance as a VM Using VM Import/Export <http://docs.aws.amazon.com/vm-import/latest/userguide/vmexport.html>`_ in the *VM Import/Export User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateInstanceExportTask>`_


========
Synopsis
========

::

    create-instance-export-task
  [--description <value>]
  [--export-to-s3-task <value>]
  --instance-id <value>
  [--target-environment <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--description`` (string)


  A description for the conversion task or the resource being exported. The maximum length is 255 bytes.

  

``--export-to-s3-task`` (structure)


  The format and location for an instance export task.

  



Shorthand Syntax::

    ContainerFormat=string,DiskImageFormat=string,S3Bucket=string,S3Prefix=string




JSON Syntax::

  {
    "ContainerFormat": "ova",
    "DiskImageFormat": "VMDK"|"RAW"|"VHD",
    "S3Bucket": "string",
    "S3Prefix": "string"
  }



``--instance-id`` (string)


  The ID of the instance.

  

``--target-environment`` (string)


  The target virtualization environment.

  

  Possible values:

  
  *   ``citrix``

  
  *   ``vmware``

  
  *   ``microsoft``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To export an instance**

This example command creates a task to export the instance i-1234567890abcdef0 to the Amazon S3 bucket
myexportbucket.

Command::

  aws ec2 create-instance-export-task --description "RHEL5 instance" --instance-id i-1234567890abcdef0 --target-environment vmware --export-to-s3-task DiskImageFormat=vmdk,ContainerFormat=ova,S3Bucket=myexportbucket,S3Prefix=RHEL5

Output::

  {
      "ExportTask": {
          "State": "active",
          "InstanceExportDetails": {
              "InstanceId": "i-1234567890abcdef0",
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

  

  Description -> (string)

    

    A description of the resource being exported.

    

    

  ExportTaskId -> (string)

    

    The ID of the export task.

    

    

  ExportToS3Task -> (structure)

    

    Information about the export task.

    

    ContainerFormat -> (string)

      

      The container format used to combine disk images with metadata (such as OVF). If absent, only the disk image is exported.

      

      

    DiskImageFormat -> (string)

      

      The format for the exported image.

      

      

    S3Bucket -> (string)

      

      The S3 bucket for the destination image. The destination bucket must exist and grant WRITE and READ_ACP permissions to the AWS account ``vm-import-export@amazon.com`` .

      

      

    S3Key -> (string)

      

      The encryption key for your S3 bucket.

      

      

    

  InstanceExportDetails -> (structure)

    

    Information about the instance to export.

    

    InstanceId -> (string)

      

      The ID of the resource being exported.

      

      

    TargetEnvironment -> (string)

      

      The target virtualization environment.

      

      

    

  State -> (string)

    

    The state of the export task.

    

    

  StatusMessage -> (string)

    

    The status message related to the export task.

    

    

  

