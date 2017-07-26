[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis decrease-stream-retention-period:


********************************
decrease-stream-retention-period
********************************



===========
Description
===========



Decreases the stream's retention period, which is the length of time data records are accessible after they are added to the stream. The minimum value of a stream’s retention period is 24 hours. 

 

This operation may result in lost data. For example, if the stream's retention period is 48 hours and is decreased to 24 hours, any data already in the stream that is older than 24 hours is inaccessible.



========
Synopsis
========

::

    decrease-stream-retention-period
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


  The new retention period of the stream, in hours. Must be less than the current retention period.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None