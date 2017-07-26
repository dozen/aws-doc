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



========
Synopsis
========

::

    add-tags-to-stream
  --stream-name <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None