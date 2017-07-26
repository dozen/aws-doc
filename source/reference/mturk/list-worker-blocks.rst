[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk list-worker-blocks:


******************
list-worker-blocks
******************



===========
Description
===========



The ``ListWorkersBlocks`` operation retrieves a list of Workers who are blocked from working on your HITs.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/ListWorkerBlocks>`_


========
Synopsis
========

::

    list-worker-blocks
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-token`` (string)


  Pagination token

  

``--max-results`` (integer)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

NextToken -> (string)

  

  If the previous response was incomplete (because there is more data to retrieve), Amazon Mechanical Turk returns a pagination token in the response. You can use this pagination token to retrieve the next set of results. 

  

  

NumResults -> (integer)

  

  The number of assignments on the page in the filtered results list, equivalent to the number of assignments returned by this call.

  

  

WorkerBlocks -> (list)

  

  The list of WorkerBlocks, containing the collection of Worker IDs and reasons for blocking.

  

  (structure)

    

    The WorkerBlock data structure represents a Worker who has been blocked. It has two elements: the WorkerId and the Reason for the block. 

    

    WorkerId -> (string)

      

      The ID of the Worker who accepted the HIT.

      

      

    Reason -> (string)

      

      A message explaining the reason the Worker was blocked. 

      

      

    

  

