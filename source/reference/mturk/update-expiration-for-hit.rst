[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk update-expiration-for-hit:


*************************
update-expiration-for-hit
*************************



===========
Description
===========



The ``update-expiration-for-hit`` operation allows you update the expiration time of a HIT. If you update it to a time in the past, the HIT will be immediately expired. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/UpdateExpirationForHIT>`_


========
Synopsis
========

::

    update-expiration-for-hit
  --hit-id <value>
  [--expire-at <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--hit-id`` (string)


  The HIT to update. 

  

``--expire-at`` (timestamp)


  The date and time at which you want the HIT to expire 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

