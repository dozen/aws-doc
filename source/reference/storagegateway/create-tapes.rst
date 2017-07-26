[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway create-tapes:


************
create-tapes
************



===========
Description
===========



Creates one or more virtual tapes. You write data to the virtual tapes and then archive the tapes. This operation is only supported in the tape gateway architecture.

 

.. note::

   

  Cache storage must be allocated to the gateway before you can create virtual tapes. Use the  add-cache operation to add cache storage to a gateway. 

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/CreateTapes>`_


========
Synopsis
========

::

    create-tapes
  --gateway-arn <value>
  --tape-size-in-bytes <value>
  --client-token <value>
  --num-tapes-to-create <value>
  --tape-barcode-prefix <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--gateway-arn`` (string)


  The unique Amazon Resource Name (ARN) that represents the gateway to associate the virtual tapes with. Use the  list-gateways operation to return a list of gateways for your account and region.

  

``--tape-size-in-bytes`` (long)


  The size, in bytes, of the virtual tapes that you want to create.

   

  .. note::

     

    The size must be aligned by gigabyte (1024*1024*1024 byte).

     

  

``--client-token`` (string)


  A unique identifier that you use to retry a request. If you retry a request, use the same ``client-token`` you specified in the initial request.

   

  .. note::

     

    Using the same ``client-token`` prevents creating the tape multiple times.

     

  

``--num-tapes-to-create`` (integer)


  The number of virtual tapes that you want to create.

  

``--tape-barcode-prefix`` (string)


  A prefix that you append to the barcode of the virtual tape you are creating. This prefix makes the barcode unique.

   

  .. note::

     

    The prefix must be 1 to 4 characters in length and must be one of the uppercase letters from A to Z.

     

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TapeARNs -> (list)

  

  A list of unique Amazon Resource Names (ARNs) that represents the virtual tapes that were created.

  

  (string)

    

    

  

