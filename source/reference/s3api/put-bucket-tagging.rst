[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api put-bucket-tagging:


******************
put-bucket-tagging
******************



===========
Description
===========

Sets the tags for a bucket.

========
Synopsis
========

::

    put-bucket-tagging
  --bucket <value>
  [--content-md5 <value>]
  --tagging <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--bucket`` (string)


``--content-md5`` (string)


``--tagging`` (structure)




Shorthand Syntax::

    TagSet=[{Key=string,Value=string},{Key=string,Value=string}]




JSON Syntax::

  {
    "TagSet": [
      {
        "Key": "string",
        "Value": "string"
      }
      ...
    ]
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command applies a tagging configuration to a bucket named ``my-bucket``::

  aws s3api put-bucket-tagging --bucket my-bucket --tagging file://tagging.json

The file ``tagging.json`` is a JSON document in the current folder that specifies tags::

  {
     "TagSet": [
       {
         "Key": "organization",
         "Value": "marketing"
       }
     ]
  }


======
Output
======

None