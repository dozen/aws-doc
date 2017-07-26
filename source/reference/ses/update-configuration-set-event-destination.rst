[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses update-configuration-set-event-destination:


******************************************
update-configuration-set-event-destination
******************************************



===========
Description
===========



Updates the event destination of a configuration set.

 

.. note::

   

  When you create or update an event destination, you must provide one, and only one, destination. The destination can be either Amazon CloudWatch or Amazon Kinesis Firehose.

   

 

Event destinations are associated with configuration sets, which enable you to publish email sending events to Amazon CloudWatch or Amazon Kinesis Firehose. For information about using configuration sets, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/monitor-sending-activity.html>`_ .

 

This action is throttled at one request per second.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/UpdateConfigurationSetEventDestination>`_


========
Synopsis
========

::

    update-configuration-set-event-destination
  --configuration-set-name <value>
  --event-destination <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--configuration-set-name`` (string)


  The name of the configuration set that you want to update.

  

``--event-destination`` (structure)


  The event destination object that you want to apply to the specified configuration set.

  



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

