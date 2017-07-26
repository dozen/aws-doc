[ :ref:`aws <cli:aws>` . :ref:`cur <cli:aws cur>` ]

.. _cli:aws cur delete-report-definition:


************************
delete-report-definition
************************



===========
Description
===========

Delete a specified report definition

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cur-2017-01-06/DeleteReportDefinition>`_


========
Synopsis
========

::

    delete-report-definition
  [--report-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--report-name`` (string)
Preferred name for a report, it has to be unique. Must starts with a number/letter, case sensitive. Limited to 256 characters.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ResponseMessage -> (string)

  A message indicates if the deletion is successful.

  

