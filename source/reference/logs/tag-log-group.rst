[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs tag-log-group:


*************
tag-log-group
*************



===========
Description
===========



Adds or updates the specified tags for the specified log group.

 

To list the tags for a log group, use  list-tags-log-group . To remove tags, use  untag-log-group .

 

For more information about tags, see `Tag Log Groups in Amazon CloudWatch Logs <http://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/log-group-tagging.html>`_ in the *Amazon CloudWatch Logs User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/logs-2014-03-28/TagLogGroup>`_


========
Synopsis
========

::

    tag-log-group
  --log-group-name <value>
  --tags <value>
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



======
Output
======

None