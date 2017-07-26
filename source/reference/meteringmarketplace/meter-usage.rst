[ :ref:`aws <cli:aws>` . :ref:`meteringmarketplace <cli:aws meteringmarketplace>` ]

.. _cli:aws meteringmarketplace meter-usage:


***********
meter-usage
***********



===========
Description
===========



API to emit metering records. For identical requests, the API is idempotent. It simply returns the metering record ID.

 

meter-usage is authenticated on the buyer's AWS account, generally when running from an EC2 instance on the AWS Marketplace.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/meteringmarketplace-2016-01-14/MeterUsage>`_


========
Synopsis
========

::

    meter-usage
  --product-code <value>
  --timestamp <value>
  --usage-dimension <value>
  --usage-quantity <value>
  --dry-run | --no-dry-run
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--product-code`` (string)


  Product code is used to uniquely identify a product in AWS Marketplace. The product code should be the same as the one used during the publishing of a new product.

  

``--timestamp`` (timestamp)


  timestamp of the hour, recorded in UTC. The seconds and milliseconds portions of the timestamp will be ignored.

  

``--usage-dimension`` (string)


  It will be one of the fcp dimension name provided during the publishing of the product.

  

``--usage-quantity`` (integer)


  Consumption value for the hour.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the permissions required for the action, but does not make the request. If you have the permissions, the request returns DryRunOperation; otherwise, it returns UnauthorizedException.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

MeteringRecordId -> (string)

  

  

