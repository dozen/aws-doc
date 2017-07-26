[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs list-tags-log-group:


*******************
list-tags-log-group
*******************



===========
Description
===========



Lists the tags for the specified log group.

 

To add tags, use  tag-log-group . To remove tags, use  untag-log-group .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/logs-2014-03-28/ListTagsLogGroup>`_


========
Synopsis
========

::

    list-tags-log-group
  --log-group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--log-group-name`` (string)


  The name of the log group.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

tags -> (map)

  

  The tags.

  

  key -> (string)

    

    

  value -> (string)

    

    

  

