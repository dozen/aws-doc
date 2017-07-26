[ :ref:`aws <cli:aws>` . :ref:`support <cli:aws support>` ]

.. _cli:aws support resolve-case:


************
resolve-case
************



===========
Description
===========



Takes a ``case-id`` and returns the initial state of the case along with the state of the case after the call to  resolve-case completed.



========
Synopsis
========

::

    resolve-case
  [--case-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--case-id`` (string)


  The AWS Support case ID requested or returned in the call. The case ID is an alphanumeric string formatted as shown in this example: case-*12345678910-2013-c4c1d2bf33c5cf47* 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

initialCaseStatus -> (string)

  

  The status of the case when the  resolve-case request was sent.

  

  

finalCaseStatus -> (string)

  

  The status of the case after the  resolve-case request was processed.

  

  

