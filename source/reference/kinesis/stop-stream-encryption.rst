[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis stop-stream-encryption:


**********************
stop-stream-encryption
**********************



===========
Description
===========



Disables server-side encryption for a specified stream. 

 

Stopping encryption is an asynchronous operation. Upon receiving the request, Amazon Kinesis returns immediately and sets the status of the stream to ``UPDATING`` . After the update is complete, Amazon Kinesis sets the status of the stream back to ``ACTIVE`` . Stopping encryption normally takes a few seconds to complete but it can take minutes. You can continue to read and write data to your stream while its status is ``UPDATING`` . Once the status of the stream is ``ACTIVE`` records written to the stream will no longer be encrypted by the Amazon Kinesis Streams service. 

 

API Limits: You can successfully disable server-side encryption 25 times in a rolling 24 hour period. 

 

Note: It can take up to 5 seconds after the stream is in an ``ACTIVE`` status before all records written to the stream are no longer subject to encryption. After you’ve disabled encryption, you can verify encryption was not applied by inspecting the API response from ``put-record`` or ``put-records`` .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesis-2013-12-02/StopStreamEncryption>`_


========
Synopsis
========

::

    stop-stream-encryption
  --stream-name <value>
  --encryption-type <value>
  --key-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stream-name`` (string)


  The name of the stream on which to stop encrypting records.

  

``--encryption-type`` (string)


  The encryption type. This parameter can be one of the following values:

   

   
  * ``NONE`` : Not valid for this operation. An ``InvalidOperationException`` will be thrown. 
   
  * ``KMS`` : Use server-side encryption on the records in the stream using a customer-managed KMS key. 
   

  

  Possible values:

  
  *   ``NONE``

  
  *   ``KMS``

  

  

``--key-id`` (string)


  The GUID for the customer-managed key that was used for encryption.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None