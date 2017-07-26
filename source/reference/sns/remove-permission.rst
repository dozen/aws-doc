[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns remove-permission:


*****************
remove-permission
*****************



===========
Description
===========



Removes a statement from a topic's access control policy.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sns-2010-03-31/RemovePermission>`_


========
Synopsis
========

::

    remove-permission
  --topic-arn <value>
  --label <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--topic-arn`` (string)


  The ARN of the topic whose access control policy you wish to modify.

  

``--label`` (string)


  The unique label of the statement you want to remove.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None