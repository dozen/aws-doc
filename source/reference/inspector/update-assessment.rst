[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector update-assessment:


*****************
update-assessment
*****************



===========
Description
===========



Updates the assessment specified by the assessment ARN.



========
Synopsis
========

::

    update-assessment
  --assessment-arn <value>
  --assessment-name <value>
  --duration-in-seconds <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--assessment-arn`` (string)


  Asessment ARN that you want to update.

  

``--assessment-name`` (string)


  Assessment name that you want to update.

  

``--duration-in-seconds`` (integer)


  Assessment duration in seconds that you want to update. The default value is 3600 seconds (one hour). The maximum value is 86400 seconds (one day).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

message -> (string)

  

  Confirmation details of the action performed.

  

  

