[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk create-additional-assignments-for-hit:


*************************************
create-additional-assignments-for-hit
*************************************



===========
Description
===========



The ``create-additional-assignments-for-hit`` operation increases the maximum number of assignments of an existing HIT. 

 

To extend the maximum number of assignments, specify the number of additional assignments.

 

.. note::

   

   
  * HITs created with fewer than 10 assignments cannot be extended to have 10 or more assignments. Attempting to add assignments in a way that brings the total number of assignments for a HIT from fewer than 10 assignments to 10 or more assignments will result in an ``AWS.MechanicalTurk.InvalidMaximumAssignmentsIncrease`` exception. 
   
  * HITs that were created before July 22, 2015 cannot be extended. Attempting to extend HITs that were created before July 22, 2015 will result in an ``AWS.MechanicalTurk.HITTooOldForExtension`` exception.  
   

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/CreateAdditionalAssignmentsForHIT>`_


========
Synopsis
========

::

    create-additional-assignments-for-hit
  --hit-id <value>
  [--number-of-additional-assignments <value>]
  [--unique-request-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--hit-id`` (string)


  The ID of the HIT to extend.

  

``--number-of-additional-assignments`` (integer)


  The number of additional assignments to request for this HIT.

  

``--unique-request-token`` (string)


  A unique identifier for this request, which allows you to retry the call on error without extending the HIT multiple times. This is useful in cases such as network timeouts where it is unclear whether or not the call succeeded on the server. If the extend HIT already exists in the system from a previous call using the same ``UniqueRequestToken`` , subsequent calls will return an error with a message containing the request ID. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

