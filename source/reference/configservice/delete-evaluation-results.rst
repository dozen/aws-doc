[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice delete-evaluation-results:


*************************
delete-evaluation-results
*************************



===========
Description
===========



Deletes the evaluation results for the specified Config rule. You can specify one Config rule per request. After you delete the evaluation results, you can call the  start-config-rules-evaluation API to start evaluating your AWS resources against the rule.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/config-2014-11-12/DeleteEvaluationResults>`_


========
Synopsis
========

::

    delete-evaluation-results
  --config-rule-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--config-rule-name`` (string)


  The name of the Config rule for which you want to delete the evaluation results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To manually delete evaluation results**

The following command deletes the current evaluation results for the AWS managed rule s3-bucket-versioning-enabled::

    aws configservice delete-evaluation-results --config-rule-name s3-bucket-versioning-enabled

======
Output
======

