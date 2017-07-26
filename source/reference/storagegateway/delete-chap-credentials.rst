[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway delete-chap-credentials:


***********************
delete-chap-credentials
***********************



===========
Description
===========



Deletes Challenge-Handshake Authentication Protocol (CHAP) credentials for a specified iSCSI target and initiator pair.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/DeleteChapCredentials>`_


========
Synopsis
========

::

    delete-chap-credentials
  --target-arn <value>
  --initiator-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--target-arn`` (string)


  The Amazon Resource Name (ARN) of the iSCSI volume target. Use the  describe-stored-iscsi-volumes operation to return to retrieve the target-arn for specified VolumeARN.

  

``--initiator-name`` (string)


  The iSCSI initiator that connects to the target.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TargetARN -> (string)

  

  The Amazon Resource Name (ARN) of the target.

  

  

InitiatorName -> (string)

  

  The iSCSI initiator that connects to the target.

  

  

