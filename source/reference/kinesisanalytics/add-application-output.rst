[ :ref:`aws <cli:aws>` . :ref:`kinesisanalytics <cli:aws kinesisanalytics>` ]

.. _cli:aws kinesisanalytics add-application-output:


**********************
add-application-output
**********************



===========
Description
===========



Adds an external destination to your Amazon Kinesis Analytics application.

 

If you want Amazon Kinesis Analytics to deliver data from an in-application stream within your application to an external destination (such as an Amazon Kinesis stream or a Firehose delivery stream), you add the relevant configuration to your application using this operation. You can configure one or more outputs for your application. Each output configuration maps an in-application stream and an external destination.

 

You can use one of the output configurations to deliver data from your in-application error stream to an external destination so that you can analyze the errors. For conceptual information, see `Understanding Application application-output (Destination) <http://docs.aws.amazon.com/kinesisanalytics/latest/dev/how-it-works-output.html>`_ . 

 

Note that any configuration update, including adding a streaming source using this operation, results in a new version of the application. You can use the  describe-application operation to find the current application version.

 

For the limits on the number of application inputs and outputs you can configure, see `Limits <http://docs.aws.amazon.com/kinesisanalytics/latest/dev/limits.html>`_ .

 

This operation requires permissions to perform the ``kinesisanalytics:AddApplicationOutput`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesisanalytics-2015-08-14/AddApplicationOutput>`_


========
Synopsis
========

::

    add-application-output
  --application-name <value>
  --current-application-version-id <value>
  --application-output <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-name`` (string)


  Name of the application to which you want to add the output configuration.

  

``--current-application-version-id`` (long)


  Version of the application to which you want add the output configuration. You can use the  describe-application operation to get the current application version. If the version specified is not the current version, the ``ConcurrentModificationException`` is returned. 

  

``--application-output`` (structure)


  An array of objects, each describing one output configuration. In the output configuration, you specify the name of an in-application stream, a destination (that is, an Amazon Kinesis stream or an Amazon Kinesis Firehose delivery stream), and record the formation to use when writing to the destination.

  



Shorthand Syntax::

    Name=string,KinesisStreamsOutput={ResourceARN=string,RoleARN=string},KinesisFirehoseOutput={ResourceARN=string,RoleARN=string},DestinationSchema={RecordFormatType=string}




JSON Syntax::

  {
    "Name": "string",
    "KinesisStreamsOutput": {
      "ResourceARN": "string",
      "RoleARN": "string"
    },
    "KinesisFirehoseOutput": {
      "ResourceARN": "string",
      "RoleARN": "string"
    },
    "DestinationSchema": {
      "RecordFormatType": "JSON"|"CSV"
    }
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

