[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk get-account-balance:


*******************
get-account-balance
*******************



===========
Description
===========



The ``get-account-balance`` operation retrieves the amount of money in your Amazon Mechanical Turk account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/GetAccountBalance>`_


========
Synopsis
========

::

    get-account-balance
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

AvailableBalance -> (string)

  

  A string representing a numeric value.

  

  

OnHoldBalance -> (string)

  

  A string representing a numeric value.

  

  

