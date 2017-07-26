[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs delete-log-stream:


*****************
delete-log-stream
*****************



===========
Description
===========



Deletes the specified log stream and permanently deletes all the archived log events associated with the log stream.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/logs-2014-03-28/DeleteLogStream>`_


========
Synopsis
========

::

    delete-log-stream
  --log-group-name <value>
  --log-stream-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--log-group-name`` (string)


  The name of the log group.

  

``--log-stream-name`` (string)


  The name of the log stream.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command deletes a log stream named ``20150531`` from a log group named ``my-logs``::

  aws logs delete-log-stream --log-group-name my-logs --log-stream-name 20150531


======
Output
======

None