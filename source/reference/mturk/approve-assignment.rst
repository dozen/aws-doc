[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk approve-assignment:


******************
approve-assignment
******************



===========
Description
===========



The ``approve-assignment`` operation approves the results of a completed assignment. 

 

Approving an assignment initiates two payments from the Requester's Amazon.com account 

 

 
* The Worker who submitted the results is paid the reward specified in the HIT.  
 
* Amazon Mechanical Turk fees are debited.  
 

 

If the Requester's account does not have adequate funds for these payments, the call to approve-assignment returns an exception, and the approval is not processed. You can include an optional feedback message with the approval, which the Worker can see in the Status section of the web site. 

 

You can also call this operation for assignments that were previous rejected and approve them by explicitly overriding the previous rejection. This only works on rejected assignments that were submitted within the previous 30 days and only if the assignment's related HIT has not been deleted. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/ApproveAssignment>`_


========
Synopsis
========

::

    approve-assignment
  --assignment-id <value>
  [--requester-feedback <value>]
  [--override-rejection | --no-override-rejection]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--assignment-id`` (string)


  The ID of the assignment. The assignment must correspond to a HIT created by the Requester. 

  

``--requester-feedback`` (string)


  A message for the Worker, which the Worker can see in the Status section of the web site. 

  

``--override-rejection`` | ``--no-override-rejection`` (boolean)


  A flag indicating that an assignment should be approved even if it was previously rejected. Defaults to ``False`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

