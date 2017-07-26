[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector start-data-collection:


*********************
start-data-collection
*********************



===========
Description
===========



Starts data collection for the assessment specified by the assessment ARN. For this API to function properly, you must not exceed the limit of running up to 500 concurrent agents per AWS account.



========
Synopsis
========

::

    start-data-collection
  --assessment-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--assessment-arn`` (string)


  The ARN of the assessment for which you want to start the data collection process.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

message -> (string)

  

  Confirmation details of the action performed.

  

  

