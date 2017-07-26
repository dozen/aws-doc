[ :ref:`aws <cli:aws>` . :ref:`kinesisanalytics <cli:aws kinesisanalytics>` ]

.. _cli:aws kinesisanalytics add-application-input:


*********************
add-application-input
*********************



===========
Description
===========



Adds a streaming source to your Amazon Kinesis application. For conceptual information, see `Configuring Application input <http://docs.aws.amazon.com/kinesisanalytics/latest/dev/how-it-works-input.html>`_ . 

 

You can add a streaming source either when you create an application or you can use this operation to add a streaming source after you create an application. For more information, see  create-application .

 

Any configuration update, including adding a streaming source using this operation, results in a new version of the application. You can use the  describe-application operation to find the current application version. 

 

This operation requires permissions to perform the ``kinesisanalytics:AddApplicationInput`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesisanalytics-2015-08-14/AddApplicationInput>`_


========
Synopsis
========

::

    add-application-input
  --application-name <value>
  --current-application-version-id <value>
  --input <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  Name of your existing Amazon Kinesis Analytics application to which you want to add the streaming source.

  

``--current-application-version-id`` (long)


  Current version of your Amazon Kinesis Analytics application. You can use the  describe-application operation to find the current application version.

  

``--input`` (structure)


  

  



JSON Syntax::

  {
    "NamePrefix": "string",
    "KinesisStreamsInput": {
      "ResourceARN": "string",
      "RoleARN": "string"
    },
    "KinesisFirehoseInput": {
      "ResourceARN": "string",
      "RoleARN": "string"
    },
    "InputParallelism": {
      "Count": integer
    },
    "InputSchema": {
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

