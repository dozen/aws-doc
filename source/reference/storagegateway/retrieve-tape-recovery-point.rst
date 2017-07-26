[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway retrieve-tape-recovery-point:


****************************
retrieve-tape-recovery-point
****************************



===========
Description
===========



Retrieves the recovery point for the specified virtual tape.

 

A recovery point is a point in time view of a virtual tape at which all the data on the tape is consistent. If your gateway crashes, virtual tapes that have recovery points can be recovered to a new gateway.

 

.. note::

  The virtual tape can be retrieved to only one gateway. The retrieved tape is read-only. The virtual tape can be retrieved to only a gateway-VTL. There is no charge for retrieving recovery points.



========
Synopsis
========

::

    retrieve-tape-recovery-point
  --tape-arn <value>
  --gateway-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--tape-arn`` (string)


  The Amazon Resource Name (ARN) of the virtual tape for which you want to retrieve the recovery point.

  

``--gateway-arn`` (string)


  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TapeARN -> (string)

  

  The Amazon Resource Name (ARN) of the virtual tape for which the recovery point was retrieved.

  

  

