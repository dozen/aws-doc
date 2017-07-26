[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs delete-message-batch:


********************
delete-message-batch
********************



===========
Description
===========



Deletes up to ten messages from the specified queue. This is a batch version of  delete-message . The result of the delete action on each message is reported individually in the response.

 

.. warning::

   

  Because the batch request can result in a combination of successful and unsuccessful actions, you should check for batch errors even when the call returns an HTTP status code of 200. 

   

 

.. note::

  Some API actions take lists of parameters. These lists are specified using the ``param.n`` notation. Values of ``n`` are integers starting from 1. For example, a parameter list with two elements looks like this: 

 

``Attribute.1=this`` 

 

``Attribute.2=that`` 



========
Synopsis
========

::

    delete-message-batch
  --queue-url <value>
  --entries <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--queue-url`` (string)


  The URL of the Amazon SQS queue to take action on.

  

``--entries`` (list)


  A list of receipt handles for the messages to be deleted.

  



Shorthand Syntax::

    Id=string,ReceiptHandle=string ...




JSON Syntax::

  [
    {
      "Id": "string",
      "ReceiptHandle": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete multiple messages as a batch**

This example deletes the specified messages.

Command::

  aws sqs delete-message-batch --queue-url https://sqs.us-east-1.amazonaws.com/80398EXAMPLE/MyQueue --entries file://delete-message-batch.json

Input file (delete-message-batch.json)::

  [
    {
	  "Id": "FirstMessage",
	  "ReceiptHandle": "AQEB1mgl...Z4GuLw=="
    },
    {
      "Id": "SecondMessage",
	  "ReceiptHandle": "AQEBLsYM...VQubAA=="
    }
  ]

Output::

  {
    "Successful": [
      {
        "Id": "FirstMessage"
      },
      {
        "Id": "SecondMessage"
      }
    ]
  }

======
Output
======

Successful -> (list)

  

  A list of  DeleteMessageBatchResultEntry items.

  

  (structure)

    

    Encloses the id an entry in  delete-message-batch .

    

    Id -> (string)

      

      Represents a successfully deleted message.

      

      

    

  

Failed -> (list)

  

  A list of  BatchResultErrorEntry items.

  

  (structure)

    

    This is used in the responses of batch API to give a detailed description of the result of an action on each entry in the request.

    

    Id -> (string)

      

      The id of an entry in a batch request.

      

      

    SenderFault -> (boolean)

      

      Whether the error happened due to the sender's fault.

      

      

    Code -> (string)

      

      An error code representing why the action failed on this entry.

      

      

    Message -> (string)

      

      A message explaining why the action failed on this entry.

      

      

    

  

