[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway describe-maintenance-start-time:


*******************************
describe-maintenance-start-time
*******************************



===========
Description
===========



This operation returns your gateway's weekly maintenance start time including the day and time of the week. Note that values are in terms of the gateway's time zone.



========
Synopsis
========

::

    describe-maintenance-start-time
  --gateway-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--gateway-arn`` (string)


  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

GatewayARN -> (string)

  

  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

  

HourOfDay -> (integer)

  

  

MinuteOfHour -> (integer)

  

  

DayOfWeek -> (integer)

  

  

Timezone -> (string)

  

  

