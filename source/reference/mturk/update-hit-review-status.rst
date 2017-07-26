[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk update-hit-review-status:


************************
update-hit-review-status
************************



===========
Description
===========



The ``update-hit-review-status`` operation updates the status of a HIT. If the status is Reviewable, this operation can update the status to Reviewing, or it can revert a Reviewing HIT back to the Reviewable status. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/UpdateHITReviewStatus>`_


========
Synopsis
========

::

    update-hit-review-status
  --hit-id <value>
  [--revert | --no-revert]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--hit-id`` (string)


  The ID of the HIT to update. 

  

``--revert`` | ``--no-revert`` (boolean)


  Specifies how to update the HIT status. Default is ``False`` . 

   

   
  * Setting this to false will only transition a HIT from ``Reviewable`` to ``Reviewing``   
   
  * Setting this to true will only transition a HIT from ``Reviewing`` to ``Reviewable``   
   

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

