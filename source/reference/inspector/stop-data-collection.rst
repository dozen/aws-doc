[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector stop-data-collection:


********************
stop-data-collection
********************



===========
Description
===========



Stop data collection for the assessment specified by the assessment ARN.



========
Synopsis
========

::

    stop-data-collection
  --assessment-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--assessment-arn`` (string)


  The ARN of the assessment for which you want to stop the data collection process.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

message -> (string)

  

  Confirmation details of the action performed.

  

  

