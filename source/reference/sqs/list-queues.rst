[ :ref:`aws <cli:aws>` . :ref:`sqs <cli:aws sqs>` ]

.. _cli:aws sqs list-queues:


***********
list-queues
***********



===========
Description
===========



Returns a list of your queues. The maximum number of queues that can be returned is 1,000. If you specify a value for the optional ``QueueNamePrefix`` parameter, only queues with a name that begins with the specified value are returned.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sqs-2012-11-05/ListQueues>`_


========
Synopsis
========

::

    list-queues
  [--queue-name-prefix <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--queue-name-prefix`` (string)


  A string to use for filtering the list results. Only those queues whose name begins with the specified string are returned.

   

  Queue names are case-sensitive.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list queues**

This example lists all queues.

Command::

  aws sqs list-queues

Output::

  {
    "QueueUrls": [
      "https://queue.amazonaws.com/80398EXAMPLE/MyDeadLetterQueue",
      "https://queue.amazonaws.com/80398EXAMPLE/MyQueue",
      "https://queue.amazonaws.com/80398EXAMPLE/MyOtherQueue",        
      "https://queue.amazonaws.com/80398EXAMPLE/TestQueue1",
	  "https://queue.amazonaws.com/80398EXAMPLE/TestQueue2"		
    ]
  }

This example lists only queues that start with "My".

Command::

  aws sqs list-queues --queue-name-prefix My

Output::

  {
    "QueueUrls": [
      "https://queue.amazonaws.com/80398EXAMPLE/MyDeadLetterQueue",
      "https://queue.amazonaws.com/80398EXAMPLE/MyQueue",
      "https://queue.amazonaws.com/80398EXAMPLE/MyOtherQueue"	
    ]
  }

======
Output
======

QueueUrls -> (list)

  

  A list of queue URLs, up to 1,000 entries.

  

  (string)

    

    

  

