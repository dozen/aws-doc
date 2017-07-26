[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis add-tags-to-stream:


******************
add-tags-to-stream
******************



===========
Description
===========



Adds or updates tags for the specified Amazon Kinesis stream. Each stream can have up to 10 tags.

 

If tags have already been assigned to the stream, ``add-tags-to-stream`` overwrites any existing tags that correspond to the specified tag keys.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesis-2013-12-02/AddTagsToStream>`_


========
Synopsis
========

::

    add-tags-to-stream
  --stream-name <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stream-name`` (string)


  The name of the stream.

  

``--tags`` (map)


  The set of key-value pairs to use to create the tags.

  



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