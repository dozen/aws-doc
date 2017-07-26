[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-export-tasks:


*********************
describe-export-tasks
*********************



===========
Description
===========



Describes one or more of your export tasks.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeExportTasks>`_


========
Synopsis
========

::

    describe-export-tasks
  [--export-task-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--export-task-ids`` (list)


  One or more export task IDs.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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
      ]
  }



======
Output
======

ExportTasks -> (list)

  

  Information about the export tasks.

  

  (structure)

    

    Describes an instance export task.

    

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

      

      

    

  

