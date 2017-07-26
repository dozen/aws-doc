[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway update-maintenance-start-time:


*****************************
update-maintenance-start-time
*****************************



===========
Description
===========



This operation updates a gateway's weekly maintenance start time information, including day and time of the week. The maintenance time is the time in your gateway's time zone.



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
  [--generate-cli-skeleton]




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


  The maintenance start time day of the week.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

GatewayARN -> (string)

  

  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

  

