[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs create-log-stream:


*****************
create-log-stream
*****************



===========
Description
===========



Creates a new log stream in the specified log group. The name of the log stream must be unique within the log group. There is no limit on the number of log streams that can exist in a log group. 

 

You must use the following guidelines when naming a log stream: 

 
* Log stream names can be between 1 and 512 characters long.
 
* The ':' colon character is not allowed.
 

 



========
Synopsis
========

::

    create-log-stream
  --log-group-name <value>
  --log-stream-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--log-group-name`` (string)


  The name of the log group under which the log stream is to be created.

  

``--log-stream-name`` (string)


  The name of the log stream to create.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command creates a log stream named ``20150601`` in the log group ``my-logs``::

  aws logs create-log-stream --log-group-name my-logs --log-stream-name 20150601


======
Output
======

None