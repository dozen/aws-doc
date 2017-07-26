[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway update-chap-credentials:


***********************
update-chap-credentials
***********************



===========
Description
===========



Updates the Challenge-Handshake Authentication Protocol (CHAP) credentials for a specified iSCSI target. By default, a gateway does not have CHAP enabled; however, for added security, you might use it.

 

.. warning::

   

  When you update CHAP credentials, all existing connections on the target are closed and initiators must reconnect with the new credentials.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/UpdateChapCredentials>`_


========
Synopsis
========

::

    update-chap-credentials
  --target-arn <value>
  --secret-to-authenticate-initiator <value>
  --initiator-name <value>
  [--secret-to-authenticate-target <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--target-arn`` (string)


  The Amazon Resource Name (ARN) of the iSCSI volume target. Use the  describe-stored-iscsi-volumes operation to return the target-arn for specified VolumeARN.

  

``--secret-to-authenticate-initiator`` (string)


  The secret key that the initiator (for example, the Windows client) must provide to participate in mutual CHAP with the target.

   

  .. note::

     

    The secret key must be between 12 and 16 bytes when encoded in UTF-8.

     

  

``--initiator-name`` (string)


  The iSCSI initiator that connects to the target.

  

``--secret-to-authenticate-target`` (string)


  The secret key that the target must provide to participate in mutual CHAP with the initiator (e.g. Windows client).

   

  Byte constraints: Minimum bytes of 12. Maximum bytes of 16.

   

  .. note::

     

    The secret key must be between 12 and 16 bytes when encoded in UTF-8.

     

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TargetARN -> (string)

  

  The Amazon Resource Name (ARN) of the target. This is the same target specified in the request.

  

  

InitiatorName -> (string)

  

  The iSCSI initiator that connects to the target. This is the same initiator name specified in the request.

  

  

