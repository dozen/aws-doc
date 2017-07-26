[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway retrieve-tape-recovery-point:


****************************
retrieve-tape-recovery-point
****************************



===========
Description
===========



Retrieves the recovery point for the specified virtual tape. This operation is only supported in the tape gateway architecture.

 

A recovery point is a point in time view of a virtual tape at which all the data on the tape is consistent. If your gateway crashes, virtual tapes that have recovery points can be recovered to a new gateway.

 

.. note::

   

  The virtual tape can be retrieved to only one gateway. The retrieved tape is read-only. The virtual tape can be retrieved to only a tape gateway. There is no charge for retrieving recovery points.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/RetrieveTapeRecoveryPoint>`_


========
Synopsis
========

::

    retrieve-tape-recovery-point
  --tape-arn <value>
  --gateway-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--tape-arn`` (string)


  The Amazon Resource Name (ARN) of the virtual tape for which you want to retrieve the recovery point.

  

``--gateway-arn`` (string)


  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TapeARN -> (string)

  

  The Amazon Resource Name (ARN) of the virtual tape for which the recovery point was retrieved.

  

  

