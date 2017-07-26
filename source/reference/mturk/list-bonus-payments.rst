[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk list-bonus-payments:


*******************
list-bonus-payments
*******************



===========
Description
===========



The ``list-bonus-payments`` operation retrieves the amounts of bonuses you have paid to Workers for a given HIT or assignment. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/ListBonusPayments>`_


========
Synopsis
========

::

    list-bonus-payments
  [--hit-id <value>]
  [--assignment-id <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--hit-id`` (string)


  The ID of the HIT associated with the bonus payments to retrieve. If not specified, all bonus payments for all assignments for the given HIT are returned. Either the HITId parameter or the AssignmentId parameter must be specified

  

``--assignment-id`` (string)


  The ID of the assignment associated with the bonus payments to retrieve. If specified, only bonus payments for the given assignment are returned. Either the HITId parameter or the AssignmentId parameter must be specified

  

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

NumResults -> (integer)

  

  The number of bonus payments on this page in the filtered results list, equivalent to the number of bonus payments being returned by this call. 

  

  

NextToken -> (string)

  

  If the previous response was incomplete (because there is more data to retrieve), Amazon Mechanical Turk returns a pagination token in the response. You can use this pagination token to retrieve the next set of results. 

  

  

BonusPayments -> (list)

  

  A successful request to the list-bonus-payments operation returns a list of BonusPayment objects. 

  

  (structure)

    

    An object representing a Bonus payment paid to a Worker.

    

    WorkerId -> (string)

      

      The ID of the Worker to whom the bonus was paid.

      

      

    BonusAmount -> (string)

      

      A string representing a numeric value.

      

      

    AssignmentId -> (string)

      

      The ID of the assignment associated with this bonus payment.

      

      

    Reason -> (string)

      

      The Reason text given when the bonus was granted, if any.

      

      

    GrantTime -> (timestamp)

      

      The date and time of when the bonus was granted.

      

      

    

  

