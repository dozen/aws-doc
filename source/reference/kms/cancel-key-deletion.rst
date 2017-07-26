[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms cancel-key-deletion:


*******************
cancel-key-deletion
*******************



===========
Description
===========



Cancels the deletion of a customer master key (CMK). When this operation is successful, the CMK is set to the ``Disabled`` state. To enable a CMK, use  enable-key .

 

For more information about scheduling and canceling deletion of a CMK, see `Deleting Customer Master Keys <http://docs.aws.amazon.com/kms/latest/developerguide/deleting-keys.html>`_ in the *AWS Key Management Service Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kms-2014-11-01/CancelKeyDeletion>`_


========
Synopsis
========

::

    cancel-key-deletion
  --key-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--key-id`` (string)


  The unique identifier for the customer master key (CMK) for which to cancel deletion.

   

  To specify this value, use the unique key ID or the Amazon Resource Name (ARN) of the CMK. Examples:

   

   
  * Unique key ID: 1234abcd-12ab-34cd-56ef-1234567890ab 
   
  * Key ARN: arn:aws:kms:us-east-2:111122223333:key/1234abcd-12ab-34cd-56ef-1234567890ab 
   

   

  To obtain the unique key ID and key ARN for a given CMK, use  list-keys or  describe-key .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

KeyId -> (string)

  

  The unique identifier of the master key for which deletion is canceled.

  

  

