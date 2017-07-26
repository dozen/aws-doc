[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway retrieve-tape-archive:


*********************
retrieve-tape-archive
*********************



===========
Description
===========



Retrieves an archived virtual tape from the virtual tape shelf (VTS) to a gateway-VTL. Virtual tapes archived in the VTS are not associated with any gateway. However after a tape is retrieved, it is associated with a gateway, even though it is also listed in the VTS.

 

Once a tape is successfully retrieved to a gateway, it cannot be retrieved again to another gateway. You must archive the tape again before you can retrieve it to another gateway.



========
Synopsis
========

::

    retrieve-tape-archive
  --tape-arn <value>
  --gateway-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--tape-arn`` (string)


  The Amazon Resource Name (ARN) of the virtual tape you want to retrieve from the virtual tape shelf (VTS). 

  

``--gateway-arn`` (string)


  The Amazon Resource Name (ARN) of the gateway you want to retrieve the virtual tape to. Use the  list-gateways operation to return a list of gateways for your account and region.

   

  You retrieve archived virtual tapes to only one gateway and the gateway must be a gateway-VTL.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TapeARN -> (string)

  

  The Amazon Resource Name (ARN) of the retrieved virtual tape.

  

  

