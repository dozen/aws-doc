[ :ref:`aws <cli:aws>` . :ref:`support <cli:aws support>` ]

.. _cli:aws support resolve-case:


************
resolve-case
************



===========
Description
===========



Takes a ``caseId`` and returns the initial state of the case along with the state of the case after the call to  resolve-case completed.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/support-2013-04-15/ResolveCase>`_


========
Synopsis
========

::

    resolve-case
  [--case-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--case-id`` (string)


  The AWS Support case ID requested or returned in the call. The case ID is an alphanumeric string formatted as shown in this example: case-*12345678910-2013-c4c1d2bf33c5cf47*  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

initialCaseStatus -> (string)

  

  The status of the case when the  resolve-case request was sent.

  

  

finalCaseStatus -> (string)

  

  The status of the case after the  resolve-case request was processed.

  

  

