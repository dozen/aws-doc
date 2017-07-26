[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis increase-stream-retention-period:


********************************
increase-stream-retention-period
********************************



===========
Description
===========



Increases the stream's retention period, which is the length of time data records are accessible after they are added to the stream. The maximum value of a stream’s retention period is 168 hours (7 days).

 

Upon choosing a longer stream retention period, this operation will increase the time period records are accessible that have not yet expired. However, it will not make previous data that has expired (older than the stream’s previous retention period) accessible after the operation has been called. For example, if a stream’s retention period is set to 24 hours and is increased to 168 hours, any data that is older than 24 hours will remain inaccessible to consumer applications.



========
Synopsis
========

::

    increase-stream-retention-period
  --stream-name <value>
  --retention-period-hours <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stream-name`` (string)


  The name of the stream to modify.

  

``--retention-period-hours`` (integer)


  The new retention period of the stream, in hours. Must be more than the current retention period.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None