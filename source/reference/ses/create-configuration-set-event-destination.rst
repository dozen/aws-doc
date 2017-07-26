[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses create-configuration-set-event-destination:


******************************************
create-configuration-set-event-destination
******************************************



===========
Description
===========



Creates a configuration set event destination.

 

.. note::

   

  When you create or update an event destination, you must provide one, and only one, destination. The destination can be either Amazon CloudWatch or Amazon Kinesis Firehose.

   

 

An event destination is the AWS service to which Amazon SES publishes the email sending events associated with a configuration set. For information about using configuration sets, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/monitor-sending-activity.html>`_ .

 

This action is throttled at one request per second.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/CreateConfigurationSetEventDestination>`_


========
Synopsis
========

::

    create-configuration-set-event-destination
  --configuration-set-name <value>
  --event-destination <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--configuration-set-name`` (string)


  The name of the configuration set to which to apply the event destination.

  

``--event-destination`` (structure)


  An object that describes the AWS service to which Amazon SES will publish the email sending events associated with the specified configuration set.

  



JSON Syntax::

  {
    "Name": "string",
    "Enabled": true|false,
    "MatchingEventTypes": ["send"|"reject"|"bounce"|"complaint"|"delivery", ...],
    "KinesisFirehoseDestination": {
      "IAMRoleARN": "string",
      "DeliveryStreamARN": "string"
    },
    "CloudWatchDestination": {
      "DimensionConfigurations": [
        {
          "DimensionName": "string",
          "DimensionValueSource": "messageTag"|"emailHeader",
          "DefaultDimensionValue": "string"
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

