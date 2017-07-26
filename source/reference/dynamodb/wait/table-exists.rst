[ :ref:`aws <cli:aws>` . :ref:`dynamodb <cli:aws dynamodb>` . :ref:`wait <cli:aws dynamodb wait>` ]

.. _cli:aws dynamodb wait table-exists:


************
table-exists
************



===========
Description
===========

Wait until JMESPath query Table.TableStatus returns ACTIVE when polling with ``describe-table``. It will poll every 20 seconds until a successful state has been reached. This will exit with a return code of 255 after 25 failed checks.

========
Synopsis
========

::

    table-exists
  --table-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--table-name`` (string)


  The name of the table to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None