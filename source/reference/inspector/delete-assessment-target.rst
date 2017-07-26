[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector delete-assessment-target:


************************
delete-assessment-target
************************



===========
Description
===========



Deletes the assessment target that is specified by the ARN of the assessment target.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/DeleteAssessmentTarget>`_


========
Synopsis
========

::

    delete-assessment-target
  --assessment-target-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--assessment-target-arn`` (string)


  The ARN that specifies the assessment target that you want to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete an assessment target**

The following ``delete-assessment-target`` command deletes the assessment target with the ARN of  ``arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq``::

  aws inspector delete-assessment-target --assessment-target-arn arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq

For more information, see `Amazon Inspector Assessment Targets`_ in the *Amazon Inspector* guide.

.. _`Amazon Inspector Assessment Targets`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_applications.html



======
Output
======

None