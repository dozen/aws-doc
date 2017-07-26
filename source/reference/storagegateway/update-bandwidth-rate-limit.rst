[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway update-bandwidth-rate-limit:


***************************
update-bandwidth-rate-limit
***************************



===========
Description
===========



This operation updates the bandwidth rate limits of a gateway. You can update both the upload and download bandwidth rate limit or specify only one of the two. If you don't set a bandwidth rate limit, the existing rate limit remains.

 

By default, a gateway's bandwidth rate limits are not set. If you don't set any limit, the gateway does not have any limitations on its bandwidth usage and could potentially use the maximum available bandwidth.

 

To specify which gateway to update, use the Amazon Resource Name (ARN) of the gateway in your request.



========
Synopsis
========

::

    update-bandwidth-rate-limit
  --gateway-arn <value>
  [--average-upload-rate-limit-in-bits-per-sec <value>]
  [--average-download-rate-limit-in-bits-per-sec <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--gateway-arn`` (string)


  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

``--average-upload-rate-limit-in-bits-per-sec`` (long)


  The average upload bandwidth rate limit in bits per second.

  

``--average-download-rate-limit-in-bits-per-sec`` (long)


  The average download bandwidth rate limit in bits per second.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

GatewayARN -> (string)

  

  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

  

