[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis remove-tags-from-stream:


***********************
remove-tags-from-stream
***********************



===========
Description
===========



Deletes tags from the specified Amazon Kinesis stream.

 

If you specify a tag that does not exist, it is ignored.



========
Synopsis
========

::

    remove-tags-from-stream
  --stream-name <value>
  --tag-keys <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None