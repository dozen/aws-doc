[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector stop-assessment-run:


*******************
stop-assessment-run
*******************



===========
Description
===========



Stops the assessment run that is specified by the ARN of the assessment run.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/StopAssessmentRun>`_


========
Synopsis
========

::

    stop-assessment-run
  --assessment-run-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--assessment-run-arn`` (string)


  The ARN of the assessment run that you want to stop.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To stop an assessment run**

The following ``stop-assessment-run`` command stops the assessment run with the ARN of ``arn:aws:inspector:us-west-2:123456789012:target/0-nvgVhaxX/template/0-it5r2S4T/run/0-jOoroxyY``::

  aws inspector stop-assessment-run --assessment-run-arn arn:aws:inspector:us-west-2:123456789012:target/0-nvgVhaxX/template/0-it5r2S4T/run/0-jOoroxyY

For more information, see `Amazon Inspector Assessment Templates and Assessment Runs`_ in the *Amazon Inspector* guide.

.. _`Amazon Inspector Assessment Templates and Assessment Runs`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_assessments.html



======
Output
======

None