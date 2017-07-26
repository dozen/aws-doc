[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway list-tapes:


**********
list-tapes
**********



===========
Description
===========



Lists virtual tapes in your virtual tape library (VTL) and your virtual tape shelf (VTS). You specify the tapes to list by specifying one or more tape Amazon Resource Names (ARNs). If you don't specify a tape ARN, the operation lists all virtual tapes in both your VTL and VTS.

 

This operation supports pagination. By default, the operation returns a maximum of up to 100 tapes. You can optionally specify the ``Limit`` parameter in the body to limit the number of tapes in the response. If the number of tapes returned in the response is truncated, the response includes a ``marker`` element that you can use in your subsequent request to retrieve the next set of tapes. This operation is only supported in the tape gateway architecture.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/ListTapes>`_


========
Synopsis
========

::

    list-tapes
  [--tape-arns <value>]
  [--marker <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--tape-arns`` (list)


  The Amazon Resource Name (ARN) of each of the tapes you want to list. If you don't specify a tape ARN, the response lists all tapes in both your VTL and VTS.

  



Syntax::

  "string" "string" ...



``--marker`` (string)


  A string that indicates the position at which to begin the returned list of tapes.

  

``--limit`` (integer)


  An optional number limit for the tapes in the list returned by this call.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TapeInfos -> (list)

  

  An array of  TapeInfo objects, where each object describes an a single tape. If there not tapes in the tape library or VTS, then the ``TapeInfos`` is an empty array.

  

  (structure)

    

    Describes a virtual tape.

    

    TapeARN -> (string)

      

      The Amazon Resource Name (ARN) of a virtual tape.

      

      

    TapeBarcode -> (string)

      

      The barcode that identifies a specific virtual tape.

      

      

    TapeSizeInBytes -> (long)

      

      The size, in bytes, of a virtual tape.

      

      

    TapeStatus -> (string)

      

      The status of the tape.

      

      

    GatewayARN -> (string)

      

      The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

      

      

    

  

Marker -> (string)

  

  A string that indicates the position at which to begin returning the next list of tapes. Use the marker in your next request to continue pagination of tapes. If there are no more tapes to list, this element does not appear in the response body.

  

  

