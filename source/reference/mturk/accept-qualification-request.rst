[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk accept-qualification-request:


****************************
accept-qualification-request
****************************



===========
Description
===========



The ``accept-qualification-request`` operation approves a Worker's request for a Qualification. 

 

Only the owner of the Qualification type can grant a Qualification request for that type. 

 

A successful request for the ``accept-qualification-request`` operation returns with no errors and an empty body. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/AcceptQualificationRequest>`_


========
Synopsis
========

::

    accept-qualification-request
  --qualification-request-id <value>
  [--integer-value <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--qualification-request-id`` (string)


  The ID of the Qualification request, as returned by the ``GetQualificationRequests`` operation.

  

``--integer-value`` (integer)


  The value of the Qualification. You can omit this value if you are using the presence or absence of the Qualification as the basis for a HIT requirement. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

