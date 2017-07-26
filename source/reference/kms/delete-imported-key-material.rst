[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms delete-imported-key-material:


****************************
delete-imported-key-material
****************************



===========
Description
===========



Deletes key material that you previously imported and makes the specified customer master key (CMK) unusable. For more information about importing key material into AWS KMS, see `Importing Key Material <http://docs.aws.amazon.com/kms/latest/developerguide/importing-keys.html>`_ in the *AWS Key Management Service Developer Guide* .

 

When the specified CMK is in the ``PendingDeletion`` state, this operation does not change the CMK's state. Otherwise, it changes the CMK's state to ``PendingImport`` .

 

After you delete key material, you can use  import-key-material to reimport the same key material into the CMK.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kms-2014-11-01/DeleteImportedKeyMaterial>`_


========
Synopsis
========

::

    delete-imported-key-material
  --key-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--key-id`` (string)


  The identifier of the CMK whose key material to delete. The CMK's ``Origin`` must be ``EXTERNAL`` .

   

  A valid identifier is the unique key ID or the Amazon Resource Name (ARN) of the CMK. Examples:

   

   
  * Unique key ID: ``1234abcd-12ab-34cd-56ef-1234567890ab``   
   
  * Key ARN: ``arn:aws:kms:us-east-2:111122223333:key/1234abcd-12ab-34cd-56ef-1234567890ab``   
   

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None