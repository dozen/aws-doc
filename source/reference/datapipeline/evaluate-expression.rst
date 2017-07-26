[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline evaluate-expression:


*******************
evaluate-expression
*******************



===========
Description
===========



Task runners call ``evaluate-expression`` to evaluate a string in the context of the specified object. For example, a task runner can evaluate SQL queries stored in Amazon S3.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/datapipeline-2012-10-29/EvaluateExpression>`_


========
Synopsis
========

::

    evaluate-expression
  --pipeline-id <value>
  --object-id <value>
  --expression <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--pipeline-id`` (string)


  The ID of the pipeline.

  

``--object-id`` (string)


  The ID of the object.

  

``--expression`` (string)


  The expression to evaluate.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

evaluatedExpression -> (string)

  

  The evaluated expression.

  

  

