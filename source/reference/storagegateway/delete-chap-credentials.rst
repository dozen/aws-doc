[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway delete-chap-credentials:


***********************
delete-chap-credentials
***********************



===========
Description
===========



This operation deletes Challenge-Handshake Authentication Protocol (CHAP) credentials for a specified iSCSI target and initiator pair.



========
Synopsis
========

::

    delete-chap-credentials
  --target-arn <value>
  --initiator-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--target-arn`` (string)


  The Amazon Resource Name (ARN) of the iSCSI volume target. Use the  describe-stored-iscsi-volumes operation to return to retrieve the target-arn for specified VolumeARN.

  

``--initiator-name`` (string)


  The iSCSI initiator that connects to the target.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TargetARN -> (string)

  

  The Amazon Resource Name (ARN) of the target.

  

  

InitiatorName -> (string)

  

  The iSCSI initiator that connects to the target.

  

  

