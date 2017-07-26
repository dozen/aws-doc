[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline get-pipeline-definition:


***********************
get-pipeline-definition
***********************



===========
Description
===========



Gets the definition of the specified pipeline. You can call ``get-pipeline-definition`` to retrieve the pipeline definition that you provided using  put-pipeline-definition .



========
Synopsis
========

::

    get-pipeline-definition
  --pipeline-id <value>
  [--pipeline-version <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--pipeline-id`` (string)


  The ID of the pipeline.

  

``--pipeline-version`` (string)


  The version of the pipeline definition to retrieve. Set this parameter to ``latest`` (default) to use the last definition saved to the pipeline or ``active`` to use the last definition that was activated.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON pipeline-version provided. The JSON pipeline-version follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get a pipeline definition**

This example gets the pipeline definition for the specified pipeline::

   aws datapipeline get-pipeline-definition --pipeline-id df-00627471SOVYZEXAMPLE
   
The following is example output::

  {
    "parameters": [
        {
            "type": "AWS::S3::ObjectKey",
            "id": "myS3OutputLoc",
            "description": "S3 output folder"
        },
        {
            "default": "s3://us-east-1.elasticmapreduce.samples/pig-apache-logs/data",
            "type": "AWS::S3::ObjectKey",
            "id": "myS3InputLoc",
            "description": "S3 input folder"
        },
        {
            "default": "grep -rc \"GET\" ${INPUT1_STAGING_DIR}/* > ${OUTPUT1_STAGING_DIR}/output.txt",
            "type": "String",
            "id": "myShellCmd",
            "description": "Shell command to run"
        }
    ],
    "objects": [
        {
            "type": "Ec2Resource",
            "terminateAfter": "20 Minutes",
            "instanceType": "t1.micro",
            "id": "EC2ResourceObj",
            "name": "EC2ResourceObj"
        },
        {
            "name": "Default",
            "failureAndRerunMode": "CASCADE",
            "resourceRole": "DataPipelineDefaultResourceRole",
            "schedule": {
                "ref": "DefaultSchedule"
            },
            "role": "DataPipelineDefaultRole",
            "scheduleType": "cron",
            "id": "Default"
        },
        {
            "directoryPath": "#{myS3OutputLoc}/#{format(@scheduledStartTime, 'YYYY-MM-dd-HH-mm-ss')}",
            "type": "S3DataNode",
            "id": "S3OutputLocation",
            "name": "S3OutputLocation"
        },
        {
            "directoryPath": "#{myS3InputLoc}",
            "type": "S3DataNode",
            "id": "S3InputLocation",
            "name": "S3InputLocation"
        },
        {
            "startAt": "FIRST_ACTIVATION_DATE_TIME",
            "name": "Every 15 minutes",
            "period": "15 minutes",
            "occurrences": "4",
            "type": "Schedule",
            "id": "DefaultSchedule"
        },
        {
            "name": "ShellCommandActivityObj",
            "command": "#{myShellCmd}",
            "output": {
                "ref": "S3OutputLocation"
            },
            "input": {
                "ref": "S3InputLocation"
            },
            "stage": "true",
            "type": "ShellCommandActivity",
            "id": "ShellCommandActivityObj",
            "runsOn": {
                "ref": "EC2ResourceObj"
            }
        }
    ],
    "values": {
        "myS3OutputLoc": "s3://my-s3-bucket/",
        "myS3InputLoc": "s3://us-east-1.elasticmapreduce.samples/pig-apache-logs/data",
        "myShellCmd": "grep -rc \"GET\" ${INPUT1_STAGING_DIR}/* > ${OUTPUT1_STAGING_DIR}/output.txt"
    }
  }


======
Output
======
The output of this command is the pipeline definition, which is documented in the `Pipeline Definition File Syntax <http://docs.aws.amazon.com/datapipeline/latest/DeveloperGuide/dp-writing-pipeline-definition.html>`__