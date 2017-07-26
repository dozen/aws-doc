[ :ref:`aws <cli:aws>` . :ref:`kinesisanalytics <cli:aws kinesisanalytics>` ]

.. _cli:aws kinesisanalytics add-application-reference-data-source:


*************************************
add-application-reference-data-source
*************************************



===========
Description
===========



Adds a reference data source to an existing application.

 

Amazon Kinesis Analytics reads reference data (that is, an Amazon S3 object) and creates an in-application table within your application. In the request, you provide the source (S3 bucket name and object key name), name of the in-application table to create, and the necessary mapping information that describes how data in Amazon S3 object maps to columns in the resulting in-application table.

 

For conceptual information, see `Configuring Application Input <http://docs.aws.amazon.com/kinesisanalytics/latest/dev/how-it-works-input.html>`_ . For the limits on data sources you can add to your application, see `Limits <http://docs.aws.amazon.com/kinesisanalytics/latest/dev/limits.html>`_ . 

 

This operation requires permissions to perform the ``kinesisanalytics:AddApplicationOutput`` action. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesisanalytics-2015-08-14/AddApplicationReferenceDataSource>`_


========
Synopsis
========

::

    add-application-reference-data-source
  --application-name <value>
  --current-application-version-id <value>
  --reference-data-source <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  Name of an existing application.

  

``--current-application-version-id`` (long)


  Version of the application for which you are adding the reference data source. You can use the  describe-application operation to get the current application version. If the version specified is not the current version, the ``ConcurrentModificationException`` is returned.

  

``--reference-data-source`` (structure)


  The reference data source can be an object in your Amazon S3 bucket. Amazon Kinesis Analytics reads the object and copies the data into the in-application table that is created. You provide an S3 bucket, object key name, and the resulting in-application table that is created. You must also provide an IAM role with the necessary permissions that Amazon Kinesis Analytics can assume to read the object from your S3 bucket on your behalf.

  



JSON Syntax::

  {
    "TableName": "string",
    "S3ReferenceDataSource": {
      "BucketARN": "string",
      "FileKey": "string",
      "ReferenceRoleARN": "string"
    },
    "ReferenceSchema": {
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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

