[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-export-tasks:


*********************
describe-export-tasks
*********************



===========
Description
===========



Describes one or more of your export tasks.



========
Synopsis
========

::

    describe-export-tasks
  [--export-task-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--export-task-ids`` (list)


  One or more export task IDs.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To list details about an instance export task**

This example describes the export task with ID export-i-fh8sjjsq.

Command::

  aws ec2 describe-export-tasks --export-task-ids export-i-fh8sjjsq

Output::

  {
      "ExportTasks": [
          {
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
      ]
  }



======
Output
======

ExportTasks -> (list)

  

  Information about the export tasks.

  

  (structure)

    

    Describes an instance export task.

    

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

        

        

      

    

  

