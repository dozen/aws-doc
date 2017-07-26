[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms schedule-key-deletion:


*********************
schedule-key-deletion
*********************



===========
Description
===========



Schedules the deletion of a customer master key (CMK). You may provide a waiting period, specified in days, before deletion occurs. If you do not provide a waiting period, the default period of 30 days is used. When this operation is successful, the state of the CMK changes to ``PendingDeletion`` . Before the waiting period ends, you can use  cancel-key-deletion to cancel the deletion of the CMK. After the waiting period ends, AWS KMS deletes the CMK and all AWS KMS data associated with it, including all aliases that point to it.

 

.. warning::

   

  Deleting a CMK is a destructive and potentially dangerous operation. When a CMK is deleted, all data that was encrypted under the CMK is rendered unrecoverable. To restrict the use of a CMK without deleting it, use  disable-key .

   

 

For more information about scheduling a CMK for deletion, go to `Deleting Customer Master Keys`_ in the *AWS Key Management Service Developer Guide* .



========
Synopsis
========

::

    schedule-key-deletion
  --key-id <value>
  [--pending-window-in-days <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--key-id`` (string)


  The unique identifier for the customer master key (CMK) to delete.

   

  To specify this value, use the unique key ID or the Amazon Resource Name (ARN) of the CMK. Examples: 

   
  * Unique key ID: 1234abcd-12ab-34cd-56ef-1234567890ab
   
  * Key ARN: arn:aws:kms:us-west-2:111122223333:key/1234abcd-12ab-34cd-56ef-1234567890ab
   

   

   

  To obtain the unique key ID and key ARN for a given CMK, use  list-keys or  describe-key .

  

``--pending-window-in-days`` (integer)


  The waiting period, specified in number of days. After the waiting period ends, AWS KMS deletes the customer master key (CMK).

   

  This value is optional. If you include a value, it must be between 7 and 30, inclusive. If you do not include a value, it defaults to 30.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

KeyId -> (string)

  

  The unique identifier of the customer master key (CMK) for which deletion is scheduled.

  

  

DeletionDate -> (timestamp)

  

  The date and time after which AWS KMS deletes the customer master key (CMK).

  

  



.. _Deleting Customer Master Keys: http://docs.aws.amazon.com/kms/latest/developerguide/deleting-keys.html
