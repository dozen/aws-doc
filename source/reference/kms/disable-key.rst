[ :ref:`aws <cli:aws>` . :ref:`kms <cli:aws kms>` ]

.. _cli:aws kms disable-key:


***********
disable-key
***********



===========
Description
===========



Sets the state of a customer master key (CMK) to disabled, thereby preventing its use for cryptographic operations. For more information about how key state affects the use of a CMK, see `How Key State Affects the Use of a Customer Master Key <http://docs.aws.amazon.com/kms/latest/developerguide/key-state.html>`_ in the *AWS Key Management Service Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kms-2014-11-01/DisableKey>`_


========
Synopsis
========

::

    disable-key
  --key-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--key-id`` (string)


  A unique identifier for the CMK.

   

  Use the CMK's unique identifier or its Amazon Resource Name (ARN). For example:

   

   
  * Unique ID: 1234abcd-12ab-34cd-56ef-1234567890ab 
   
  * ARN: arn:aws:kms:us-east-2:111122223333:key/1234abcd-12ab-34cd-56ef-1234567890ab 
   

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None