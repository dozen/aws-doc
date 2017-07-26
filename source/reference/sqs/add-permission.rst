[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs add-permission:


**************
add-permission
**************



===========
Description
===========



Adds a permission to a queue for a specific `principal <http://docs.aws.amazon.com/general/latest/gr/glos-chap.html#P>`_ . This allows sharing access to the queue.

 

When you create a queue, you have full control access rights for the queue. Only you, the owner of the queue, can grant or deny permissions to the queue. For more information about these permissions, see `Shared Queues <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/acp-overview.html>`_ in the *Amazon SQS Developer Guide* .

 

.. note::

   

   ``add-permission`` writes an Amazon-SQS-generated policy. If you want to write your own policy, use ``  set-queue-attributes `` to upload your policy. For more information about writing your own policy, see `Using The Access Policy Language <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/AccessPolicyLanguage.html>`_ in the *Amazon SQS Developer Guide* .

   

  Some actions take lists of parameters. These lists are specified using the ``param.n`` notation. Values of ``n`` are integers starting from 1. For example, a parameter list with two elements looks like this:

   

   ``Attribute.1=this``  

   

   ``Attribute.2=that``  

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sqs-2012-11-05/AddPermission>`_


========
Synopsis
========

::

    add-permission
  --queue-url <value>
  --label <value>
  --aws-account-ids <value>
  --actions <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--queue-url`` (string)


  The URL of the Amazon SQS queue to which permissions are added.

   

  Queue URLs are case-sensitive.

  

``--label`` (string)


  The unique identification of the permission you're setting (for example, ``AliceSendMessage`` ). Maximum 80 characters. Allowed characters include alphanumeric characters, hyphens (``-`` ), and underscores (``_`` ).

  

``--aws-account-ids`` (list)


  The AWS account number of the `principal <http://docs.aws.amazon.com/general/latest/gr/glos-chap.html#P>`_ who is given permission. The principal must have an AWS account, but does not need to be signed up for Amazon SQS. For information about locating the AWS account identification, see `Your AWS Identifiers <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/AWSCredentials.html>`_ in the *Amazon SQS Developer Guide* .

  



Syntax::

  "string" "string" ...



``--actions`` (list)


  The action the client wants to allow for the specified principal. The following values are valid:

   

   
  * ``*``   
   
  * ``change-message-visibility``   
   
  * ``delete-message``   
   
  * ``get-queue-attributes``   
   
  * ``get-queue-url``   
   
  * ``receive-message``   
   
  * ``send-message``   
   

   

  For more information about these actions, see `Understanding Permissions <http://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/acp-overview.html#PermissionTypes>`_ in the *Amazon SQS Developer Guide* .

   

  Specifying ``send-message`` , ``delete-message`` , or ``change-message-visibility`` for ``ActionName.n`` also grants permissions for the corresponding batch versions of those actions: ``send-message-batch`` , ``delete-message-batch`` , and ``change-message-visibility-batch`` .

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To add a permission to a queue**

This example enables the specified AWS account to send messages to the specified queue.

Command::

  aws sqs add-permission --queue-url https://sqs.us-east-1.amazonaws.com/80398EXAMPLE/MyQueue --label SendMessagesFromMyQueue --aws-account-ids 12345EXAMPLE --actions SendMessage

Output::

  None.

======
Output
======

None