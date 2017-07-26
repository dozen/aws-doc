[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector start-assessment-run:


********************
start-assessment-run
********************



===========
Description
===========



Starts the assessment run specified by the ARN of the assessment template. For this API to function properly, you must not exceed the limit of running up to 500 concurrent agents per AWS account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/StartAssessmentRun>`_


========
Synopsis
========

::

    start-assessment-run
  --assessment-template-arn <value>
  [--assessment-run-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--assessment-template-arn`` (string)


  The ARN of the assessment template of the assessment run that you want to start.

  

``--assessment-run-name`` (string)


  You can specify the name for the assessment run. The name must be unique for the assessment template whose ARN is used to start the assessment run.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To start an assessment run**

The following ``start-assessment-run`` command starts the assessment run named ``examplerun`` using the assessment template with the ARN of ``arn:aws:inspector:us-west-2:123456789012:target/0-nvgVhaxX/template/0-it5r2S4T``::

  aws inspector start-assessment-run --assessment-run-name examplerun --assessment-template-arn arn:aws:inspector:us-west-2:123456789012:target/0-nvgVhaxX/template/0-it5r2S4T

Output::

  {
	"assessmentRunArn": "arn:aws:inspector:us-west-2:123456789012:target/0-nvgVhaxX/template/0-it5r2S4T/run/0-jOoroxyY"
  }

For more information, see `Amazon Inspector Assessment Templates and Assessment Runs`_ in the *Amazon Inspector* guide.

.. _`Amazon Inspector Assessment Templates and Assessment Runs`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_assessments.html



======
Output
======

assessmentRunArn -> (string)

  

  The ARN of the assessment run that has been started.

  

  

