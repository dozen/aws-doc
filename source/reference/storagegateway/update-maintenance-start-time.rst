[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway update-maintenance-start-time:


*****************************
update-maintenance-start-time
*****************************



===========
Description
===========



Updates a gateway's weekly maintenance start time information, including day and time of the week. The maintenance time is the time in your gateway's time zone.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/UpdateMaintenanceStartTime>`_


========
Synopsis
========

::

    update-maintenance-start-time
  --gateway-arn <value>
  --hour-of-day <value>
  --minute-of-hour <value>
  --day-of-week <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--gateway-arn`` (string)


  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

``--hour-of-day`` (integer)


  The hour component of the maintenance start time represented as *hh* , where *hh* is the hour (00 to 23). The hour of the day is in the time zone of the gateway.

  

``--minute-of-hour`` (integer)


  The minute component of the maintenance start time represented as *mm* , where *mm* is the minute (00 to 59). The minute of the hour is in the time zone of the gateway.

  

``--day-of-week`` (integer)


  The maintenance start time day of the week represented as an ordinal number from 0 to 6, where 0 represents Sunday and 6 Saturday.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

GatewayARN -> (string)

  

  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

  

