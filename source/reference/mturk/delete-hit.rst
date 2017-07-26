[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk delete-hit:


**********
delete-hit
**********



===========
Description
===========



The ``delete-hit`` operation is used to delete HIT that is no longer needed. Only the Requester who created the HIT can delete it. 

 

You can only dispose of HITs that are in the ``Reviewable`` state, with all of their submitted assignments already either approved or rejected. If you call the delete-hit operation on a HIT that is not in the ``Reviewable`` state (for example, that has not expired, or still has active assignments), or on a HIT that is Reviewable but without all of its submitted assignments already approved or rejected, the service will return an error. 

 

.. note::

   

   
  * HITs are automatically disposed of after 120 days.  
   
  * After you dispose of a HIT, you can no longer approve the HIT's rejected assignments.  
   
  * Disposed HITs are not returned in results for the list-hits operation.  
   
  * Disposing HITs can improve the performance of operations such as list-reviewable-hits and ListHITs.  
   

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/DeleteHIT>`_


========
Synopsis
========

::

    delete-hit
  --hit-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--hit-id`` (string)


  The ID of the HIT to be deleted.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

