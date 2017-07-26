[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs create-log-group:


****************
create-log-group
****************



===========
Description
===========



Creates a log group with the specified name.

 

You can create up to 5000 log groups per account.

 

You must use the following guidelines when naming a log group:

 

 
* Log group names must be unique within a region for an AWS account. 
 
* Log group names can be between 1 and 512 characters long. 
 
* Log group names consist of the following characters: a-z, A-Z, 0-9, '_' (underscore), '-' (hyphen), '/' (forward slash), and '.' (period). 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/logs-2014-03-28/CreateLogGroup>`_


========
Synopsis
========

::

    create-log-group
  --log-group-name <value>
  [--tags <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--log-group-name`` (string)


  The name of the log group.

  

``--tags`` (map)


  The key-value pairs to use for the tags.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command creates a log group named ``my-logs``::

  aws logs create-log-group --log-group-name my-logs


======
Output
======

None