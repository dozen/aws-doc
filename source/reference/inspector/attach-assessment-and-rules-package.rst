[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector attach-assessment-and-rules-package:


***********************************
attach-assessment-and-rules-package
***********************************



===========
Description
===========



Attaches the rules package specified by the rules package ARN to the assessment specified by the assessment ARN.



========
Synopsis
========

::

    attach-assessment-and-rules-package
  --assessment-arn <value>
  --rules-package-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--assessment-arn`` (string)


  The ARN specifying the assessment to which you want to attach a rules package.

  

``--rules-package-arn`` (string)


  The ARN specifying the rules package that you want to attach to the assessment.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

message -> (string)

  

  Confirmation details of the action performed.

  

  

