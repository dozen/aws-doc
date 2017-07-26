[ :ref:`aws <cli:aws>` . :ref:`kinesisanalytics <cli:aws kinesisanalytics>` ]

.. _cli:aws kinesisanalytics update-application:


******************
update-application
******************



===========
Description
===========



Updates an existing Amazon Kinesis Analytics application. Using this API, you can update application code, input configuration, and output configuration. 

 

Note that Amazon Kinesis Analytics updates the ``CurrentApplicationVersionId`` each time you update your application. 

 

This operation requires permission for the ``kinesisanalytics:UpdateApplication`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesisanalytics-2015-08-14/UpdateApplication>`_


========
Synopsis
========

::

    update-application
  --application-name <value>
  --current-application-version-id <value>
  --application-update <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  Name of the Amazon Kinesis Analytics application to update.

  

``--current-application-version-id`` (long)


  The current application version ID. You can use the  describe-application operation to get this value.

  

``--application-update`` (structure)


  Describes application updates.

  



JSON Syntax::

  {
    "InputUpdates": [
      {
        "InputId": "string",
        "NamePrefixUpdate": "string",
        "KinesisStreamsInputUpdate": {
          "ResourceARNUpdate": "string",
          "RoleARNUpdate": "string"
        },
        "KinesisFirehoseInputUpdate": {
          "ResourceARNUpdate": "string",
          "RoleARNUpdate": "string"
        },
        "InputSchemaUpdate": {
          "RecordFormatUpdate": {
            "RecordFormatType": "JSON"|"CSV",
            "MappingParameters": {
              "JSONMappingParameters": {
                "RecordRowPath": "string"
              },
              "CSVMappingParameters": {
                "RecordRowDelimiter": "string",
                "RecordColumnDelimiter": "string"
              }
            }
          },
          "RecordEncodingUpdate": "string",
          "RecordColumnUpdates": [
            {
              "Name": "string",
              "Mapping": "string",
              "SqlType": "string"
            }
            ...
          ]
        },
        "InputParallelismUpdate": {
          "CountUpdate": integer
        }
      }
      ...
    ],
    "ApplicationCodeUpdate": "string",
    "OutputUpdates": [
      {
        "OutputId": "string",
        "NameUpdate": "string",
        "KinesisStreamsOutputUpdate": {
          "ResourceARNUpdate": "string",
          "RoleARNUpdate": "string"
        },
        "KinesisFirehoseOutputUpdate": {
          "ResourceARNUpdate": "string",
          "RoleARNUpdate": "string"
        },
        "DestinationSchemaUpdate": {
          "RecordFormatType": "JSON"|"CSV"
        }
      }
      ...
    ],
    "ReferenceDataSourceUpdates": [
      {
        "ReferenceId": "string",
        "TableNameUpdate": "string",
        "S3ReferenceDataSourceUpdate": {
          "BucketARNUpdate": "string",
          "FileKeyUpdate": "string",
          "ReferenceRoleARNUpdate": "string"
        },
        "ReferenceSchemaUpdate": {
          "RecordFormat": {
            "RecordFormatType": "JSON"|"CSV",
            "MappingParameters": {
              "JSONMappingParameters": {
                "RecordRowPath": "string"
              },
              "CSVMappingParameters": {
                "RecordRowDelimiter": "string",
                "RecordColumnDelimiter": "string"
              }
            }
          },
          "RecordEncoding": "string",
          "RecordColumns": [
            {
              "Name": "string",
              "Mapping": "string",
              "SqlType": "string"
            }
            ...
          ]
        }
      }
      ...
    ],
    "CloudWatchLoggingOptionUpdates": [
      {
        "CloudWatchLoggingOptionId": "string",
        "LogStreamARNUpdate": "string",
        "RoleARNUpdate": "string"
      }
      ...
    ]
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

