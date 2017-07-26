[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis remove-tags-from-stream:


***********************
remove-tags-from-stream
***********************



===========
Description
===========



Removes tags from the specified Amazon Kinesis stream. Removed tags are deleted and cannot be recovered after this operation successfully completes.

 

If you specify a tag that does not exist, it is ignored.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesis-2013-12-02/RemoveTagsFromStream>`_


========
Synopsis
========

::

    remove-tags-from-stream
  --stream-name <value>
  --tag-keys <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stream-name`` (string)


  The name of the stream.

  

``--tag-keys`` (list)


  A list of tag keys. Each corresponding tag is removed from the stream.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None