[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms import-key-material:


*******************
import-key-material
*******************



===========
Description
===========



Imports key material into an AWS KMS customer master key (CMK) from your existing key management infrastructure. For more information about importing key material into AWS KMS, see `Importing Key Material <http://docs.aws.amazon.com/kms/latest/developerguide/importing-keys.html>`_ in the *AWS Key Management Service Developer Guide* .

 

You must specify the key ID of the CMK to import the key material into. This CMK's ``Origin`` must be ``EXTERNAL`` . You must also send an import token and the encrypted key material. Send the import token that you received in the same  get-parameters-for-import response that contained the public key that you used to encrypt the key material. You must also specify whether the key material expires and if so, when. When the key material expires, AWS KMS deletes the key material and the CMK becomes unusable. To use the CMK again, you can reimport the same key material. If you set an expiration date, you can change it only by reimporting the same key material and specifying a new expiration date.

 

When this operation is successful, the specified CMK's key state changes to ``Enabled`` , and you can use the CMK.

 

After you successfully import key material into a CMK, you can reimport the same key material into that CMK, but you cannot import different key material.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kms-2014-11-01/ImportKeyMaterial>`_


========
Synopsis
========

::

    import-key-material
  --key-id <value>
  --import-token <value>
  --encrypted-key-material <value>
  [--valid-to <value>]
  [--expiration-model <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--key-id`` (string)


  The identifier of the CMK to import the key material into. The CMK's ``Origin`` must be ``EXTERNAL`` .

   

  A valid identifier is the unique key ID or the Amazon Resource Name (ARN) of the CMK. Examples:

   

   
  * Unique key ID: ``1234abcd-12ab-34cd-56ef-1234567890ab``   
   
  * Key ARN: ``arn:aws:kms:us-east-2:111122223333:key/1234abcd-12ab-34cd-56ef-1234567890ab``   
   

  

``--import-token`` (blob)


  The import token that you received in the response to a previous  get-parameters-for-import request. It must be from the same response that contained the public key that you used to encrypt the key material.

  

``--encrypted-key-material`` (blob)


  The encrypted key material to import. It must be encrypted with the public key that you received in the response to a previous  get-parameters-for-import request, using the wrapping algorithm that you specified in that request.

  

``--valid-to`` (timestamp)


  The time at which the imported key material expires. When the key material expires, AWS KMS deletes the key material and the CMK becomes unusable. You must omit this parameter when the ``ExpirationModel`` parameter is set to ``KEY_MATERIAL_DOES_NOT_EXPIRE`` . Otherwise it is required.

  

``--expiration-model`` (string)


  Specifies whether the key material expires. The default is ``KEY_MATERIAL_EXPIRES`` , in which case you must include the ``ValidTo`` parameter. When this parameter is set to ``KEY_MATERIAL_DOES_NOT_EXPIRE`` , you must omit the ``ValidTo`` parameter.

  

  Possible values:

  
  *   ``KEY_MATERIAL_EXPIRES``

  
  *   ``KEY_MATERIAL_DOES_NOT_EXPIRE``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

