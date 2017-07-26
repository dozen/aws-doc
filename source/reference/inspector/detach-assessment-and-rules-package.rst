[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector detach-assessment-and-rules-package:


***********************************
detach-assessment-and-rules-package
***********************************



===========
Description
===========



Detaches the rules package specified by the rules package ARN from the assessment specified by the assessment ARN.



========
Synopsis
========

::

    detach-assessment-and-rules-package
  --assessment-arn <value>
  --rules-package-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--assessment-arn`` (string)


  The ARN specifying the assessment from which you want to detach a rules package.

  

``--rules-package-arn`` (string)


  The ARN specifying the rules package that you want to detach from the assessment.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

message -> (string)

  

  Confirmation details of the action performed.

  

  

