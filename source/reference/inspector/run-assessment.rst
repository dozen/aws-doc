[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector run-assessment:


**************
run-assessment
**************



===========
Description
===========



Starts the analysis of the application’s behavior against selected rule packages for the assessment specified by the assessment ARN.



========
Synopsis
========

::

    run-assessment
  --assessment-arn <value>
  --run-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--assessment-arn`` (string)


  The ARN of the assessment that you want to run.

  

``--run-name`` (string)


  A name specifying the run of the assessment.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

runArn -> (string)

  

  The ARN specifying the run of the assessment.

  

  

