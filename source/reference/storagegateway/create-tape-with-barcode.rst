[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway create-tape-with-barcode:


************************
create-tape-with-barcode
************************



===========
Description
===========



Creates a virtual tape by using your own barcode. You write data to the virtual tape and then archive the tape.

 

.. note::

  Cache storage must be allocated to the gateway before you can create a virtual tape. Use the  add-cache operation to add cache storage to a gateway.



========
Synopsis
========

::

    create-tape-with-barcode
  --gateway-arn <value>
  --tape-size-in-bytes <value>
  --tape-barcode <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--gateway-arn`` (string)


  The unique Amazon Resource Name (ARN) that represents the gateway to associate the virtual tape with. Use the  list-gateways operation to return a list of gateways for your account and region.

  

``--tape-size-in-bytes`` (long)


  The size, in bytes, of the virtual tape that you want to create.

   

  .. note::

    The size must be aligned by gigabyte (1024*1024*1024 byte).

  

``--tape-barcode`` (string)


  The barcode that you want to assign to the tape.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TapeARN -> (string)

  

  A unique Amazon Resource Name (ARN) that represents the virtual tape that was created.

  

  

