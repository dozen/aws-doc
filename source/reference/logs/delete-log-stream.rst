[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs delete-log-stream:


*****************
delete-log-stream
*****************



===========
Description
===========



Deletes a log stream and permanently deletes all the archived log events associated with it. 



========
Synopsis
========

::

    delete-log-stream
  --log-group-name <value>
  --log-stream-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--log-group-name`` (string)


  The name of the log group under which the log stream to delete belongs.

  

``--log-stream-name`` (string)


  The name of the log stream to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command deletes a log stream named ``20150531`` from a log group named ``my-logs``::

  aws logs delete-log-stream --log-group-name my-logs --log-stream-name 20150531


======
Output
======

None