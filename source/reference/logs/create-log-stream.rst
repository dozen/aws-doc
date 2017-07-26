[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs create-log-stream:


*****************
create-log-stream
*****************



===========
Description
===========



Creates a log stream for the specified log group.

 

There is no limit on the number of log streams that you can create for a log group.

 

You must use the following guidelines when naming a log stream:

 

 
* Log stream names must be unique within the log group. 
 
* Log stream names can be between 1 and 512 characters long. 
 
* The ':' (colon) and '*' (asterisk) characters are not allowed. 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/logs-2014-03-28/CreateLogStream>`_


========
Synopsis
========

::

    create-log-stream
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

The following command creates a log stream named ``20150601`` in the log group ``my-logs``::

  aws logs create-log-stream --log-group-name my-logs --log-stream-name 20150601


======
Output
======

None