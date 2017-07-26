[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api put-bucket-tagging:


******************
put-bucket-tagging
******************



===========
Description
===========

Sets the tags for a bucket.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/PutBucketTagging>`_


========
Synopsis
========

::

    put-bucket-tagging
  --bucket <value>
  [--content-md5 <value>]
  --tagging <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

Or apply a tagging configuration to ``my-bucket`` directly from the command line::

  aws s3api put-bucket-tagging --bucket my-bucket --tagging 'TagSet=[{Key=organization,Value=marketing}]'


======
Output
======

None