[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs change-message-visibility-batch:


*******************************
change-message-visibility-batch
*******************************



===========
Description
===========



Changes the visibility timeout of multiple messages. This is a batch version of ``  change-message-visibility .`` The result of the action on each message is reported individually in the response. You can send up to 10 ``  change-message-visibility `` requests with each ``change-message-visibility-batch`` action.

 

.. warning::

   

  Because the batch request can result in a combination of successful and unsuccessful actions, you should check for batch errors even when the call returns an HTTP status code of ``200`` .

   

 

.. note::

   

  Some actions take lists of parameters. These lists are specified using the ``param.n`` notation. Values of ``n`` are integers starting from 1. For example, a parameter list with two elements looks like this:

   

   ``Attribute.1=this``  

   

   ``Attribute.2=that``  

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sqs-2012-11-05/ChangeMessageVisibilityBatch>`_


========
Synopsis
========

::

    change-message-visibility-batch
  --queue-url <value>
  --entries <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--queue-url`` (string)


  The URL of the Amazon SQS queue whose messages' visibility is changed.

   

  Queue URLs are case-sensitive.

  

``--entries`` (list)


  A list of receipt handles of the messages for which the visibility timeout must be changed.

  



Shorthand Syntax::

    Id=string,ReceiptHandle=string,VisibilityTimeout=integer ...




JSON Syntax::

  [
    {
      "Id": "string",
      "ReceiptHandle": "string",
      "VisibilityTimeout": integer
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To change multiple messages' timeout visibilities as a batch**

This example changes the 2 specified messages' timeout visibilities to 10 hours (10 hours * 60 minutes * 60 seconds).

Command::

  aws sqs change-message-visibility-batch --queue-url https://sqs.us-east-1.amazonaws.com/80398EXAMPLE/MyQueue --entries file://change-message-visibility-batch.json
  
Input file (change-message-visibility-batch.json)::

  [
    {
      "Id": "FirstMessage",
	  "ReceiptHandle": "AQEBhz2q...Jf3kaw==",
	  "VisibilityTimeout": 36000
    },
    {
      "Id": "SecondMessage",
	  "ReceiptHandle": "AQEBkTUH...HifSnw==",
	  "VisibilityTimeout": 36000  
    }
  ]

Output::

  {
    "Successful": [
      {
        "Id": "SecondMessage"
      },
      {
        "Id": "FirstMessage"
      }
    ]
  }



======
Output
======

Successful -> (list)

  

  A list of ``  ChangeMessageVisibilityBatchResultEntry `` items.

  

  (structure)

    

    Encloses the ``Id`` of an entry in ``  change-message-visibility-batch .``  

    

    Id -> (string)

      

      Represents a message whose visibility timeout has been changed successfully.

      

      

    

  

Failed -> (list)

  

  A list of ``  BatchResultErrorEntry `` items.

  

  (structure)

    

    This is used in the responses of batch API to give a detailed description of the result of an action on each entry in the request.

    

    Id -> (string)

      

      The ``Id`` of an entry in a batch request.

      

      

    SenderFault -> (boolean)

      

      Specifies whether the error happened due to the sender's fault.

      

      

    Code -> (string)

      

      An error code representing why the action failed on this entry.

      

      

    Message -> (string)

      

      A message explaining why the action failed on this entry.

      

      

    

  

