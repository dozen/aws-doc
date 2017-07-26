[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway describe-chap-credentials:


*************************
describe-chap-credentials
*************************



===========
Description
===========



This operation returns an array of Challenge-Handshake Authentication Protocol (CHAP) credentials information for a specified iSCSI target, one for each target-initiator pair.



========
Synopsis
========

::

    describe-chap-credentials
  --target-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--target-arn`` (string)


  The Amazon Resource Name (ARN) of the iSCSI volume target. Use the  describe-stored-iscsi-volumes operation to return to retrieve the target-arn for specified VolumeARN.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ChapCredentials -> (list)

  

  An array of  ChapInfo objects that represent CHAP credentials. Each object in the array contains CHAP credential information for one target-initiator pair. If no CHAP credentials are set, an empty array is returned. CHAP credential information is provided in a JSON object with the following fields:

   

   
  * **InitiatorName** : The iSCSI initiator that connects to the target. 
   
  * **SecretToAuthenticateInitiator** : The secret key that the initiator (for example, the Windows client) must provide to participate in mutual CHAP with the target. 
   
  * **SecretToAuthenticateTarget** : The secret key that the target must provide to participate in mutual CHAP with the initiator (e.g. Windows client). 
   
  * **target-arn** : The Amazon Resource Name (ARN) of the storage volume. 
   

  

  (structure)

    

    Describes Challenge-Handshake Authentication Protocol (CHAP) information that supports authentication between your gateway and iSCSI initiators.

    

    TargetARN -> (string)

      

      The Amazon Resource Name (ARN) of the volume.

       

      *Valid Values* : 50 to 500 lowercase letters, numbers, periods (.), and hyphens (-).

      

      

    SecretToAuthenticateInitiator -> (string)

      

      The secret key that the initiator (for example, the Windows client) must provide to participate in mutual CHAP with the target.

      

      

    InitiatorName -> (string)

      

      The iSCSI initiator that connects to the target.

      

      

    SecretToAuthenticateTarget -> (string)

      

      The secret key that the target must provide to participate in mutual CHAP with the initiator (e.g. Windows client).

      

      

    

  

